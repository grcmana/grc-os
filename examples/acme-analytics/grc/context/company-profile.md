---
document: Company GRC Profile
version: 0.1
owner: CTO
last_reviewed: 2026-10-29
next_review: 2027-04-29
user_experience: accidental-owner
language: en-GB
approved_by:
approved_on:
---

# Company GRC Profile — Acme Analytics Ltd (FICTIONAL EXAMPLE)

> This is a fictional company used to demonstrate GRC OS. Any resemblance to a real organisation is coincidental.

## 1. Business
| Field | Value |
|---|---|
| Legal entity | Acme Analytics Ltd (England & Wales) |
| What we sell | SaaS customer-analytics platform for mid-market UK retailers (loyalty, basket and churn insights) |
| Business model | B2B SaaS, annual contracts |
| Customers | ~60 UK retailers; first EU prospects |
| Stage / funding | Series A (2026) |
| Headcount | 45 employees + 6 contractors |
| Locations / remote model | London office (Shoreditch) + remote-first UK staff |

## 2. GRC drivers
| Driver | Who's asking | Requirement | Deadline | Impact if missed |
|---|---|---|---|---|
| Supply-chain requirement | Large UK grocery retailer (renewal) | Cyber Essentials Plus | 2027-01-31 | ~£400k ARR renewal at risk |
| Enterprise prospect | National fashion retailer | ISO 27001 certificate (or credible roadmap) | Certificate by 2027-09 | Lost new logo (~£250k ARR) |
| Law | n/a | UK GDPR (processor for retailers' customer data; controller for own staff/marketing) | Ongoing | Regulatory and contractual exposure |
| Board | Series A investors | Security & AI governance reporting | Quarterly | Investor confidence |

## 3. Data
| Data type | Data subjects | Volume | Where stored | Our role |
|---|---|---|---|---|
| Retail loyalty & transaction data (pseudonymised IDs, purchase history, postcode district, email for some customers) | Retailers' customers | ~18m records | AWS eu-west-2 (London) | Processor |
| Customer account users | Retailer staff | ~900 users | AWS eu-west-2 | Controller (account data) |
| Employee / contractor data | Staff | 51 | HiBob, Google Workspace | Controller |
| Marketing contacts | Prospects | ~4k | HubSpot | Controller |

Special category data: none intended. **TBC**: confirm that retailers don't upload health-related purchase categories (e.g. pharmacy).
International transfers: LLM API provider (US) for the Insights Assistant. Transfer mechanism **TBC**.

## 4. Technology
| Area | Tooling |
|---|---|
| Cloud / hosting | AWS (eu-west-2), Terraform |
| Identity / SSO | Google Workspace (2SV optional); AWS IAM Identity Center |
| Email & collaboration | Google Workspace, Slack |
| Code & CI/CD | GitHub, GitHub Actions |
| Ticketing | Jira |
| HRIS | HiBob |
| Endpoints | 51 MacBooks (company-owned, ~80% in Jamf); BYOD mobiles for email and Slack |
| Security tooling | AWS GuardDuty; no EDR; no centralised logging beyond CloudWatch |
| Critical suppliers | AWS, Google, LLM API provider, GitHub, HubSpot, HiBob |

## 5. AI
| Question | Answer |
|---|---|
| AI in the product? | Yes: the "Insights Assistant" uses a third-party LLM API to answer natural-language questions over retailer analytics |
| AI tools used by staff | Claude Team (company); some personal use of other public tools (unmanaged) |
| AI use policy in place? | No |

## 6. People & governance
| Role | Owner |
|---|---|
| Executive sponsor | CEO |
| Security owner | CTO (delegated day-to-day to Head of Engineering) |
| Privacy owner / DPO | COO (no formal DPO; **TBC** whether one is required) |
| IT | IT Lead (1 FTE) |

Existing certifications: none. Existing policies: Employee Handbook, an informal security page in Notion.

## 7. Constraints
| Constraint | Value |
|---|---|
| Budget band | £30–50k for year 1 (incl. certification) |
| Internal capacity | Head of Engineering ~1 day/week; IT Lead ~40% |
| Target dates | CE+ by 2027-01-31; ISO 27001 Stage 2 by 2027-09 |

## 8. Framework selection
| Framework | Status | Priority | Rationale |
|---|---|---|---|
| Cyber Essentials Plus | not-started | **P1** | Hard renewal requirement; fast baseline that also feeds ISO 27001 |
| ISO 27001 | not-started | **P2** | Enterprise prospect plus UK/EU market default; build on CE work |
| GDPR | applies | **P1** | Processor obligations, and the Insights Assistant needs a DPIA |
| SOC 2 | n/a (for now) | — | No US customers yet; revisit if US expansion is planned |
| ISO 42001 | not-started | P3 | Run ISO 42001-style AI impact assessments now; consider certification after ISO 27001 |

## 9. Open questions
- Does any retailer upload health-related purchase categories? (affects special category data and the DPIA)
- Transfer mechanism for the US LLM provider (UK IDTA / Addendum?)
- Is a DPO required? (likely not, but document the reasoning)
