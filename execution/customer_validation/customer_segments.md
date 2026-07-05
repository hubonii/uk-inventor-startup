# Customer Segmentation Analysis

## Local-Logistics Protocol — Target Customer Segments

> **Last Updated:** July 2026
> **Status:** Pre-Validation — Hypotheses to be tested via discovery interviews

---

## Segmentation Framework

We segment by **job urgency × trust sensitivity**. Every segment below shares the same core friction: they need something moved locally, today, and cannot justify (or access) traditional courier pricing. The cryptographic chain-of-custody protocol addresses the trust gap that prevents them from handing packages to strangers.

---

## Segment A: Independent Pharmacies — Same-Day Prescription Drops

### Market Definition

Independent community pharmacies in dense London postcodes (WC1, N1, E1-E2, SE1) that currently offer no delivery or rely on ad-hoc staff runs. This excludes Boots/Lloyds chains (who have national logistics contracts) and focuses on the ~1,800 independent pharmacies within the M25.

### Sizing

| Metric | Estimate | Source / Basis |
|---|---|---|
| Independent pharmacies in London | ~1,800 | GPhC register, 2025 |
| Target "University Wedge" (UCL/Bloomsbury, WC1/N1) | ~85 | Manual mapping via Google Maps + NHS directory |
| Avg. delivery-eligible prescriptions/day/pharmacy | 8-15 | NPA Small Pharmacy Survey 2024 |
| Addressable daily drops (wedge, at 30% conversion) | ~250 | 85 × 10 avg × 30% |
| Annual addressable revenue (wedge only, at £5 avg drop) | ~£325,000 | 250 × £5 × 260 working days |

### Pain Intensity: 🔴 CRITICAL (9/10)

- **Regulatory pressure:** NHS England increasingly mandates delivery options for vulnerable patients (2025 Community Pharmacy Contractual Framework).
- **Competitive threat:** Pharmacy2U, Echo (Lloyds), and Amazon Pharmacy offer free next-day delivery. Independents lose patients who can't collect in person.
- **Staff constraints:** Hiring a dedicated delivery driver costs £25,000-£30,000/yr — uneconomic for a pharmacy doing £400K revenue.
- **Urgency profile:** Prescriptions are time-sensitive (antibiotics, insulin, controlled substances). Same-day is not a luxury; it's clinical necessity.
- **Current workaround:** Owner/technician leaves the counter, drives the drop personally, closing the dispensary or leaving it short-staffed. Average round-trip: 25 minutes. Opportunity cost: ~£12 in lost dispensing time.

### Willingness to Pay

| Pricing Element | Estimated WTP | Confidence |
|---|---|---|
| Per-drop fee (passed to patient or absorbed) | £3.50 – £5.50 | Medium — needs Van Westendorp validation |
| Monthly B2B SaaS subscription (dashboard, compliance logs, billing) | £39 – £59/mo | Medium — anchored to existing POS software costs |
| Aggregated weekly invoicing (vs. per-drop card payments) | Strong preference | High — pharmacists hate per-transaction friction |

### Accessibility

| Factor | Score (1-5) | Notes |
|---|---|---|
| Decision-maker reachability | ⭐⭐⭐⭐⭐ | Owner-pharmacist is behind the counter. Walk in, pitch in 3 minutes. |
| Buying cycle length | ⭐⭐⭐⭐⭐ | No procurement committee. Owner decides on the spot. |
| Technical readiness | ⭐⭐⭐ | Mixed. Most have smartphones but many still use paper-based systems. QR handshake must be dead simple. |
| Regulatory complexity | ⭐⭐ | Prescription delivery has chain-of-custody requirements (CQC). Our TOTP protocol *helps* here but needs GPhC sign-off on digital proof-of-delivery. |
| Willingness to experiment | ⭐⭐⭐⭐ | Desperate for a solution. Low risk tolerance, but high pain = high motivation. |

### Key Hypotheses to Validate

1. Independent pharmacists currently lose ≥3 patients/week to online pharmacy competitors due to lack of delivery.
2. Pharmacists would pay £3-5 per drop rather than leave the counter.
3. Digital chain-of-custody (QR handshake) satisfies GPhC/CQC audit requirements.
4. Pharmacy staff can be onboarded to the dispatch workflow in <10 minutes.

---

## Segment B: Hardware & Print Shops — Instant Local Delivery

### Market Definition

Independent hardware stores, print shops, key-cutting/shoe-repair shops, and specialist retailers (art supplies, electronics components) in dense urban areas. These are high-street businesses where customers often need items urgently but can't carry them or can't visit in person.

### Sizing

| Metric | Estimate | Source / Basis |
|---|---|---|
| Independent specialist retailers in London | ~12,000 | ONS Business Demography 2024, SIC codes 47.5-47.7 |
| Target "University Wedge" (WC1/N1) | ~200 | Manual mapping |
| Avg. delivery-eligible orders/day/shop | 2-5 | Hypothesis — lower frequency than pharmacy |
| Addressable daily drops (wedge, at 20% conversion) | ~120 | 200 × 3 avg × 20% |
| Annual addressable revenue (wedge only, at £5.50 avg drop) | ~£170,000 | 120 × £5.50 × 260 days |

### Pain Intensity: 🟡 HIGH (7/10)

- **Customer expectation gap:** Amazon/Argos same-day delivery has reset expectations. A customer who needs a specific drill bit or a printed banner *today* will order online if the local shop can't deliver.
- **Revenue leakage:** Shop owners report losing 2-5 sales/week because the customer "can't carry it" or "will come back later" (and never does).
- **No existing solution:** Royal Mail and DPD don't do same-hour local delivery. Uber Connect exists but is expensive (£8-15) and has no chain-of-custody for valuable items.
- **Current workaround:** Shop owner's teenage son, a favour from a friend, or "sorry, we don't deliver."

### Willingness to Pay

| Pricing Element | Estimated WTP | Confidence |
|---|---|---|
| Per-drop fee (passed to customer) | £4.00 – £7.00 | Medium — higher item values justify higher delivery fees |
| Monthly SaaS subscription | £29 – £49/mo | Low — price-sensitive segment, need to validate |
| Markup absorption | Some shops may absorb £2-3 as a competitive advantage | Low — hypothesis |

### Accessibility

| Factor | Score (1-5) | Notes |
|---|---|---|
| Decision-maker reachability | ⭐⭐⭐⭐⭐ | Owner is in the shop. Same walk-in pitch model as pharmacies. |
| Buying cycle length | ⭐⭐⭐⭐⭐ | Instant decision-maker. |
| Technical readiness | ⭐⭐⭐ | Varies wildly. Some have Shopify POS, others use a paper till roll. |
| Regulatory complexity | ⭐⭐⭐⭐⭐ | None. No special handling requirements. |
| Willingness to experiment | ⭐⭐⭐ | Moderate. Less pain = less urgency to try something new. |

### Key Hypotheses to Validate

1. Independent retailers lose ≥2 sales/week due to inability to offer local delivery.
2. Customers would pay £4-6 delivery on a £15+ local purchase rather than ordering from Amazon.
3. Shop owners can dispatch a package in <2 minutes using our QR flow.
4. Demand is concentrated enough in the "wedge" to keep courier wait times <15 min.

---

## Segment C: C2C Resellers (Vinted/Depop Sellers)

### Market Definition

Individual sellers on peer-to-peer marketplaces (Vinted, Depop, eBay, Facebook Marketplace) who sell locally and want a cheaper/faster alternative to Royal Mail. Focus on high-volume sellers (5+ items/week) in London.

### Sizing

| Metric | Estimate | Source / Basis |
|---|---|---|
| Active Vinted/Depop sellers in London | ~180,000 | Vinted UK press releases (15M UK users, ~8% active sellers, 15% London) |
| High-volume sellers (5+ items/week) | ~18,000 | Estimate 10% of active sellers |
| Target "University Wedge" residents | ~2,000 | UCL area population density |
| Avg. local-eligible sales/week/seller | 1-2 | Most sales are national; local is a subset |
| Addressable weekly drops (wedge) | ~400 | 2,000 × 10% adoption × 2/week |
| Annual addressable revenue (wedge only, at £3.50 avg) | ~£72,000 | 400 × £3.50 × 52 weeks |

### Pain Intensity: 🟠 MEDIUM-HIGH (6/10)

- **Royal Mail friction:** Queue at the post office (avg. 12-minute wait). Buy packaging. Pay £3.49+ for 2nd class. Item arrives in 2-3 days.
- **Local sales opportunity:** ~15% of Vinted/Depop transactions are within the same city. Sellers and buyers *want* local exchange but lack a safe, convenient mechanism.
- **Trust gap in local exchange:** Meeting strangers for handoffs creates safety concerns, especially for women and younger sellers. Our TOTP QR handshake eliminates the "meet a stranger in a car park" problem.
- **Current workaround:** Royal Mail regardless of distance, or awkward meet-ups at tube stations.

### Willingness to Pay

| Pricing Element | Estimated WTP | Confidence |
|---|---|---|
| Per-drop fee | £2.50 – £4.00 | Medium — must undercut Royal Mail 2nd class (£3.49) |
| Subscription | £0 — not viable for C2C | High — consumers won't pay monthly fees |
| Speed premium (same-day vs. 2-day) | +£1.00 – £1.50 | Low — needs testing |

### Accessibility

| Factor | Score (1-5) | Notes |
|---|---|---|
| Decision-maker reachability | ⭐⭐ | Fragmented, online-native audience. Must reach via digital channels. |
| Buying cycle length | ⭐⭐⭐⭐⭐ | Instant. Download app, use it. |
| Technical readiness | ⭐⭐⭐⭐⭐ | Digital-native. Already using 2-3 marketplace apps. |
| Regulatory complexity | ⭐⭐⭐⭐⭐ | None. |
| Willingness to experiment | ⭐⭐⭐⭐ | High. Always looking for cheaper/faster ways to ship. |

### Key Hypotheses to Validate

1. At least 15% of Vinted/Depop transactions in London are buyer-seller pairs within 5 miles.
2. Sellers would switch from Royal Mail for local drops if price ≤ £3.00 and delivery is same-day.
3. The TOTP QR handshake removes enough trust friction for strangers to accept the hand-off.
4. C2C volume is consistent enough to feed the courier supply side (not just weekends).

---

## Segment D: University Students — Textbook & Goods Exchange

### Market Definition

Students at London universities (starting UCL, expanding to KCL, Imperial, LSE) exchanging textbooks, lab equipment, course materials, and general goods. Also covers food/grocery sharing and "I forgot my charger" micro-errands.

### Sizing

| Metric | Estimate | Source / Basis |
|---|---|---|
| UCL students (full-time) | ~42,000 | UCL Annual Report 2024 |
| Students in UCL "wedge" (living in WC1/N1/NW1) | ~15,000 | HESA + UCL accommodation data |
| Estimated local-delivery-eligible transactions/week | 200-400 | Hypothesis: textbook swaps, forgotten items, marketplace purchases |
| Addressable weekly drops | ~100 | 25-50% adoption of eligible transactions |
| Annual addressable revenue (at £3.00 avg) | ~£15,600 | 100 × £3.00 × 52 weeks |

### Pain Intensity: 🟡 MEDIUM (5/10)

- **Textbook exchange:** Second-hand textbooks are expensive to ship (heavy, oversized). Students sell on Facebook groups but delivery is a hassle.
- **Forgotten items:** "Left my notes in halls, I'm in the library" — micro-errands that aren't worth a cab but are too far to walk.
- **Marketplace friction:** Student marketplace apps (e.g., Unibuddy, Facebook groups) lack integrated delivery.
- **Current workaround:** Walk/cycle themselves, ask a flatmate, or just don't bother.

### Willingness to Pay

| Pricing Element | Estimated WTP | Confidence |
|---|---|---|
| Per-drop fee | £2.00 – £3.50 | Medium — students are extremely price-sensitive |
| Subscription | £0 | High — no student pays a monthly fee for sporadic use |
| "Errand" premium (non-package tasks) | +£1.00 | Low — scope creep risk |

### Accessibility

| Factor | Score (1-5) | Notes |
|---|---|---|
| Decision-maker reachability | ⭐⭐⭐⭐⭐ | On campus. Poster boards, SU partnerships, freshers' fairs. |
| Buying cycle length | ⭐⭐⭐⭐⭐ | Instant. |
| Technical readiness | ⭐⭐⭐⭐⭐ | Gen Z. Smartphone-native. |
| Regulatory complexity | ⭐⭐⭐⭐⭐ | None. |
| Willingness to experiment | ⭐⭐⭐⭐⭐ | Highest of all segments. Will try anything if free/cheap. |

### Key Hypotheses to Validate

1. Students make ≥1 local delivery-eligible transaction per month.
2. Price sensitivity caps WTP at ~£3.00 per drop.
3. Students will also *supply* courier labour (walking between halls and campus anyway).
4. Usage is highly seasonal (term-time only, with spikes at start/end of term).

---

## Segment Priority Matrix

| Segment | Pain Intensity | WTP | Market Size (Wedge) | Accessibility | Revenue Potential | **Priority** |
|---|---|---|---|---|---|---|
| A: Independent Pharmacies | 🔴 9/10 | £3.50-5.50/drop + £49/mo SaaS | 85 shops | ⭐⭐⭐⭐ | £325K/yr | **🥇 #1 — Beachhead** |
| B: Hardware/Print Shops | 🟡 7/10 | £4-7/drop + £29-49/mo SaaS | 200 shops | ⭐⭐⭐⭐ | £170K/yr | **🥈 #2 — Fast Follow** |
| C: C2C Resellers | 🟠 6/10 | £2.50-4.00/drop | 2,000 sellers | ⭐⭐ | £72K/yr | **🥉 #3 — Volume Play** |
| D: University Students | 🟡 5/10 | £2-3.50/drop | 15,000 students | ⭐⭐⭐⭐⭐ | £16K/yr | **#4 — Supply-Side Feeder** |

### Strategic Rationale

**Pharmacies first** because:
1. Highest pain = fastest sales cycle
2. Recurring B2B SaaS revenue (£49/mo) gives predictable MRR for investor narrative
3. Regulatory chain-of-custody is a *moat* — our TOTP protocol is a genuine differentiator
4. NHS/healthcare angle strengthens Innovator Founder Visa "innovation" narrative
5. Daily, predictable demand creates reliable courier utilisation

**Students as supply-side feeder** — even though revenue per student is low, they provide the courier labour pool. A student walking from halls to campus can carry a pharmacy prescription en route. The demand side (pharmacies) and supply side (students) are geographically co-located in the University Wedge.

---

## Cross-Segment Demand Density Model

For the courier marketplace to work, we need sufficient demand density to keep courier wait times under 15 minutes. Here's the combined model for the UCL/Bloomsbury wedge:

| Time Slot | Pharmacy | Hardware/Print | C2C | Student | **Total Drops/Hour** |
|---|---|---|---|---|---|
| 08:00-10:00 | 5 | 1 | 0 | 2 | **8** |
| 10:00-12:00 | 8 | 3 | 2 | 5 | **18** |
| 12:00-14:00 | 6 | 4 | 3 | 8 | **21** |
| 14:00-16:00 | 7 | 3 | 4 | 6 | **20** |
| 16:00-18:00 | 10 | 2 | 3 | 4 | **19** |
| 18:00-20:00 | 3 | 0 | 5 | 3 | **11** |
| **Daily Total** | **39** | **13** | **17** | **28** | **97** |

At 97 drops/day in a ~2km² wedge, a courier doing 3 drops/hour needs ~32 courier-hours/day. With part-time students doing 2-3 hour shifts, that's 12-16 active couriers — achievable with a pool of 40-50 registered couriers.

---

*Next step: Validate these segments through customer discovery interviews (see [interview_plan.md](interview_plan.md)).*
