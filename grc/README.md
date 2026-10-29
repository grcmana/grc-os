# grc/ — your programme data

This folder holds your organisation's GRC data: company context, risks, policies, evidence, audits and AI run logs. Everything in here **except this README and the empty folders is git-ignored**, so it won't be pushed to the public GRC OS repo.

To version it, make it its own **private** repository:

```bash
git init && git remote add origin <your-private-repo-url>
```

| Folder | Contents |
|---|---|
| `context/` | `company-profile.md`, `scope.md` |
| `risks/` | `risk-register.csv`, `treatment-plan.md`, AI inventory and impact assessments |
| `policies/` | Policy drafts, policy plan, gap reviews |
| `evidence/` | `evidence-tracker.csv`, request lists, evidence reviews |
| `audits/` | Readiness reports, CE scope, DPIAs, management reviews |
| `runs/` | Log of every AI-assisted skill run (your AI audit trail) |
