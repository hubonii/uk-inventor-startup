# 18-Month Hiring Plan — Local-Logistics Protocol

> Last updated: July 2026 | Budget Basis: £750k Seed Round

---

## Executive Summary

The hiring plan adds **6 roles** over 18 months, growing the team from **1 founder** to **7 people** by Month 18. Total headcount cost over the period is approximately **£392,000**. Every hire is justified by a specific milestone trigger — no hire is made speculatively. Engineering talent accounts for 65% of headcount cost, reflecting our product-led growth strategy.

---

## Hiring Timeline Overview

```
Month:  1    2    3    4    5    6    7    8    9   10   11   12   13   14   15   16   17   18
        │    │    │    │    │    │    │    │    │    │    │    │    │    │    │    │    │    │
Founder ████████████████████████████████████████████████████████████████████████████████████
FS Eng 1     ███████████████████████████████████████████████████████████████████████████████
FS Eng 2          ████████████████████████████████████████████████████████████████████████
B2B Sales              ██████████████████████████████████████████████████████████████████████
Mobile Eng                             ████████████████████████████████████████████████████
Community Mgr                                        ██████████████████████████████████████
CTO                                                                 ███████████████████████
                                                                     
Team Size: 1    2    3    3    4    4    4    5    5    5    5    5    6    6    6    7    7    7
```

---

## Role Details

### Role 1: Founder / CEO & Acting CTO

| Attribute | Detail |
|---|---|
| **Start** | Month 0 (pre-seed) |
| **Salary** | £4,000/mo draw → £6,000/mo from M7 → £8,000/mo from M13 |
| **Total Cost (18 mo)** | £108,000 |
| **Equity** | 100% at founding → diluted per investment rounds |
| **Justification** | Founder wears CTO hat until dedicated CTO hire at M13. Below-market salary preserves runway. |
| **Key Responsibilities** | Architecture decisions, investor relations, product direction, initial code, hiring |

---

### Role 2: Full-Stack Engineer #1

| Attribute | Detail |
|---|---|
| **Start** | Month 2 |
| **Salary Band** | £55,000 – £70,000/year (£4,583 – £5,833/mo) |
| **Target Salary** | £65,000/year (£5,417/mo) |
| **Total Cost (16 mo)** | £86,672 |
| **Equity** | 1.0 – 1.5% (4-year vest, 1-year cliff) |
| **Justification** | Required for MVP development velocity. Founder cannot ship API + frontend + mobile alone. First hire must be a generalist who can work across the stack. |
| **Key Skills** | Node.js/TypeScript, React, PostgreSQL, REST APIs, basic DevOps |
| **Hiring Trigger** | Seed round closed |
| **Milestone Owned** | API v1 deployed, Sender web app functional |

---

### Role 3: Full-Stack Engineer #2

| Attribute | Detail |
|---|---|
| **Start** | Month 3 |
| **Salary Band** | £50,000 – £65,000/year (£4,167 – £5,417/mo) |
| **Target Salary** | £58,000/year (£4,833/mo) |
| **Total Cost (15 mo)** | £72,495 |
| **Equity** | 0.75 – 1.0% (4-year vest, 1-year cliff) |
| **Justification** | TOTP handshake protocol and payment/staking system require dedicated development capacity. Cannot be built in parallel by one engineer. |
| **Key Skills** | Security-focused development, Stripe API, cryptographic protocols, React Native exposure |
| **Hiring Trigger** | API v1 architecture defined; database schema finalized |
| **Milestone Owned** | TOTP handshake system, Stripe payment integration, staking escrow |

---

### Role 4: B2B Sales Lead

| Attribute | Detail |
|---|---|
| **Start** | Month 4 |
| **Salary Band** | £35,000 – £50,000/year base + commission (£2,917 – £4,167/mo) |
| **Target Salary** | £42,000/year base (£3,500/mo) + £500/mo commission target |
| **Total Cost (14 mo)** | £56,000 (base + commission) |
| **Equity** | 0.25 – 0.5% (4-year vest, 1-year cliff) |
| **Justification** | Founder cannot do door-to-door merchant sales while managing engineering. Dedicated field sales needed to hit 20 merchants by M9. The UCL/Bloomsbury wedge has ~200 eligible merchants within walking distance. |
| **Key Skills** | B2B field sales experience, retail/hospitality sector knowledge, CRM management, London commercial knowledge |
| **Hiring Trigger** | MVP functional with at least 5 completed deliveries |
| **Milestone Owned** | 20 B2B merchants signed by M9, merchant onboarding process |
| **Commission Structure** | £200 per new merchant signed + £50/quarter retention bonus per active merchant |

---

### Role 5: Mobile Engineer

| Attribute | Detail |
|---|---|
| **Start** | Month 6 |
| **Salary Band** | £55,000 – £75,000/year (£4,583 – £6,250/mo) |
| **Target Salary** | £62,000/year (£5,167/mo) |
| **Total Cost (12 mo)** | £62,004 |
| **Equity** | 0.75 – 1.0% (4-year vest, 1-year cliff) |
| **Justification** | Courier app (React Native) needs dedicated mobile expertise for GPS tracking, push notifications, camera (QR scanning), and offline capability. Web-first MVP works for senders/merchants but couriers need a native-quality mobile experience. |
| **Key Skills** | React Native (strong), iOS/Android native (exposure), GPS/location services, camera APIs, push notifications, offline-first architecture |
| **Hiring Trigger** | 100+ active couriers; clear mobile app requirements validated by courier feedback |
| **Milestone Owned** | Courier mobile app v2 (native-quality), QR scanner optimization, GPS tracking |

---

### Role 6: Community Manager

| Attribute | Detail |
|---|---|
| **Start** | Month 9 |
| **Salary Band** | £28,000 – £38,000/year (£2,333 – £3,167/mo) |
| **Target Salary** | £32,000/year (£2,667/mo) |
| **Total Cost (9 mo)** | £24,003 |
| **Equity** | 0.1 – 0.25% (4-year vest, 1-year cliff) |
| **Justification** | At 100+ couriers, community management becomes critical for retention. Courier WhatsApp groups, event coordination, feedback loops, and social media require dedicated attention. This role directly impacts the 12% monthly churn target. |
| **Key Skills** | Community building, social media management, event coordination, basic data analysis, empathy and conflict resolution |
| **Hiring Trigger** | Courier base exceeds 100; churn rate data available for 3+ months |
| **Milestone Owned** | Courier retention improvement (target: reduce churn from 12% to 8%), courier NPS >40 |

---

### Role 7: CTO (Dedicated)

| Attribute | Detail |
|---|---|
| **Start** | Month 13 |
| **Salary Band** | £90,000 – £120,000/year (£7,500 – £10,000/mo) |
| **Target Salary** | £100,000/year (£8,333/mo) |
| **Total Cost (5 mo in 18-mo plan)** | £41,665 |
| **Equity** | 3 – 5% (4-year vest, 1-year cliff) |
| **Justification** | By M13, the engineering team is 4 people and the system handles thousands of daily transactions. The founder needs to shift fully to CEO duties (fundraising Series A, strategic partnerships, expansion planning). A dedicated CTO brings architectural maturity, security leadership, and engineering management. |
| **Key Skills** | 8+ years engineering leadership, distributed systems, security architecture, team management (5-15 engineers), fintech/marketplace experience, Series A-stage scaling |
| **Hiring Trigger** | Series A fundraising initiated; engineering team at 4+; founder time split >50% on non-technical |
| **Milestone Owned** | System architecture for multi-city, 99.9% uptime SLA, engineering culture and processes |

---

## Salary Summary Table

| Role | Start Month | Monthly Cost | Annual Equivalent | Equity % | 18-Mo Total |
|---|---|---|---|---|---|
| Founder (CEO) | M0 | £4k → £6k → £8k | £48k → £72k → £96k | Founder | £108,000 |
| Full-Stack Engineer #1 | M2 | £5,417 | £65,000 | 1.0-1.5% | £86,672 |
| Full-Stack Engineer #2 | M3 | £4,833 | £58,000 | 0.75-1.0% | £72,495 |
| B2B Sales Lead | M4 | £4,000 (inc. commission) | £48,000 OTE | 0.25-0.5% | £56,000 |
| Mobile Engineer | M6 | £5,167 | £62,000 | 0.75-1.0% | £62,004 |
| Community Manager | M9 | £2,667 | £32,000 | 0.1-0.25% | £24,003 |
| CTO | M13 | £8,333 | £100,000 | 3-5% | £41,665 |
| **Total** | — | — | — | **~7%** | **£450,839** |

---

## Employer Cost Add-Ons

| Cost | Rate | Notes |
|---|---|---|
| Employer NI | 13.8% above £9,100 threshold | Applied to all employees |
| Pension (auto-enrolment) | 3% of qualifying earnings | Statutory minimum |
| Equipment (laptop + monitor) | £1,500 one-time per hire | MacBook Pro + external monitor |
| Recruitment costs | £3,000 avg per hire | Mix of job boards, referrals, LinkedIn |
| **Employer cost multiplier** | **~1.18x** | Applied to base salary |

### Total Loaded Headcount Cost (18 months)

| Component | Amount |
|---|---|
| Base salaries (18 mo) | £450,839 |
| Employer NI + pension (~18%) | £81,151 |
| Equipment (6 hires × £1,500) | £9,000 |
| Recruitment (6 hires × £3,000) | £18,000 |
| **Total loaded headcount cost** | **£558,990** |

> Headcount represents **~74.5%** of the £750k seed — appropriate for a product-led, engineering-heavy startup.

---

## Monthly Headcount Cost Ramp

| Month | Headcount | Monthly Salary Cost | Loaded Cost (×1.18) |
|---|---|---|---|
| M1 | 1 | £4,000 | £4,720 |
| M2 | 2 | £9,417 | £11,112 |
| M3 | 3 | £14,250 | £16,815 |
| M4 | 4 | £18,250 | £21,535 |
| M5 | 4 | £18,250 | £21,535 |
| M6 | 5 | £23,417 | £27,632 |
| M7-8 | 5 | £25,417 | £29,992 |
| M9-12 | 6 | £28,084 | £33,139 |
| M13-18 | 7 | £36,417 | £42,972 |

---

## Equity Option Pool

| Allocation | Percentage |
|---|---|
| Founder | ~85% (post-seed dilution) |
| Seed investors | ~15% (estimated for £750k at £5M pre-money) |
| Employee option pool | 10% (carved from founder) |
| Allocated to hires (18 mo plan) | ~7% |
| Reserved for future hires | ~3% |

> **Vesting:** All employee equity on 4-year vesting with 1-year cliff. Monthly vesting after cliff. Single-trigger acceleration on acquisition for key hires (CTO).

---

## Hiring Principles

1. **Milestone-triggered hiring** — No hire is made until a specific metric or milestone justifies it
2. **Generalists first, specialists later** — Early hires must wear multiple hats
3. **London-based or hybrid** — All roles require 3+ days/week in-person for early-stage velocity
4. **Equity-heavy compensation** — Below-market salaries offset with meaningful equity
5. **No premature management layers** — Founder manages directly until team exceeds 8
6. **Contractor bridge** — Use contractors for 2-4 week spikes (design, security audit) rather than hiring

---

## Roles NOT Hired in 18 Months (Deferred to Series A)

| Role | Reason for Deferral | Expected Hire |
|---|---|---|
| VP Engineering | CTO handles this initially | M20-24 |
| Product Manager | Founder acts as PM through Series A | M18-20 |
| Data Scientist | Analytics dashboard + manual analysis sufficient | M20-24 |
| Finance / Ops Manager | Outsourced to accountancy firm | M18-24 |
| Customer Success Manager | Community Manager covers initial needs | M20 |
| Additional Engineers (3-5) | Post-Series A scaling | M18-24 |
| Head of Marketing | Growth handled by founder + community manager | M20 |

---

*Hiring plan reviewed quarterly. Salary benchmarks sourced from levels.fyi, Glassdoor UK, and Otta for London-based startup roles (Seed to Series A stage).*
