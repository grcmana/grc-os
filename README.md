# GRC OS

**An open-source AI operating system for GRC practitioners, built on Claude Code.**
By [GRCMANA](https://grcmana.com) · powered by [GRC Skills](https://github.com/grcmana/grcskills) · MIT licensed · v0.1.0

GRC OS turns Claude Code into a GRC pair-worker. Clone it, open it in Claude Code, and run a real compliance programme from your terminal:
- build your company context
- maintain a risk register
- draft and gap-check policies
- assess readiness
- run evidence collection

It covers **ISO 27001, SOC 2, Cyber Essentials, GDPR and ISO 42001**.

It's built for two kinds of people:
- **GRC engineers** who want to automate repetitive programme work and keep it all as code.
- **"Accidental" owners**: the founder, CTO or ops lead who has just been told "the customer needs SOC 2 / ISO 27001 / Cyber Essentials".

> ⚠️ GRC OS produces **drafts for review by a competent person**. It doesn't certify compliance, give legal advice or replace an auditor. See [Disclaimer](#disclaimer).

## GRC OS vs GRC Skills

| | [GRC Skills](https://github.com/grcmana/grcskills) | **GRC OS** (this repo) |
|---|---|---|
| What | A library of portable skills | A ready-to-run workspace |
| Install | `npx skills add grcmana/grcskills` into any project | `git clone` and open in Claude Code |
| Includes | Skills + framework knowledge | All skills **plus** operating instructions, guardrails, permission defaults, a private `grc/` workspace and a worked example |
| Best for | Adding GRC capability to an existing agent setup | Running your GRC programme end to end |

## Quick start (about 15 minutes to first value)

**You need:** [Claude Code](https://docs.claude.com/en/docs/claude-code/overview) installed and signed in, plus `git`.

```bash
git clone https://github.com/grcmana/grc-os.git
cd grc-os
claude
```

Then say **"hi"**. GRC OS will offer to start your programme or show you the worked example. Or go straight to:

```
/company-context
```

Answer a few batches of questions, or point Claude at your website and existing docs. You'll get a company profile, a draft scope and a recommended framework set in `grc/context/`. Then:

```
/risk-register           # your first risk register
/policy-writer           # the policy set you actually need
/audit-readiness         # how far you are from audit, and the roadmap
/evidence-request-list   # what to collect, from where, by whom
/grc-status              # one-page status for leadership
```

## See it working first

[`examples/acme-analytics/`](examples/acme-analytics/) is a complete worked example of a fictional 45-person UK SaaS company that needs Cyber Essentials, ISO 27001 and GDPR. It includes a company profile, risk register, readiness report and run log.

## What's inside

```
grc-os/
├── CLAUDE.md                  # Operating instructions + guardrails Claude follows
├── .claude/
│   ├── settings.json          # Conservative permission defaults
│   └── skills/                # GRC Skills (from grcmana/grcskills)
├── grc/                       # YOUR programme data. Git-ignored by default
│   ├── context/  risks/  policies/  evidence/  audits/  runs/
└── examples/acme-analytics/   # Worked example (fictional)
```

## Design principles

1. **Context first.** Every workflow reads your company profile. Generic GRC is useless GRC.
2. **Human in the loop.** Claude proposes and humans approve. Approval fields are never auto-filled.
3. **Everything is a file.** Markdown and CSV in a folder you control, so it diffs, versions, and imports into any GRC platform later.
4. **Private by default.** `grc/` is git-ignored, so your risk register doesn't land on GitHub by accident.
5. **Auditable AI.** Every skill run writes a log to `grc/runs/`. You can show your auditor exactly how AI was used, which is useful evidence for ISO 42001.
6. **Version-aware.** Framework knowledge carries an `as_of` date, and Claude flags anything that may have moved on.

## Keeping your programme in version control (recommended)

`grc/` is ignored so the public repo stays clean. To version your own programme, keep it in a **private** repo:

```bash
cd grc && git init && git remote add origin <your-private-repo-url>
```

## Updating skills

```bash
npx skills add grcmana/grcskills   # choose Claude Code and project scope when prompted
```

Or `git pull` this repo to get the latest bundled skills and operating instructions.

## Roadmap

- **v0.2:** asset inventory, supplier risk, incident response, Statement of Applicability, security questionnaires
- **v0.3:** evidence automation via MCP connectors (identity, cloud, ticketing, MDM)
- **Later:** NIS2, DORA and EU AI Act packs, continuous control monitoring, board reporting

Ideas and requests are welcome in [Issues](../../issues). Skill contributions go to [grcmana/grcskills](https://github.com/grcmana/grcskills).

## Disclaimer

Provided "as is" under the MIT licence. GRC OS is **not** legal, regulatory or audit advice and does not certify compliance. AI output can be wrong, so all outputs must be reviewed by a competent person. Framework summaries reflect our understanding as of each pack's `as_of` date, so check official sources. ISO/IEC standards are © ISO/IEC, the SOC 2 Trust Services Criteria are © AICPA, and Cyber Essentials is a UK Government scheme delivered by IASME for the NCSC. Not affiliated with or endorsed by any of these bodies, or by Anthropic.

---

Built by **Harry West** ([GRCMANA](https://grcmana.com)): ~20 years in cyber, former Global CISO, ISO 27001 / 42001 / 9001 and Cyber Essentials certified.
⭐ Star the repo if it saves you time. Browse more skills at **[grcskills.io](https://grcskills.io)**.
