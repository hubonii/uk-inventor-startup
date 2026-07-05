# Willingness to Pay Analysis

## Local-Logistics Protocol — Price Sensitivity & Revenue Optimisation

> **Last Updated:** July 2026
> **Status:** Framework Ready — Awaiting interview data inputs
> **Methods:** Van Westendorp Price Sensitivity Meter, Conjoint Analysis, Price Ladder Experiments

---

## 1. Van Westendorp Price Sensitivity Meter (PSM)

### Methodology

The Van Westendorp PSM identifies the acceptable price range by asking four questions:

1. **Too Cheap:** At what price would you consider the delivery so cheap that you'd question its quality/safety?
2. **Bargain:** At what price would you consider the delivery a bargain — a great deal for the money?
3. **Expensive (but acceptable):** At what price would the delivery start to feel expensive, but you'd still consider paying?
4. **Too Expensive:** At what price would the delivery be too expensive — you'd never consider it?

The intersection of these curves reveals:
- **Point of Marginal Cheapness (PMC):** Below this, quality concerns emerge
- **Point of Marginal Expensiveness (PME):** Above this, too many customers drop off
- **Optimal Price Point (OPP):** Where equal numbers consider it cheap vs. expensive
- **Indifference Price Point (IDP):** Where equal numbers consider it a bargain vs. too expensive

### Application: Per-Drop Pricing (Sender-Side)

#### Segment A: Pharmacies

| Question | Hypothesised Range | Interview Collection Method |
|---|---|---|
| Too Cheap | <£1.50 | "At what price would you think the courier can't be trusted?" |
| Bargain | £2.00 – £3.50 | "At what price is this a no-brainer compared to driving yourself?" |
| Expensive | £5.00 – £6.50 | "At what price does it hurt, but you'd still use it for urgent prescriptions?" |
| Too Expensive | >£7.00 | "At what price would you just drive it yourself every time?" |

**Hypothesised Optimal Range:** £3.50 – £5.50 per drop

**Expected PSM Output:**

```
100% ┌──────────────────────────────────────────┐
     │  Too Cheap ╲           ╱ Too Expensive   │
     │              ╲       ╱                    │
     │                ╲   ╱                      │
 50% │──────────────── ★ ─────────────────────── │
     │               ╱ ╲ ★ = OPP (~£4.25)       │
     │             ╱     ╲                       │
     │  Bargain  ╱         ╲  Expensive          │
  0% └──────────────────────────────────────────┘
     £1    £2    £3    £4    £5    £6    £7    £8
                     PMC   OPP  PME
                    £3.00 £4.25 £5.50
```

#### Segment B: Hardware/Print Shops

| Question | Hypothesised Range |
|---|---|
| Too Cheap | <£2.00 |
| Bargain | £3.00 – £4.50 |
| Expensive | £5.50 – £7.00 |
| Too Expensive | >£8.00 |

**Hypothesised Optimal Range:** £4.00 – £7.00 per drop (higher item values justify higher delivery fees)

#### Segment C: C2C Resellers

| Question | Hypothesised Range |
|---|---|
| Too Cheap | <£1.00 |
| Bargain | £1.50 – £2.50 |
| Expensive | £3.50 – £4.50 |
| Too Expensive | >£5.00 |

**Hypothesised Optimal Range:** £2.50 – £4.00 per drop (must compete with Royal Mail 2nd class at £3.49)

#### Segment D: University Students

| Question | Hypothesised Range |
|---|---|
| Too Cheap | <£0.50 |
| Bargain | £1.00 – £2.00 |
| Expensive | £3.00 – £4.00 |
| Too Expensive | >£4.50 |

**Hypothesised Optimal Range:** £2.00 – £3.50 per drop (extremely price-sensitive)

### Cross-Segment Price Map

```
        Pharmacy    Hardware    C2C        Student
        ┌──────┐   ┌──────┐   ┌──────┐   ┌──────┐
Too $:  │ £7.00│   │ £8.00│   │ £5.00│   │ £4.50│
        │      │   │      │   │      │   │      │
Exp:    │ £5.50│   │ £7.00│   │ £4.00│   │ £3.50│
        │      │   │      │   │      │   │      │
OPP:    │ £4.25│   │ £5.00│   │ £3.00│   │ £2.50│
        │      │   │      │   │      │   │      │
Barg:   │ £3.00│   │ £3.50│   │ £2.00│   │ £1.50│
        │      │   │      │   │      │   │      │
Cheap:  │ £1.50│   │ £2.00│   │ £1.00│   │ £0.50│
        └──────┘   └──────┘   └──────┘   └──────┘

Our target: ───────── £3.50 - £5.50 ─────────────
```

**Key Insight:** Our target range (£3.50-5.50) aligns well with pharmacy and hardware segments but is at the upper end for C2C and over budget for students. This validates pharmacies as our beachhead — they have the highest WTP.

---

## 2. Conjoint Analysis Plan

### Objective
Determine which delivery attributes customers value most and how they trade off between them.

### Attributes & Levels

| Attribute | Level 1 | Level 2 | Level 3 |
|---|---|---|---|
| **Price** | £3.00 | £4.50 | £6.00 |
| **Speed** | Under 30 minutes | 30-60 minutes | 1-2 hours |
| **Trust Mechanism** | Rating system only | Rating + ID verification | Rating + ID + £50 deposit |
| **Tracking** | No tracking | Delivery confirmation only | Real-time GPS tracking |
| **Courier Type** | Any available courier | Verified local resident | Background-checked courier |

### Choice-Based Conjoint (CBC) Design

Present respondents with choice sets of 3 delivery options plus a "none" option:

**Example Choice Set:**

| | Option A | Option B | Option C | None |
|---|---|---|---|---|
| Price | £3.00 | £4.50 | £6.00 | — |
| Speed | 1-2 hours | Under 30 min | 30-60 min | — |
| Trust | Rating only | Rating + ID + £50 deposit | Rating + ID | — |
| Tracking | No tracking | Real-time GPS | Confirmation only | — |
| Courier | Any | Verified local | Background checked | — |
| **I'd choose:** | ☐ | ☐ | ☐ | ☐ I wouldn't use any |

**Design Parameters:**
- 12 choice sets per respondent
- Target sample: 200 respondents (online survey via Prolific, targeting London residents)
- Analysis: Hierarchical Bayes estimation of part-worth utilities
- Tool: Conjointly.com or Lighthouse Studio (Sawtooth Software)
- Cost: £400-600 (survey platform + respondent incentives at £1.50/respondent)

### Expected Outputs

| Attribute | Hypothesised Relative Importance |
|---|---|
| Price | 35% |
| Speed | 25% |
| Trust Mechanism | 20% |
| Tracking | 12% |
| Courier Type | 8% |

**Key Question We Need Answered:** How much more will people pay for the £50 deposit trust mechanism? If the part-worth utility of "Rating + ID + £50 deposit" is significantly higher than "Rating only," this validates our core differentiator.

---

## 3. Price Ladder Experiments

### Experiment 3A: Sender Per-Drop Price Ladder

**Method:** During Concierge MVP and Wizard of Oz phases, vary the price shown to different merchants and measure acceptance rates.

| Price Point | Merchants Shown | Expected Acceptance | What We Learn |
|---|---|---|---|
| £3.00 | 3 merchants (1 week) | ~90% | Floor price — almost everyone accepts |
| £3.50 | 3 merchants (1 week) | ~85% | Near floor — strong acceptance |
| £4.00 | 3 merchants (1 week) | ~75% | Sweet spot candidate |
| £4.50 | 3 merchants (1 week) | ~65% | Still viable? |
| £5.00 | 3 merchants (1 week) | ~55% | Testing ceiling |
| £5.50 | 3 merchants (1 week) | ~45% | At the edge |
| £6.00 | 3 merchants (1 week) | ~30% | Likely too high for routine use |
| £7.00 | 3 merchants (1 week) | ~15% | Only for urgent/high-value |
| £8.00 | 3 merchants (1 week) | ~5% | Uber Connect territory — we've lost our advantage |

**Important:** Rotate prices across merchants and time to avoid confounding. Each merchant sees multiple price points across the test period.

**Measurement:**
- Acceptance rate (% of shown prices that result in a delivery request)
- Request volume at each price (do merchants request more deliveries at lower prices?)
- Qualitative feedback ("I'd use this all the time at £3" vs. "£5 is fine for urgent prescriptions but I'd drive myself for routine ones")

### Experiment 3B: B2B SaaS Subscription Price Ladder

**Method:** During B2B pre-sale conversations, vary the subscription price offered.

| Price Point | Includes | Target Segment | Expected Close Rate |
|---|---|---|---|
| £29/mo ("Founder's Rate") | Dashboard, weekly invoicing, 24/7 support, CQC audit logs | Pharmacies (early adopters) | ~40% |
| £39/mo ("Starter") | Dashboard, weekly invoicing, email support | Hardware/print shops | ~30% |
| £49/mo ("Professional") | Full dashboard, weekly invoicing, priority support, CQC audit logs, analytics | Pharmacies (post-launch) | ~25% |
| £69/mo ("Growth") | All Professional + API integration, custom branding, dedicated account manager | Multi-location pharmacies | ~15% |
| £99/mo ("Enterprise") | All Growth + SLA guarantees, compliance reporting, volume discounts on drops | Pharmacy groups (3+ locations) | ~10% |

**Key Decision:** Should subscription include a per-drop credit bundle? E.g., £49/mo includes 30 free drops (£1.63/drop), then £3.50/drop thereafter?

**Bundled vs. Unbundled Test:**

| Model | Structure | Pro | Con |
|---|---|---|---|
| **Unbundled** | £49/mo subscription + £4/drop | Simple. Clear per-drop cost. | Double charge feels expensive. |
| **Bundled** | £49/mo includes 20 free drops + £4/drop overage | Encourages usage. Higher perceived value. | Revenue risk if merchants use all 20. |
| **Pure Per-Drop** | No subscription. £5/drop all-in. | Lowest barrier. No commitment. | No recurring revenue. Hard to forecast. |

### Experiment 3C: Courier Rate Ladder

**Method:** Survey couriers (during interviews and via online survey) with different earning scenarios.

| Scenario | Earning Per Drop | Distance | Time | Expected Acceptance |
|---|---|---|---|---|
| "On your route, 5 min" | £2.00 | 0.3 miles | 5 min | ~60% |
| "On your route, 5 min" | £3.00 | 0.3 miles | 5 min | ~85% |
| "On your route, 5 min" | £4.00 | 0.3 miles | 5 min | ~95% |
| "Small detour, 10 min" | £3.00 | 0.8 miles | 10 min | ~50% |
| "Small detour, 10 min" | £4.00 | 0.8 miles | 10 min | ~70% |
| "Small detour, 10 min" | £5.00 | 0.8 miles | 10 min | ~85% |
| "Dedicated trip, 20 min" | £5.00 | 1.5 miles | 20 min | ~40% |
| "Dedicated trip, 20 min" | £7.00 | 1.5 miles | 20 min | ~65% |
| "Dedicated trip, 20 min" | £10.00 | 1.5 miles | 20 min | ~85% |

**Key Question:** Can the True Marketplace model (couriers set their own rates) naturally find the equilibrium where senders' WTP meets couriers' minimum acceptable rate? Our hypothesis: for on-route deliveries, the equilibrium is £3-4/drop, which leaves ~£0.57 net margin for the platform after the 15% fee.

---

## 4. Price Sensitivity by Segment — Depth Analysis

### Pharmacy Price Elasticity Model

| Drops/Day | At £3.50/drop | At £4.50/drop | At £5.50/drop |
|---|---|---|---|
| 5 | £17.50/day → £4,550/yr | £22.50/day → £5,850/yr | £27.50/day → £7,150/yr |
| 10 | £35.00/day → £9,100/yr | £45.00/day → £11,700/yr | £55.00/day → £14,300/yr |
| 15 | £52.50/day → £13,650/yr | £67.50/day → £17,550/yr | £82.50/day → £21,450/yr |

**Comparison to alternatives:**
- Part-time driver: £12,000-15,000/yr (fixed cost regardless of volume)
- Self-delivery (pharmacist's time): £12/trip × 10/day × 260 days = £31,200/yr in opportunity cost

**Insight:** Even at £5.50/drop, a pharmacy doing 10 deliveries/day spends £14,300/yr — less than a part-time driver and less than half the opportunity cost of self-delivery. Price sensitivity is LOW for this segment.

### C2C Price Sensitivity — Royal Mail Benchmark

| Our Price | Royal Mail 2nd Class | Price Advantage | Speed Advantage |
|---|---|---|---|
| £2.50 | £3.49 | -£0.99 (29% cheaper) | +2 days faster |
| £3.00 | £3.49 | -£0.49 (14% cheaper) | +2 days faster |
| £3.50 | £3.49 | +£0.01 (break-even) | +2 days faster |
| £4.00 | £3.49 | +£0.51 (15% more) | +2 days faster |
| £4.50 | £3.49 | +£1.01 (29% more) | +2 days faster |

**Key Insight:** At £3.50+ we lose the price advantage over Royal Mail. We must compete on speed and convenience. Our messaging for C2C should emphasise "same-day delivery, no post office queue" rather than "cheaper than Royal Mail."

---

## 5. Revenue Scenario Modelling

### Base Case: UCL/Bloomsbury Wedge, Month 12

| Segment | Drops/Day | Avg Price/Drop | Platform Fee (15%) | Monthly Revenue |
|---|---|---|---|---|
| Pharmacies (10 active) | 80 | £4.50 | £0.675 | £1,755 |
| Hardware/Print (5 active) | 15 | £5.50 | £0.825 | £402 |
| C2C Resellers | 20 | £3.50 | £0.525 | £341 |
| Students | 15 | £3.00 | £0.45 | £219 |
| **Drop Revenue** | **130/day** | | | **£2,717/mo** |
| B2B Subscriptions (15 merchants × £49/mo) | | | | **£735/mo** |
| **Total Monthly Revenue** | | | | **£3,452/mo** |
| **Annual Run-Rate** | | | | **£41,424** |

### Optimistic Case: Month 12

| Source | Drops/Day | Monthly Revenue |
|---|---|---|
| Drops (200/day avg, £4.50 avg, 15% fee) | 200 | £4,050 |
| B2B Subscriptions (25 × £49) | — | £1,225 |
| **Total** | | **£5,275/mo (£63K ARR)** |

### Pessimistic Case: Month 12

| Source | Drops/Day | Monthly Revenue |
|---|---|---|
| Drops (60/day avg, £3.50 avg, 15% fee) | 60 | £819 |
| B2B Subscriptions (8 × £29) | — | £232 |
| **Total** | | **£1,051/mo (£12.6K ARR)** |

---

## 6. Pricing Implementation Plan

### Phase 1: Discovery (Now)
- Collect Van Westendorp data from 25 sender interviews
- Survey 12 couriers on minimum acceptable earnings
- Document all pricing objections verbatim

### Phase 2: Concierge MVP (Month 3-4)
- Test prices at £3.50, £4.00, £4.50, £5.00 across different merchants
- Observe actual courier pricing in True Marketplace (let them set rates, see where they land)
- Measure price elasticity (does demand change at different price points?)

### Phase 3: Wizard of Oz (Month 5-6)
- Run full price ladder experiment across 8 merchants
- Test bundled vs. unbundled subscription models
- Launch online conjoint analysis survey (200 respondents)

### Phase 4: Real MVP Launch (Month 7+)
- Implement data-driven pricing based on all learnings
- Set platform fee at 15% (validated range: 12-18%)
- Launch with "Founder's Rate" subscription at £29/mo, increasing to £49/mo at Month 9
- Monitor price-to-churn sensitivity monthly

---

*Pricing findings feed into [success_metrics.md](../product_validation/success_metrics.md) unit economics and [assumption_mapping.md](../product_validation/assumption_mapping.md).*
