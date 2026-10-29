# Worked Example: Acme Analytics Ltd (fictional)

A complete, fictional walk-through of GRC OS in action. **Acme Analytics** is a 45-person UK SaaS company selling customer analytics to retailers. It has three pressures at once:

1. 🛒 A grocery retailer wants **Cyber Essentials Plus** by January, or a ~£400k renewal is at risk.
2. 👗 A fashion retailer prospect wants **ISO 27001**.
3. 🤖 Its new AI "Insights Assistant" sends data to a third-party LLM, which needs a **GDPR DPIA** and an **ISO 42001-style AI impact assessment**.

Its CTO is an **accidental owner**: smart and technical, but new to compliance.

## The journey

| Step | Skill | Output |
|---|---|---|
| 1 | `/company-context` | [`grc/context/company-profile.md`](grc/context/company-profile.md): drivers, data, stack, AI use, framework priorities |
| 2 | `/risk-register` | [`grc/risks/risk-register.csv`](grc/risks/risk-register.csv): 12 scenario-based risks, scored, treated and mapped to ISO 27001 / CE / GDPR / ISO 42001 |
| 3 | `/audit-readiness` | [`grc/audits/readiness-iso27001-2026-10-29.md`](grc/audits/readiness-iso27001-2026-10-29.md): 21% ready, a realistic path to Stage 2 in September 2027 |
| — | (every skill) | [`grc/runs/`](grc/runs/): the AI audit trail |

Next steps in the journey (try them yourself): `/cyber-essentials-scoping` → `/dpia` for the Insights Assistant → `/policy-writer` → `/evidence-request-list` → `/grc-status`.

## Things to notice
- **Specific, not generic.** Risks name Acme's real tools (Google Workspace 2SV, Jamf, Terraform, the Insights Assistant), not "malware" or "hackers".
- **Build once, comply many.** Each risk treatment carries `framework_refs`. Enforcing MFA closes an ISO 27001 gap *and* a Cyber Essentials hard fail.
- **Human in the loop.** `approved_by` and `approved_on` are blank everywhere. R-012 sits in "Pending acceptance" until the CEO decides.
- **Honest unknowns.** Open questions are listed as `TBC` rather than invented.

> Everything here is fictional. Don't copy it into your own `grc/` folder. Run `/company-context` to start your own programme.
