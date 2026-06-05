## Deception in LLMs

In multi-agent interactive game systems, the abilities of large language models (LLMs) both to deceive and to detect deception are crucial during interactive reasoning. Reliably evaluating these capabilities is therefore essential for understanding how LLMs behave in adversarial multi-agent settings. However, prior work has largely treated deception evaluation as static classification, thereby ignoring the interactive, adversarial, and longitudinal nature of real deceptive dynamics.

### [WOLF](https://arxiv.org/abs/2512.09187)

WOLF is a multi-agent social deduction benchmark built on Werewolf that lets deception *production* and deception *detection* be measured separately. It classifies each statement using four deception types, plus a `none` baseline for truthful statements:

- **none** *(baseline)*: A truthful statement with no deceptive intent. Included so that honesty is explicitly represented alongside the deception categories.
- **omission**: Withholding relevant information. The deception comes not from a false claim but from leaving out details that would change how the statement is interpreted.
- **distortion**: Twisting true information — facts are present but exaggerated, downplayed, or reframed to create a false impression.
- **misdirection**: Steering attention away from what matters, redirecting focus to less relevant or distracting points rather than stating anything false.
- **fabrication**: Inventing entirely false information. The strongest form, with no basis in truth.

**Measurement protocol.** Every public statement is treated as one unit of analysis. The speaker self-assesses the honesty of each statement (made during debate or when explaining a vote), and every other player records their own perception of the speaker's honesty. Capturing both sides at once is what lets WOLF measure production and detection in real time.

**Suspicion update.** Because suspicion shifts over the course of a game, WOLF tracks it with exponential smoothing:

$$D_{t+1}(o, t) = \alpha \cdot s(o, t) + (1 - \alpha) \cdot D_t(o, t), \quad \alpha = 0.7$$

Here $s(o, t)$ is observer $o$'s suspicion toward target $t$ for the **single new statement** (an instantaneous value), while $D_t(o, t)$ is $o$'s suspicion toward $t$ **accumulated from all prior statements**. With $\alpha = 0.7$, a new statement carries most of the weight but past history still dampens overreaction.

> **My note on notation:** the paper reuses $t$ for two different things — the time step (the $t{+}1$ / $t$ subscript) and the *target* player (the $t$ inside $(o, t)$, made explicit in §5.4's $D[o,t]$). Worth flagging as a clarity issue if I cite this.

**Metrics.** The paper actually reports five metrics (§4.5); the three most central:

- **Deception production rate** — how often deception occurs for a given role.
- **Detection accuracy** — peer judgments compared against speaker self-reports as ground truth.
- **Calibration** — whether suspicion values behave like probabilities (measured by Brier score).
- *(also: Cross-perception matrix — how suspicion distributes across observer→target pairs; and Threshold analyses — ROC/AUPRC, whether suspicion can drive rule-based decisions.)*

### My critique

WOLF is a genuine contribution: an interactive framework that evaluates both the production and the detection of deception, rather than treating deception as static classification. But it is hard to read in places, mainly because key terms are introduced without definition. Several details that a reader needs are also missing or unclear:

- **Which LLM(s)** the experiments actually use — the paper says only "actual language models" and mentions an A100 in the compute section, but never names a model.
- **What prompts** guide each role's behavior (the role-play instructions for Villager / Werewolf / Seer / Doctor).
- **How the observation/analysis texts are generated** from each statement.
- Whether each metric is reported **per role or per model**.