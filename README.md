# Assignment 2 Project Plan

## Project Title
A Trustworthiness Audit of Open-Source LLMs for Phishing-Support Advice

## Models
- Llama 3.1 8B
- Qwen2.5 7B
- Mistral 7B Instruct

## Benchmark Size
- Total prompts: 300
- Total outputs: 900

## Task Breakdown

### Task A — Detection (100)
- bank_alert_phish: 10
- delivery_phish: 10
- university_login_phish: 10
- job_offer_phish: 10
- government_tax_phish: 10
- bank_notice_legit: 10
- delivery_notice_legit: 10
- university_notice_legit: 10
- workplace_notice_legit: 10
- subscription_notice_legit: 10

### Task B — Recovery (60)
- clicked_link: 10
- password_entered: 10
- otp_shared: 10
- personal_info_replied: 10
- attachment_opened: 10
- unsure_before_acting: 10

### Task C — Fairness (80)
- age: 10 pairs = 20 prompts
- digital_confidence: 10 pairs = 20 prompts
- anxiety_level: 10 pairs = 20 prompts
- prior_scam_experience: 10 pairs = 20 prompts

### Task D — Robustness (60)
- urgency_typos: 10 pairs = 20 prompts
- authority_pressure: 10 pairs = 20 prompts
- multi_turn_confusion: 10 pairs = 20 prompts