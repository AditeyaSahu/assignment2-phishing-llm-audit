# A Trustworthiness Audit of Open-Source LLMs for Phishing-Support Advice

## Abstract
- Brief problem statement
- Research gap
- 3 models
- 300 prompts
- 900 generated outputs
- 4 task groups: detection, recovery, fairness, robustness
- Main finding direction: accuracy is not enough; protective quality matters

---

## 1. Introduction
### Purpose
Introducing the problem clearly and establish why this study matters.

### Points to cover
- Phishing is a serious human-centered cybersecurity problem.
- Users may increasingly rely on LLMs when deciding whether a message is dangerous or when trying to recover from a suspected scam.
- Existing LLM trustworthiness work is broad, but phishing-support trustworthiness is underexplored.
- In this setting, a correct classification alone is not sufficient; the model must also provide safe and useful next-step advice.

### End the section with:
- Research gap
- Study objective
- Contributions

### Planned contribution statements
- We evaluate 3 open-source LLMs in phishing-support scenarios.
- We construct a 300-prompt benchmark with 900 total outputs.
- We measure not only detection performance, but also protective-quality, fairness, and robustness.
- We provide error analysis, limitations, and deployment implications.

---

## 2. Related Work

### 2.1 LLM trustworthiness benchmarks
Cover:
- DECODINGTRUST
- one secondary trustworthiness framework

Key point:
- Trustworthiness must be evaluated across multiple dimensions, not only accuracy.

### 2.2 Human-centered phishing susceptibility
Cover:
- why phishing vulnerability depends on context
- why users need support, not just technical detection systems

Key point:
- our persona-based fairness conditions are controlled probes, not claims about real-world group superiority/inferiority

### 2.3 Phishing detection and mitigation
Cover:
- phishing cue recognition
- remediation and reporting guidance
- why safe next-step advice matters after suspected compromise

### 2.4 Gap statement
State clearly:
- existing work rarely audits open-source LLMs as phishing-support assistants for vulnerable users
- our project fills that gap with a focused trustworthiness audit

---

## 3. Research Questions

### RQ1
How accurately do open-source LLMs detect phishing risk and provide appropriate recovery guidance in user-facing support scenarios?

### RQ2
Does the protective quality of LLM responses change when only the user persona changes?

### RQ3
How robust are LLM responses under manipulative prompt conditions such as urgency, authority pressure, and multi-turn confusion?

---

## 4. Methodology

### 4.1 Models
- Llama 3.1 8B
- Qwen2.5 7B
- Mistral 7B Instruct

### Justification
- Open-source
- Widely used
- Different model families
- Feasible to compare consistently

### 4.2 Benchmark design
Total benchmark:
- 300 prompts
- 900 outputs

Breakdown:
- Task A: Detection = 100 prompts
- Task B: Recovery = 60 prompts
- Task C: Fairness = 80 prompts
- Task D: Robustness = 60 prompts

### 4.3 Task descriptions

#### Task A — Detection
- phishing vs legitimate messages
- goal: classify correctly and explain risk

#### Task B — Recovery
- post-click, password entry, OTP sharing, attachment opening, reply with personal data, unsure-before-acting cases
- goal: assess whether the model gives safe next steps

#### Task C — Fairness
- same scenario, persona changes only
- dimensions: age, digital confidence, anxiety, prior scam experience
- goal: measure whether advice quality changes unfairly

#### Task D — Robustness
- clean vs manipulated prompts
- manipulations: urgency + typos, authority pressure, multi-turn confusion
- goal: test whether advice degrades under pressure/noise

### 4.4 Structured output format
All models should be prompted to produce a structured answer.

Planned fields:
- risk_label
- warning_level
- stop_engagement
- verify_official_channel
- remediation_steps
- report_or_escalate
- supportive_tone
- brief_explanation

### 4.5 Evaluation metrics

#### Detection metrics
- Accuracy
- Precision
- Recall
- F1
- False negative rate

#### Protective Quality Score (PQS) — 0 to 6
Give 1 point for each:
1. Correct risk judgment
2. Warns and tells user to stop engagement
3. Advises independent verification through official channels
4. Gives appropriate remediation steps
5. Advises reporting/escalation/monitoring where relevant
6. Uses safe, supportive, non-blaming advice

#### Fairness metrics
- PQS gap across matched persona prompts
- harmful omission gap

#### Robustness metrics
- PQS drop between clean and manipulated prompts
- detection performance drop where relevant

### 4.6 Error analysis categories
- false reassurance
- over-warning
- vague advice
- missing remediation step
- unsafe advice
- privacy/security omission
- victim-blaming or dismissive tone
- inconsistency across similar cases

---

## 5. Results

### 5.1 Detection performance
Planned outputs:
- table of accuracy, precision, recall, F1, false negative rate by model
- one figure showing detection performance

### 5.2 Protective quality results
Planned outputs:
- table of average PQS by model
- discussion of which models gave the safest advice overall

### 5.3 Fairness results
Planned outputs:
- table of PQS gaps across persona dimensions
- discussion of whether the same scenario produced lower-quality support for some personas

### 5.4 Robustness results
Planned outputs:
- table of clean vs manipulated performance
- discussion of which manipulation types caused the biggest degradation

---

## 6. Error Analysis and Discussion

### 6.1 Main failure patterns
Discuss:
- which models falsely reassured users
- which models missed key remediation steps
- which models changed advice quality across personas
- which manipulation type caused the most damage

### 6.2 Why accuracy alone is not enough
Key argument:
- a model can identify phishing correctly and still fail to protect the user if it omits essential next steps

### 6.3 Practical implications
Potential deployment settings:
- university IT support assistants
- customer-support scam triage tools
- digital safety assistants

### 6.4 Reproducibility
Mention:
- fixed models
- fixed prompt structure
- saved outputs
- defined scoring rubric
- clear experimental organisation

---

## 7. Limitations and Future Work
Include:
- simulated prompts, not real-user deployment
- persona prompts are controlled evaluation probes only
- some scoring remains partly subjective
- English-only scope
- only 3 models
- future work could include human evaluation and broader multilingual testing

---

## 8. Conclusion
One short concluding section:
- restate study purpose
- restate main contribution
- final takeaway: trustworthiness in phishing-support settings requires more than correct classification

---

## Planned Tables
- Table 1: Model overview
- Table 2: Benchmark composition
- Table 3: PQS rubric
- Table 4: Detection metrics by model
- Table 5: Average PQS by model
- Table 6: Fairness gaps by persona condition
- Table 7: Robustness degradation by manipulation type

## Planned Figures
- Figure 1: Detection performance by model
- Figure 2: Average PQS by model
- Figure 3: Robustness degradation by condition
