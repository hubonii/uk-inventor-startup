# Problem Validation Framework

## Local-Logistics Protocol — Do People Actually Have This Problem?

> **Last Updated:** July 2026
> **Status:** Pre-Validation — Hypotheses defined, experiments not yet run
> **Methodology:** Lean Validation Board + Hypothesis-Driven Entrepreneurship

---

## Core Problem Statement

> **Urban merchants and individuals cannot move physical items across short distances (0.5-5 miles) affordably (<£5), quickly (same-day), and safely (without fear of loss/theft) — because no logistics option exists that is simultaneously cheap enough, fast enough, and trustworthy enough for low-to-mid-value items.**

This problem statement contains three embedded sub-problems:

1. **Affordability:** Existing same-day options (Uber Connect, Stuart) cost £8-20 — too expensive for a £15 item or a pharmacy prescription
2. **Speed:** Affordable options (Royal Mail) take 1-3 days — too slow for urgent or perishable needs
3. **Trust:** No mechanism exists to safely hand a valuable item to an unvetted stranger without anxiety

---

## Hypothesis Map

### H1: Primary Problem Hypothesis

> **Hypothesis:** Independent merchants in dense urban areas lose revenue and operational efficiency because they cannot offer affordable same-day local delivery.

| Element | Detail |
|---|---|
| **Falsifiable Prediction** | ≥60% of independent pharmacies in WC1/N1 report losing ≥2 patients/month to online competitors due to lack of delivery |
| **Experiment** | 15 semi-structured interviews with independent pharmacists |
| **Success Criteria** | ≥9 of 15 (60%) confirm this pattern |
| **Kill Criteria** | <5 of 15 (33%) confirm, OR average pain score <5/10 |
| **Status** | ⬜ Not yet tested |

### H2: Trust Barrier Hypothesis

> **Hypothesis:** The primary barrier to using gig couriers for valuable items is trust — specifically, the fear that the courier will steal, lose, or damage the item, and that there will be no recourse.

| Element | Detail |
|---|---|
| **Falsifiable Prediction** | ≥70% of potential senders cite "trust in the courier" as a top-3 concern when asked about using stranger-based delivery |
| **Experiment** | 25 interviews across all sender segments (pharmacy, hardware, C2C, student) |
| **Success Criteria** | ≥18 of 25 (70%) cite trust unprompted or when asked about concerns |
| **Kill Criteria** | <8 of 25 (32%) cite trust, suggesting the barrier is something else |
| **Status** | ⬜ Not yet tested |

### H3: Price-Speed Gap Hypothesis

> **Hypothesis:** A gap exists between "affordable but slow" (Royal Mail, £3.49, 2 days) and "fast but expensive" (Uber Connect, £8-15, 1 hour) — and customers would pay £3-5 for a same-day option.

| Element | Detail |
|---|---|
| **Falsifiable Prediction** | ≥50% of senders indicate willingness to pay £3.50-5.50 for same-day local delivery when presented with the Van Westendorp pricing questions |
| **Experiment** | Pricing questions embedded in 25 sender interviews |
| **Success Criteria** | ≥13 of 25 (50%) indicate WTP within our target range |
| **Kill Criteria** | <7 of 25 (28%) indicate WTP, OR the "too expensive" threshold is below £3.00 |
| **Status** | ⬜ Not yet tested |

### H4: Courier Supply Hypothesis

> **Hypothesis:** Sufficient courier supply exists among students, gig workers, and local residents who are already walking/cycling routes through the target area and would carry packages for £3-5 per drop.

| Element | Detail |
|---|---|
| **Falsifiable Prediction** | ≥60% of potential couriers surveyed would accept package delivery jobs for £3-5 if the pickup/dropoff is ≤500m from their existing route |
| **Experiment** | 12 interviews with students, gig workers, and local residents + 1-week walking diary study with 10 students |
| **Success Criteria** | ≥8 of 12 (60%) express willingness at target rates. Diary study shows ≥5 students walk routes passing ≥2 pharmacy locations daily |
| **Kill Criteria** | <4 of 12 (33%) express willingness, OR diary study shows routes are too dispersed for efficient matching |
| **Status** | ⬜ Not yet tested |

### H5: Collateral Deposit Hypothesis

> **Hypothesis:** A £50 refundable deposit from couriers significantly increases sender trust, AND at least 50% of potential couriers will accept it.

| Element | Detail |
|---|---|
| **Falsifiable Prediction** | Sender trust increases ≥3 points (on 1-10 scale) when told about the £50 deposit. ≥50% of potential couriers say they would pay it. |
| **Experiment** | Trust A/B within interviews (ask about trust BEFORE mentioning deposit, then ask again AFTER) + courier deposit acceptance in courier interviews |
| **Success Criteria** | Average sender trust increase ≥3 points. ≥6 of 12 couriers accept the deposit. |
| **Kill Criteria** | Trust increase <1 point (deposit doesn't move the needle). <3 of 12 couriers accept it. |
| **Status** | ⬜ Not yet tested |

### H6: QR Handshake Acceptance Hypothesis

> **Hypothesis:** Both senders and receivers will find a TOTP QR handshake (scan-to-confirm) an acceptable and reassuring way to verify delivery, without it being too much friction.

| Element | Detail |
|---|---|
| **Falsifiable Prediction** | ≥70% of interviewees say the QR handshake is "reassuring" or "a good idea." <20% say it's "too much hassle." |
| **Experiment** | Show a mockup/diagram of the QR flow in 25 interviews. Ask for reaction. |
| **Success Criteria** | ≥18 of 25 find it positive. <5 of 25 find it too much friction. |
| **Kill Criteria** | <13 of 25 find it positive. ≥8 of 25 find it too friction-heavy. |
| **Status** | ⬜ Not yet tested |

### H7: Demand Density Hypothesis

> **Hypothesis:** The UCL/Bloomsbury "wedge" (WC1/N1, ~2km²) can generate ≥50 delivery requests/day within 6 months of launch, sufficient for marketplace liquidity.

| Element | Detail |
|---|---|
| **Falsifiable Prediction** | Combining pharmacy interviews (daily delivery count × adoption rate) + hardware (daily eligible orders) + C2C (weekly local sales) + students yields ≥50 modelled drops/day |
| **Experiment** | Bottom-up demand modelling from interview data |
| **Success Criteria** | Model shows ≥50 drops/day with conservative assumptions (20-30% adoption rates) |
| **Kill Criteria** | Model shows <25 drops/day even with optimistic assumptions (50% adoption) |
| **Status** | ⬜ Not yet tested |

### H8: Regulatory Compatibility Hypothesis

> **Hypothesis:** Our TOTP QR chain-of-custody protocol satisfies GPhC/CQC requirements for prescription delivery audit trails.

| Element | Detail |
|---|---|
| **Falsifiable Prediction** | At least 1 pharmacy consultant or regulatory advisor confirms the protocol would satisfy CQC inspection requirements |
| **Experiment** | Consultation with 2 pharmacy compliance experts + 1 CQC inquiry |
| **Success Criteria** | Positive confirmation from ≥1 expert. No fundamental blockers identified. |
| **Kill Criteria** | All experts say it's insufficient. CQC requires in-person signature or physical audit trail. |
| **Status** | ⬜ Not yet tested |

---

## Experiment Priority & Sequencing

| Priority | Hypothesis | Risk Level | Sequence | Rationale |
|---|---|---|---|---|
| 🔴 P1 | H1: Problem exists | Existential | Week 2-3 | If the problem isn't real, nothing else matters |
| 🔴 P1 | H3: Price-speed gap | Existential | Week 2-5 | If no one will pay, the business doesn't work |
| 🔴 P1 | H4: Courier supply | Existential | Week 5-6 | No supply = no marketplace |
| 🟠 P2 | H2: Trust barrier | Core Value Prop | Week 2-6 | Trust is our differentiator; must validate it's the real issue |
| 🟠 P2 | H5: Deposit acceptance | Core Mechanism | Week 2-6 | Tests a specific feature of our trust architecture |
| 🟡 P3 | H6: QR handshake UX | Feature Design | Week 3-6 | Tests usability of our core protocol |
| 🟡 P3 | H7: Demand density | Marketplace Viability | Week 7-8 | Modelled from interview data; not directly tested pre-MVP |
| 🟡 P3 | H8: Regulatory | Compliance | Week 3-6 | Important for pharmacy segment but not a day-1 blocker |

---

## Validation Board

```
┌──────────────────────────────────────────────────────────────────┐
│                    VALIDATION BOARD                              │
├──────────┬───────────┬──────────┬───────────┬───────────────────┤
│ Hypothesis│ Riskiest  │Experiment│ Minimum   │ Result            │
│           │ Assumption│ Design   │ Success   │                   │
├──────────┼───────────┼──────────┼───────────┼───────────────────┤
│ H1       │ Merchants │15 pharma │ 60% pain  │ ⬜ Pending        │
│ Problem  │ lose      │interviews│ ≥7/10     │                   │
│ Exists   │ revenue   │          │           │                   │
├──────────┼───────────┼──────────┼───────────┼───────────────────┤
│ H2       │ Trust is  │25 sender │ 70% cite  │ ⬜ Pending        │
│ Trust    │ the #1    │interviews│ trust in  │                   │
│ Barrier  │ barrier   │          │ top 3     │                   │
├──────────┼───────────┼──────────┼───────────┼───────────────────┤
│ H3       │ WTP at    │25 pricing│ 50%       │ ⬜ Pending        │
│ Price    │ £3.50-5.50│questions │ accept    │                   │
│ Gap      │           │          │ range     │                   │
├──────────┼───────────┼──────────┼───────────┼───────────────────┤
│ H4       │ Couriers  │12 courier│ 60%       │ ⬜ Pending        │
│ Supply   │ exist at  │interviews│ willing   │                   │
│          │ target $  │+ diary   │ at £3-5   │                   │
├──────────┼───────────┼──────────┼───────────┼───────────────────┤
│ H5       │ £50       │A/B in    │ Trust +3  │ ⬜ Pending        │
│ Deposit  │ increases │interviews│ 50% of    │                   │
│ Trust    │ trust     │          │ couriers  │                   │
├──────────┼───────────┼──────────┼───────────┼───────────────────┤
│ H6       │ QR is     │Show      │ 70%       │ ⬜ Pending        │
│ QR UX    │ usable +  │mockup in │ positive  │                   │
│          │ reassuring│interviews│ <20% hate │                   │
├──────────┼───────────┼──────────┼───────────┼───────────────────┤
│ H7       │ 50+       │Bottom-up │ ≥50/day   │ ⬜ Pending        │
│ Density  │ drops/day │model     │ conservative│                 │
├──────────┼───────────┼──────────┼───────────┼───────────────────┤
│ H8       │ QR meets  │Expert    │ 1+ expert │ ⬜ Pending        │
│ Regulatory│CQC/GPhC  │consult   │ confirms  │                   │
└──────────┴───────────┴──────────┴───────────┴───────────────────┘
```

---

## Decision Tree

```
H1: Problem exists?
├── NO (pain <5/10) → KILL or MAJOR PIVOT
│   Consider: Is the problem elsewhere? Different segment? Different geography?
│
└── YES (pain ≥7/10) →
    │
    H3: Will they pay £3.50-5.50?
    ├── NO (WTP <£3.00) → REVISE PRICING MODEL
    │   Consider: Can we reduce cost structure? Different revenue model?
    │
    └── YES →
        │
        H4: Can we supply couriers at £3-5/drop?
        ├── NO (couriers want £7+) → REVISE SUPPLY MODEL
        │   Consider: Subsidy period? Different courier pool? Route bundling?
        │
        └── YES →
            │
            H5+H6: Trust mechanisms work?
            ├── NO → REDESIGN TRUST PROTOCOL
            │   Consider: Higher deposit? DBS checks? Insurance instead? Escrow?
            │
            └── YES →
                │
                H7: Demand density sufficient?
                ├── NO → RECONSIDER GEOGRAPHY
                │   Consider: Tighter wedge? Different neighbourhood? Phased rollout?
                │
                └── YES →
                    │
                    ✅ PROCEED TO MVP
                    Build the Concierge MVP (see mvp_validation.md)
```

---

## Evidence Tracking

### Evidence Classification

| Type | Description | Weight |
|---|---|---|
| **Strong Signal** | Unprompted mention of pain, specific examples with numbers, emotional language, history of trying alternatives | High — counts as validation |
| **Moderate Signal** | Prompted acknowledgment of pain, general agreement without specifics, theoretical interest | Medium — needs corroboration |
| **Weak Signal** | Polite agreement, hypothetical responses ("yeah I'd probably use that"), no emotional energy | Low — likely social desirability bias |
| **Counter-Signal** | Active disagreement, describes existing solutions that work well, no interest in alternatives | High — counts as invalidation |

### Per-Interview Scoring Template

```
Interview #: ___    Date: ___    Persona: ___    Name: ___

H1 - Problem Exists:
  Pain Score (1-10): ___
  Evidence Type: [Strong / Moderate / Weak / Counter]
  Key Quote: "___"

H2 - Trust Barrier:
  Trust mentioned as concern? [Y/N]
  Unprompted or prompted? ___
  Evidence Type: [Strong / Moderate / Weak / Counter]
  Key Quote: "___"

H3 - WTP:
  Price point mentioned: £___
  "Too expensive" threshold: £___
  "Bargain" threshold: £___
  Evidence Type: [Strong / Moderate / Weak / Counter]

H5 - Deposit:
  Trust before deposit mentioned (1-10): ___
  Trust after deposit explained (1-10): ___
  Delta: +___
  Key Quote: "___"

H6 - QR Handshake:
  Reaction: [Positive / Neutral / Negative]
  Key Quote: "___"

Surprise Finding: "___"
Follow-up needed? [Y/N] ___
```

---

## Pivot Triggers

If validation fails, we don't give up immediately. We explore structured pivots:

| Failed Hypothesis | Pivot Option A | Pivot Option B | Pivot Option C |
|---|---|---|---|
| H1: Problem not real for pharmacies | Pivot to hardware/print segment only | Pivot to B2B inter-merchant delivery | Test a completely different geography (e.g., suburban not urban) |
| H3: WTP too low (<£3) | Reduce cost via batch routing (3-4 drops per courier trip) | Shift to pure B2B subscription (flat monthly, unlimited deliveries) | Pivot to premium-only (high-value items, £8+ delivery with insurance) |
| H4: No courier supply | Pivot from walking couriers to cargo-bike couriers (fewer needed) | Partner with existing Deliveroo riders during dead time | Employ part-time couriers (sacrifice True Marketplace model) |
| H5: Deposit rejected | Remove deposit, replace with DBS check + insurance | Reduce to £20 deposit | Implement post-delivery hold on courier earnings instead |
| H7: Density too low | Shrink wedge to 0.5km² around UCL | Pre-schedule all deliveries (batch model, not on-demand) | Start with single-merchant Concierge MVP (1 pharmacy) |

---

*This framework guides our entire validation process. Experiments are executed via [interview_plan.md](interview_plan.md) and measured against [success_metrics.md](../product_validation/success_metrics.md).*
