# Pain Point Analysis

## Local-Logistics Protocol — Deep Pain Assessment by Segment

> **Last Updated:** July 2026
> **Status:** Pre-Validation Hypotheses — Severity rankings to be confirmed via discovery interviews

---

## Pain Severity Framework

| Level | Label | Definition | Business Implication |
|---|---|---|---|
| 🔴 | **Critical** | Causes measurable revenue loss, regulatory risk, or safety concern. Customer actively seeking solutions. | Build this into MVP. Non-negotiable. |
| 🟠 | **High** | Significant friction, time waste, or cost burden. Customer complains but has a workaround. | Build this into V1. |
| 🟡 | **Medium** | Annoyance or inefficiency. Customer tolerates it. | Build in V2 or later. |
| ⚪ | **Low** | Minor inconvenience. Customer barely notices. | Nice-to-have. Don't prioritise. |

---

## Segment A: Independent Pharmacies

### Pain A1: Losing Patients to Online Pharmacies 🔴 CRITICAL

| Element | Detail |
|---|---|
| **Pain Description** | Patients who can't physically collect prescriptions switch to Pharmacy2U, Echo (Lloyds), or Amazon Pharmacy, which offer free delivery. The independent pharmacy permanently loses the patient and their ~£8,000/year in prescription revenue. |
| **Severity** | 🔴 Critical — existential threat to business model |
| **Frequency** | Estimated 2-5 patient losses/month per pharmacy |
| **Financial Impact** | £16,000-£40,000/year in lost prescription revenue per pharmacy |
| **Who Feels It** | Owner-pharmacist (revenue), patients (inconvenience), NHS (reduced access) |
| **Current Alternatives** | (1) Owner delivers personally — closes shop, loses 30 min. (2) Hire a part-time driver — £12,000-15,000/yr, underutilised. (3) Volunteer delivery services — unreliable, limited hours. (4) Do nothing — lose patients. |
| **Why Alternatives Fail** | (1) Unsustainable, loses dispensing revenue. (2) Too expensive for a small pharmacy doing 60 Rx/day. (3) Not available on-demand, no accountability. (4) Death spiral. |
| **Our Solution** | On-demand courier dispatch via app. £3.50-5.50/drop. No fixed staff cost. Instant availability. |

### Pain A2: Compliance Risk with Informal Delivery 🔴 CRITICAL

| Element | Detail |
|---|---|
| **Pain Description** | When pharmacists use ad-hoc methods (asking a family member, the postman, a neighbour) to deliver prescriptions, they have no proof of delivery, no chain of custody, and potential CQC/GPhC violations — especially for Schedule 2-5 controlled drugs. |
| **Severity** | 🔴 Critical — professional licence at risk |
| **Frequency** | Every informal delivery (estimated 3-8/week) |
| **Financial Impact** | GPhC fitness-to-practice hearings cost £5,000-20,000. CQC enforcement notices can close the pharmacy. |
| **Who Feels It** | Pharmacist (liability), patient (safety), regulator (oversight gap) |
| **Current Alternatives** | (1) Paper delivery log signed by recipient — often lost or unsigned. (2) Royal Mail tracked — 24-48hr delay, prescription may expire. (3) Don't deliver controlled drugs — patient must collect. |
| **Why Alternatives Fail** | (1) Not tamper-proof, not timestamped, not GPS-tagged. (2) Too slow for urgent medications. (3) Vulnerable patients can't always collect. |
| **Our Solution** | TOTP QR handshake creates cryptographic, timestamped, GPS-tagged proof of custody transfer. Generates CQC-ready audit logs automatically. |

### Pain A3: Counter Abandonment During Deliveries 🟠 HIGH

| Element | Detail |
|---|---|
| **Pain Description** | When the pharmacist or technician leaves to make a delivery, the dispensary is short-staffed. Walk-in patients wait longer, phone calls go unanswered, and dispensing errors increase under time pressure. |
| **Severity** | 🟠 High — operational disruption |
| **Frequency** | 1-3 times/day in pharmacies doing self-delivery |
| **Financial Impact** | ~£12/delivery in lost dispensing productivity (25-min round trip at pharmacist hourly rate) |
| **Who Feels It** | Pharmacist (stress), staff (overload), patients (wait times) |
| **Current Alternatives** | Hire a second pharmacist (£40K+/yr) or a delivery driver (£25K/yr). |
| **Why Alternatives Fail** | Both are prohibitively expensive for a small pharmacy. |
| **Our Solution** | Courier does the delivery. Pharmacist stays behind the counter. 25 minutes saved per delivery. |

### Pain A4: Unpredictable Delivery Costs 🟡 MEDIUM

| Element | Detail |
|---|---|
| **Pain Description** | Using ad-hoc solutions (taxis, Uber, asking staff to drive) creates unpredictable, untrackable delivery costs. Pharmacist can't budget for it. |
| **Severity** | 🟡 Medium — operational annoyance |
| **Current Alternatives** | Absorb the cost informally, pass costs to patients (awkward), or use a flat-rate courier (expensive). |
| **Our Solution** | Transparent per-drop pricing. Aggregated weekly invoicing. Predictable monthly cost. |

---

## Segment B: Hardware & Print Shops

### Pain B1: Lost Sales Due to Lack of Delivery 🟠 HIGH

| Element | Detail |
|---|---|
| **Pain Description** | Customer wants to buy but can't carry the item (e.g., 20kg bag of cement, framed print, assembled furniture part). They say "I'll come back" and never do — or they order the same item on Amazon. |
| **Severity** | 🟠 High — direct revenue loss |
| **Frequency** | Estimated 2-5 lost sales/week |
| **Financial Impact** | £5,000-£15,000/year in lost revenue per shop (at avg £30 sale, 3 lost sales/week, 50 weeks) |
| **Who Feels It** | Shop owner (revenue), customer (inconvenience) |
| **Current Alternatives** | (1) "Can you come back with a car?" (2) Offer free delivery via owner's van (if they have one). (3) Royal Mail / DPD for next-day. (4) Uber Connect — £8-15 per trip. |
| **Why Alternatives Fail** | (1) Customer doesn't come back. (2) Owner can't leave the shop. (3) Next-day is too slow for impulse purchases. (4) Too expensive relative to item value. |
| **Our Solution** | Same-hour delivery for £4-7. Customer pays at checkout. Shop dispatches in 2 minutes via QR. |

### Pain B2: Competing with Amazon on Convenience 🟠 HIGH

| Element | Detail |
|---|---|
| **Pain Description** | Amazon offers same-day or next-day delivery with Prime. Local shops can't match this convenience. Even when the local shop has the item *right now*, the friction of visiting the shop and carrying the item home makes Amazon the easier choice. |
| **Severity** | 🟠 High — competitive existential threat |
| **Frequency** | Constant, accelerating |
| **Financial Impact** | UK independent retail revenue declined 23% 2019-2024 (Local Data Company) |
| **Current Alternatives** | Hope customers value "shopping local." |
| **Why Alternatives Fail** | Convenience trumps values for most consumers. |
| **Our Solution** | "Same-hour local delivery" — actually faster than Amazon. Positioned as "Amazon convenience, local shop prices, zero emissions." |

### Pain B3: No Suitable Courier for Small, Local Deliveries 🟡 MEDIUM

| Element | Detail |
|---|---|
| **Pain Description** | Traditional couriers (DPD, Hermes, Royal Mail) have minimum charges of £5-8, require pre-booking, and deliver next-day. There's no on-demand, affordable option for sending a £15 item 1.5 miles. |
| **Severity** | 🟡 Medium — the gap exists but shops have adapted by not offering delivery |
| **Frequency** | Whenever a customer needs delivery |
| **Current Alternatives** | Overpriced couriers, shop owner's personal vehicle, or simply not offering delivery. |
| **Our Solution** | Walking/cycling couriers at £4-7 per drop, available in <15 minutes. |

---

## Segment C: C2C Resellers

### Pain C1: Post Office Queue Friction 🟠 HIGH

| Element | Detail |
|---|---|
| **Pain Description** | Sending items via Royal Mail requires going to the post office, queueing (avg. 12 minutes in urban London), buying packaging, and paying £3.49+ per item. For a seller doing 10+ items/week, this consumes 2+ hours of time weekly. |
| **Severity** | 🟠 High — significant time waste |
| **Frequency** | Every shipment (potentially daily for high-volume sellers) |
| **Financial Impact** | 2+ hours/week × 50 weeks × £12/hr opportunity cost = £1,200/year in lost time |
| **Who Feels It** | High-volume Vinted/Depop sellers |
| **Current Alternatives** | (1) Royal Mail Click & Drop + Parcel Postbox — limited box sizes, not always near home. (2) InPost lockers — requires buyer to have a nearby locker. (3) Evri drop-off at local shop — queues, limited hours. |
| **Why Alternatives Fail** | (1) Limited to small items <2kg. (2) Coverage is patchy. (3) Still requires leaving home and queuing. |
| **Our Solution** | Courier comes to your door. No post office, no queue, no packaging (courier handles handshake). |

### Pain C2: Unsafe Stranger Meet-Ups 🟠 HIGH

| Element | Detail |
|---|---|
| **Pain Description** | Local sales on Facebook Marketplace, Gumtree, and Vinted often involve meeting strangers in public places. This creates safety concerns, particularly for women, non-binary, and younger sellers. |
| **Severity** | 🟠 High — safety and emotional friction |
| **Frequency** | Every local in-person transaction |
| **Financial Impact** | Hard to quantify, but estimated 30-40% of potential local sales are abandoned due to safety concerns |
| **Who Feels It** | Sellers (especially women and younger sellers), buyers |
| **Current Alternatives** | (1) Meet in a busy public place (still uncomfortable). (2) Ship via Royal Mail (defeats the purpose of local selling). (3) Don't sell locally. |
| **Why Alternatives Fail** | (1) Doesn't eliminate risk, just reduces it. (2) Adds £3.49+ and 2 days. (3) Leaves money on the table. |
| **Our Solution** | Vetted courier with £50 deposit and cryptographic handshake acts as a trusted intermediary. Neither buyer nor seller meets a stranger. |

### Pain C3: Slow Payment Release 🟡 MEDIUM

| Element | Detail |
|---|---|
| **Pain Description** | On Vinted/Depop, seller payment isn't released until the buyer confirms receipt. Royal Mail 2nd class takes 2-3 days, so payment is locked for 3-5 days. |
| **Severity** | 🟡 Medium — cash flow annoyance |
| **Financial Impact** | Cash locked for 3-5 days per sale × 10 sales/week = £150-500 perpetually locked up |
| **Our Solution** | Same-day delivery → same-day buyer confirmation → same-day payment release. |

---

## Segment D: University Students

### Pain D1: Textbook/Item Exchange Friction 🟡 MEDIUM

| Element | Detail |
|---|---|
| **Pain Description** | Students selling textbooks or items to other students must coordinate meet-ups between lectures, across campus, at inconvenient times. Many potential sales fall through due to scheduling friction. |
| **Severity** | 🟡 Medium — annoying but not critical |
| **Frequency** | Start/end of each term (heavy), occasional during term |
| **Financial Impact** | Avg. textbook sold for £15-30. Lost sales = £50-100/term per active seller. |
| **Current Alternatives** | Student FB groups, campus notice boards, meet between lectures. |
| **Why Alternatives Fail** | Scheduling is hard. "I'm free at 2 but I have a tutorial at 3" spiral. |
| **Our Solution** | Drop it with a courier. £2-3 delivery. Both parties stay where they are. |

### Pain D2: Forgotten Items / Micro-Errands 🟡 MEDIUM

| Element | Detail |
|---|---|
| **Pain Description** | "I left my laptop charger in halls and I'm in the library for a 4-hour study session." Walking back is a 40-minute round trip. Asking a flatmate is unreliable. |
| **Severity** | 🟡 Medium — situational but intense when it happens |
| **Frequency** | 1-3 times/month per student |
| **Current Alternatives** | Walk back, ask a flatmate, buy a new charger. |
| **Our Solution** | Request a courier to bring it. £2-3. Arrives in 15 minutes. |

---

## Cross-Segment Pain Comparison Matrix

| Pain Point | Pharmacy | Hardware | C2C Reseller | Student | **Severity** |
|---|---|---|---|---|---|
| Patient/customer loss to online competitors | 🔴 Critical | 🟠 High | — | — | 🔴 |
| Compliance/liability risk in delivery | 🔴 Critical | — | — | — | 🔴 |
| Staff/owner leaving shop to deliver | 🟠 High | 🟠 High | — | — | 🟠 |
| No affordable same-day courier exists | 🟠 High | 🟠 High | 🟠 High | 🟡 Medium | 🟠 |
| Trust in stranger handling valuable items | 🔴 Critical | 🟠 High | 🟠 High | 🟡 Medium | 🟠 |
| Post office / shipping friction | — | — | 🟠 High | 🟡 Medium | 🟠 |
| Unsafe stranger meet-ups | — | — | 🟠 High | 🟡 Medium | 🟠 |
| Slow payment release | — | — | 🟡 Medium | — | 🟡 |
| Item exchange scheduling friction | — | — | — | 🟡 Medium | 🟡 |
| Unpredictable delivery costs | 🟡 Medium | 🟡 Medium | — | — | 🟡 |

---

## Current Alternatives Deep-Dive

### Why Every Existing Option Fails for Hyper-Local Same-Day Delivery

| Alternative | Speed | Cost | Trust/Tracking | Availability | **Fatal Flaw** |
|---|---|---|---|---|---|
| **Royal Mail** | 1-3 days | £3.49-6.85 | Tracking available | Universal | ❌ Too slow for same-day needs |
| **DPD/Hermes/Evri** | Next-day | £5-12 | Good tracking | Booking required | ❌ No same-day. Minimum £5. |
| **Uber Connect** | 30-60 min | £8-15 | Driver tracking | Limited cities | ❌ Too expensive for £5-30 items |
| **Deliveroo** | 30 min | N/A | Real-time tracking | Restaurant only | ❌ Doesn't carry packages |
| **Stuart/Gophr** | 1-2 hours | £8-20 | Basic tracking | London | ❌ B2B focused, expensive, complex integration |
| **Amazon Flex** | Same-day | "Free" (Prime) | Full tracking | Amazon items only | ❌ Only for Amazon purchases |
| **Self-delivery (car/walk)** | Immediate | Free (but time) | None | Always | ❌ Sender must leave their location |
| **Ask a friend/flatmate** | Variable | Free | None | Unreliable | ❌ No accountability, social capital cost |
| **TaskRabbit** | 1-4 hours | £15-30 | Basic | Limited | ❌ Way too expensive for a £5 delivery |

### The Gap in the Market

```
                    FAST (< 2 hours)
                         │
                         │
        ┌────────────────┼────────────────┐
        │                │                │
        │  Uber Connect  │                │
        │  £8-15         │                │
        │  Stuart/Gophr  │                │
        │  £8-20         │                │
        │                │                │
EXPENSIVE               │           AFFORDABLE
(> £8)   ────────────────┼──────────── (< £5)
        │                │                │
        │                │   ★ LOCAL-     │
        │                │   LOGISTICS    │
        │                │   PROTOCOL     │
        │                │   £3-5, <1hr   │
        │                │                │
        │  Royal Mail    │                │
        │  DPD/Hermes    │                │
        │  £3.49-12      │                │
        │                │                │
        └────────────────┼────────────────┘
                         │
                    SLOW (> 24 hours)
```

**We occupy the bottom-right quadrant: fast AND affordable.** This is possible because our couriers are walking/cycling on journeys they're already making, so marginal cost is near-zero. The True Marketplace model (couriers set prices) finds the natural equilibrium between speed, cost, and courier supply.

---

## Pain Intensity Validation Plan

Each pain point hypothesis needs to be validated through discovery interviews. Here's our validation approach:

| Pain Point | Validation Method | Sample Size | Success Criteria |
|---|---|---|---|
| Patient loss to online pharmacies | Pharmacist interviews | 15 pharmacies | ≥60% report losing 2+ patients/month to online competitors |
| Compliance risk in informal delivery | Pharmacist interviews + GPhC consultation | 15 pharmacies + 2 regulators | ≥70% use informal methods with no audit trail |
| Staff leaving shop to deliver | Shop owner interviews | 20 shops | ≥50% report regular self-delivery with operational disruption |
| No affordable same-day courier | All segment interviews | 50 total | ≥70% cannot name an affordable same-day option |
| Trust in stranger-couriers | All segment interviews + survey | 50 interviews + 200 surveys | ≥60% cite trust as #1 barrier to using gig delivery |
| Post office friction | C2C seller interviews | 10 sellers | ≥80% visit post office 2+/week and find it painful |
| Unsafe stranger meet-ups | C2C seller interviews | 10 sellers | ≥40% have avoided a local sale due to safety concerns |

---

*These pain points drive our [feature_prioritization.md](../product_validation/feature_prioritization.md) and [mvp_validation.md](../product_validation/mvp_validation.md). Validate severity via [interview_plan.md](interview_plan.md).*
