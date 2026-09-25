# Challenge 02 — BOLA API Vulnerability Assessment & Board Risk Report

**Program:** CYBR Z Survivor International Cohort | CyberDistro  
**Challenge:** #02 — "You Are Logged In. But Are You Allowed?"  
**Analyst:** Mohammad Zahir | (ISC)² CC  
**Target:** Apex Retail UK (fictional scenario)

---

## Scenario

Apex Retail UK's e-commerce platform passed authentication but failed authorization. Task: confirm whether a logged-in user could access another user's basket — then present findings to the board with financial exposure, regulatory framing, and a remediation business case.

---

## Vulnerability Identified

| Field | Detail |
|---|---|
| **Vulnerability** | Broken Object Level Authorization (BOLA) |
| **OWASP** | API1:2023 |
| **Endpoint** | `GET /rest/basket/:id` |
| **Root Cause** | Server validates token exists — never checks token holder owns the resource |
| **Severity** | Critical — active, reproducible, cross-account data access |

---

## Technical Evidence

| Step | Who | Action | Result |
|---|---|---|---|
| E02 Baseline | user_a@apex.local | Requests own basket (ID 9) | Granted — expected |
| E03 Attack | user_b@apex.local | Requests user_a's basket (ID 9) | Full access — UserId: 31, all items exposed |

**Root cause confirmed:** Any authenticated user can request any basket ID and receive full data. Front-end hiding is not a fix — the endpoint remains unprotected regardless of what the UI shows.

---

## Blast Radius

| Metric | Value |
|---|---|
| Customer accounts at risk | 180,000 |
| Annual orders in exposure boundary | 250,000 |
| Data exposed | Name, email, postal address, order history, invoice metadata, customer identifiers |
| Data NOT stored | Card numbers · plaintext passwords · national identity numbers |

**Unknown:** Whether historical unauthorized access occurred outside this test, full scope of affected endpoints, and whether data left the organisation.

---

## Financial Exposure & ROSI

| Metric | Value |
|---|---|
| Single Breach Exposure | £900,000 |
| Expected Annual Loss (pre-remediation) | £225,000 |
| Year-1 Investment | £60,000 |
| Residual Risk after remediation | £27,000 |
| Net Risk Reduction | £198,000 |
| **Year-1 ROSI** | **230%** |

> Every £1 invested avoids £2.30 in expected loss. Investment is justified.

*Fictional challenge assumptions — not industry benchmarks.*

---

## Regulatory Assessment — UK GDPR

| Determination | Status |
|---|---|
| Vulnerability confirmed | ✅ Yes — E03 proves server-side authorization failure |
| Personal data breach confirmed | ❌ No — requires further investigation |
| ICO 72-hour notification clock | Does not start on vulnerability alone |
| Maximum penalty ceiling | £17.5m or 4% of £52m turnover (£2.08m) |

> A confirmed vulnerability and a confirmed personal-data breach are distinct legal determinations. They cannot be conflated without evidence.

---

## Remediation

**Primary Control — Server-Side Ownership Check**
IF authenticated_user_id != basket.user_id → return HTTP 403 Forbidden

Must be implemented server-side. Cannot be delegated to the client.

**Validation Test — Mandatory in Every Deployment Pipeline**
user_a@apex.local → GET /rest/basket/9 → ALLOW (owns resource)
user_b@apex.local → GET /rest/basket/9 → DENY (HTTP 403)

**Defence-in-Depth**

| Layer | Control |
|---|---|
| Enumeration reduction | Non-sequential basket IDs (UUIDs) |
| Abuse throttling | Rate limiting on resource endpoints |
| Detection | Anomaly alerts on cross-account access patterns |

---

## Board Ask

- Approve **£60,000** Year-1 remediation programme
- Mandate server-side authorization regression testing on every deployment
- Initiate UK GDPR notification assessment
- Schedule annual access-control review

---

## Skills Demonstrated

`BOLA / IDOR Analysis` · `API Security Testing` · `OWASP API Top 10`  
`ROSI Calculation` · `UK GDPR Regulatory Framing`  
`Board-Level Risk Communication` · `Evidence-Based Remediation Design`

---

## Project Artifacts

| File | Description |
|------|-------------|
| [CYBRZ C02 Board Deck](./CYBRZ_C02_Kakar_Zahir_BoardDeck.pdf) | Original board deck submitted to CYBR Z Survivor panel |

---

> **CYBR Z Survivor Cohort** — 1 of ~35 selected globally from 600+ applicants | Powered by CyberDistro
