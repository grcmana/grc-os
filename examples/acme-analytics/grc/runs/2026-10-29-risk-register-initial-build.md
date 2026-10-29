---
skill: risk-register
date: 2026-10-29
mode: build
inputs: [grc/context/company-profile.md]
outputs: [grc/risks/risk-register.csv]
decisions_pending:
  - "Owners to confirm scores for R-001 to R-012"
  - "CEO to approve or reject acceptance of R-012 (Retain, residual 9 > appetite 7)"
  - "CEO to approve risk methodology (default 5x5, appetite ≤7)"
---
## Summary
Built the initial risk register for Acme Analytics from the company profile. 19 candidate scenarios were proposed. The CTO removed 5 and merged 2, leaving 12 confirmed risks: 1 High and 11 Medium (residual). The top risk is account takeover via phishing (R-001, residual 15), driven by optional MFA. The highest inherent AI risk is R-008: personal data reaching the third-party LLM through the Insights Assistant. It's linked to a DPIA and an AI impact assessment.

## Open questions
- Do retailers upload health-related purchase categories? This affects R-008 severity and the DPIA.
- What is the transfer mechanism for the US LLM provider?
