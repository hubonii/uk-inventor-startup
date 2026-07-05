# Jobs To Be Done (JTBD) Framework

## Local-Logistics Protocol — What Customers Are Hiring Us To Do

> **Last Updated:** July 2026
> **Framework:** Christensen/Ulwick Outcome-Driven Innovation
> **Status:** Pre-Validation Hypotheses

---

## Core Job Statement

> **When** people need to move a physical item across a short distance in a city, **they hire** a solution that gets it there quickly, affordably, and without worry that the item will be lost, damaged, or stolen.

The Local-Logistics Protocol is "hired" to do this job when:
- The distance is too far to walk but too short to justify traditional courier pricing
- The sender doesn't know or trust the person carrying it
- Speed matters (same-day or same-hour)
- The item has non-trivial value (£5-£500+)

---

## 1. Functional Jobs

These are the practical, measurable outcomes customers need.

### Job F1: Get a Package Delivered Same-Day for Under £5

**Job Statement:** Minimise the time and cost of moving a physical item from point A to point B within the same urban area, same day.

| Element | Detail |
|---|---|
| **Job Performer** | Sender (merchant or individual) |
| **Desired Outcome** | Package arrives at destination within 2 hours, costing <£5 |
| **Current Overserved** | Royal Mail next-day (too slow but affordable at £3.49) |
| **Current Underserved** | Uber Connect same-day (fast but £8-15, no custody tracking) |
| **Importance** | 9/10 — this is the core functional job |
| **Satisfaction with current solutions** | 3/10 — gap between speed and price is enormous |

**By Segment:**

| Segment | 'When I...' | 'I want to...' | 'So I can...' |
|---|---|---|---|
| **A: Pharmacy** | When I have a patient who can't collect their prescription today | I want to dispatch it to their home within 2 hours for under £5 | So I can retain the patient, meet NHS delivery obligations, and avoid leaving the dispensary counter |
| **B: Hardware/Print** | When a customer buys something too bulky to carry or can't visit | I want to get it to them same-day at a reasonable cost | So I can close the sale instead of losing it to Amazon/Argos |
| **C: C2C Reseller** | When I sell an item on Vinted to someone 3 miles away | I want to ship it locally, same-day, cheaper than Royal Mail | So I can avoid the post office queue, get faster payment release, and get a better buyer rating |
| **D: Student** | When I need to send a textbook/item to another student across campus | I want someone to carry it for me for ~£3 | So I can stay in the library and not waste 40 minutes walking |

### Job F2: Prove the Package Was Delivered to the Right Person

**Job Statement:** Eliminate disputes about whether delivery occurred by creating irrefutable, timestamped proof of handover.

| Element | Detail |
|---|---|
| **Job Performer** | Sender, Receiver, Platform (for dispute resolution) |
| **Desired Outcome** | Cryptographic, timestamped, GPS-tagged proof that the right person received the right package |
| **Current Underserved** | "Left with neighbour" / photo of doorstep (easily disputed) |
| **Importance** | 8/10 — trust is the #1 barrier to using stranger-couriers |
| **Satisfaction with current solutions** | 2/10 — Royal Mail "sorry we missed you" cards are universally hated |

| Segment | 'When I...' | 'I want to...' | 'So I can...' |
|---|---|---|---|
| **A: Pharmacy** | When I hand a prescription to an unvetted courier | I want cryptographic proof it reached the patient | So I can satisfy CQC audit requirements and my professional liability |
| **B: Hardware/Print** | When I send a £200 power tool with a stranger | I want proof the customer received it | So I can defend against "item never arrived" chargebacks |
| **C: C2C Reseller** | When I hand my item to someone I've never met | I want both parties to confirm the handover digitally | So I can release payment and avoid Vinted/Depop disputes |
| **D: Student** | When I lend my £80 textbook to someone I don't know well | I want a record that they received it | So I can get it back or prove they have it |

### Job F3: Find a Courier Quickly Without Pre-Booking

**Job Statement:** Access on-demand courier availability within 10 minutes, without scheduling in advance.

| Segment | 'When I...' | 'I want to...' | 'So I can...' |
|---|---|---|---|
| **A: Pharmacy** | When a patient calls and needs their medication urgently | I want to tap a button and have a courier arrive in 10 minutes | So I can respond to urgent needs without advance planning |
| **B: Hardware/Print** | When a customer says "I need this delivered now" | I want to dispatch immediately, not schedule for tomorrow | So I can match the instant gratification of Amazon |
| **C: C2C Reseller** | When I sell something and the buyer wants it today | I want a courier to come to my flat within 30 minutes | So I can ship it without leaving home or going to the post office |
| **D: Student** | When I forget my laptop charger in halls and I'm in the library | I want to find someone heading my way in the next 15 minutes | So I can keep studying without a 40-minute round trip |

### Job F4: Get Paid Fairly for Carrying Packages (Courier-Side)

**Job Statement:** Earn supplemental income by carrying packages along routes I'm already walking/cycling, at a rate I find fair.

| Element | Detail |
|---|---|
| **Job Performer** | Courier |
| **Desired Outcome** | Earn £5-15/hour in supplement income with minimal detour from existing journeys |
| **Current Overserved** | Deliveroo/UberEats (high intensity, long hours, low per-drop pay) |
| **Current Underserved** | No gig platform exists for hyper-local, walking-distance package delivery |
| **Importance** | 8/10 — couriers won't supply if economics don't work |

| Courier Type | 'When I...' | 'I want to...' | 'So I can...' |
|---|---|---|---|
| **Student Walking to Campus** | When I'm already walking from halls to the library | I want to pick up a package en route and earn £3-4 | So I can make money from a journey I'm already making |
| **Gig Worker Between Jobs** | When I'm waiting for my next Deliveroo order | I want to fill downtime with a quick package drop | So I can maximise my hourly earnings |
| **Local Resident Running Errands** | When I'm heading to the shops anyway | I want to carry a parcel for someone along my route | So I can earn a few pounds with zero additional effort |

---

## 2. Emotional Jobs

These are about how customers want to *feel* during and after the experience.

### Job E1: Trust That a Stranger Won't Steal My Package

**Core Emotion:** Security, peace of mind, reduced anxiety

This is the **#1 emotional job** and the reason our cryptographic chain-of-custody protocol exists. Every segment has a trust gap when handing valuable items to unknown people.

| Segment | 'When I...' | 'I want to feel...' | 'So I can...' |
|---|---|---|---|
| **A: Pharmacy** | When I entrust a controlled substance to someone I've never met | Confident that there's a financial and cryptographic guarantee of delivery | Protect my professional licence and sleep at night |
| **B: Hardware/Print** | When I hand a £150 item to a stranger with a phone | Assured that if anything goes wrong, I'm covered | Offer delivery without the anxiety of potential loss |
| **C: C2C Reseller** | When I give my vintage jacket to a courier at my door | Safe that the £50 courier deposit protects me | Sell locally without the fear that comes with meeting strangers |
| **D: Student** | When I send my only copy of lecture notes with someone from a WhatsApp group | Comfortable that there's accountability | Share and trade without the social awkwardness of chasing people |

**Trust Architecture That Addresses This Job:**

```
┌─────────────────────────────────────────────────────┐
│              TRUST LAYER STACK                       │
├─────────────────────────────────────────────────────┤
│ Layer 4: Financial — £50 collateral stake (slashed  │
│          if delivery fails)                         │
│ Layer 3: Cryptographic — TOTP QR handshake proves   │
│          custody transfer                           │
│ Layer 2: Identity — Verified ID + selfie on signup  │
│ Layer 1: Reputation — Rating system with history    │
└─────────────────────────────────────────────────────┘
```

### Job E2: Feel in Control of the Delivery Process

**Core Emotion:** Agency, empowerment, transparency

| Segment | 'When I...' | 'I want to feel...' | 'So I can...' |
|---|---|---|---|
| **A: Pharmacy** | When a prescription is in transit | In control — knowing exactly where it is, in real-time | Reassure patients who call asking "where's my medication?" |
| **B: Hardware/Print** | When I've dispatched a customer's order | Confident I can see the courier's location and ETA | Update the customer and manage expectations |
| **C: C2C Reseller** | When my parcel is being carried across town | Calm, because I can track it live | Stop refreshing the app and get on with my day |
| **D: Student** | When someone is bringing my charger to the library | Reassured that they're actually coming | Focus on studying instead of sending "are you still coming?" texts |

### Job E3: Not Feel Like I'm Exploiting the Courier

**Core Emotion:** Ethical comfort, fairness

| Segment | 'When I...' | 'I want to feel...' | 'So I can...' |
|---|---|---|---|
| **All Senders** | When I pay £4 for a delivery | Confident the courier is being fairly compensated | Use the service without guilt about gig economy exploitation |
| **All Couriers** | When I accept a delivery job | Respected — I set my own rate and I'm not being algorithmically squeezed | Continue supplying my labour without resentment |

**Our True Marketplace model directly addresses this:** Couriers set their own prices. The platform takes a transparent 15% fee. No surge pricing manipulation, no hidden rate cuts. This is both an ethical stance and a legal defence (Uber v Aslam).

---

## 3. Social Jobs

These are about how customers want to be *perceived* by others.

### Job S1: Feel Green and Sustainable

**Core Social Signal:** "I'm reducing emissions by using walking/cycling couriers instead of vans"

| Segment | 'When I...' | 'I want to...' | 'So I can...' |
|---|---|---|---|
| **A: Pharmacy** | When I tell patients about our delivery service | Say it's zero-emission, walking/cycling delivery | Differentiate from Amazon's diesel vans and appeal to health-conscious patients |
| **B: Hardware/Print** | When I market my shop's delivery option | Advertise "local, green, same-day delivery" | Attract environmentally conscious customers in gentrified London postcodes |
| **C: C2C Reseller** | When I list "delivery available" on my Vinted profile | Feel good that I'm using a sustainable option, not adding a van to the road | Signal environmental values to buyers |
| **D: Student** | When I use the platform to send/receive items | Tell friends I use a peer-to-peer, walking-based delivery network | Signal alignment with sustainability values common in university culture |

**Quantifiable Sustainability Claim:**
- Average Local-Logistics drop: 1.2 km, carried by foot/bike = **0g CO₂**
- Equivalent Royal Mail delivery: 0.5 kg CO₂ (shared van route average)
- Equivalent Uber Connect: 1.2 kg CO₂ (single car trip)

### Job S2: Support Local, Independent Businesses

**Core Social Signal:** "I'm helping my local high street survive"

| Segment | 'When I...' | 'I want to...' | 'So I can...' |
|---|---|---|---|
| **B: Hardware/Print** | When I use this platform to offer delivery | Tell customers it's a local tech startup, not Amazon | Strengthen the "shop local" narrative |
| **D: Student** | When I choose to buy from the local print shop instead of ordering online | Feel that I'm part of the community, not just a consumer | Build social capital in my university neighbourhood |

### Job S3: Be Seen as a Smart, Tech-Forward Business

**Core Social Signal:** "We use cutting-edge technology for secure delivery"

| Segment | 'When I...' | 'I want to...' | 'So I can...' |
|---|---|---|---|
| **A: Pharmacy** | When I explain our delivery process to a CQC inspector | Show a digital chain-of-custody log with cryptographic verification | Be seen as progressive and compliant, not old-fashioned |
| **B: Hardware/Print** | When competitors still say "sorry, we don't deliver" | Offer instant, app-based dispatch | Be the most modern shop on the high street |

---

## Job Priority Map

Plotting importance (x-axis) against current satisfaction (y-axis) reveals where the biggest opportunities lie:

```
High Satisfaction
    │
    │                    ● F4 (Courier earnings)
    │                      [Deliveroo/UberEats exist
    │                       but don't fit this niche]
    │
    │         ● S1 (Green/sustainable)
    │           [No strong current option]
    │
    │
    │                              ● F3 (Find courier quickly)
    │                                [Uber exists but overpriced]
    │
    │
    │
    │
    │                                        ● F1 (Same-day <£5)
    │                                          [MASSIVE GAP]
    │
    │                                    ● F2 (Prove delivery)
    │                                      [Nothing works well]
    │
    │                                  ● E1 (Trust stranger)
    │                                    [Huge anxiety, no solution]
    │
Low Satisfaction ──────────────────────────────────────── High Importance
```

**Key Insight:** The three jobs in the bottom-right quadrant — same-day affordable delivery (F1), proof of delivery (F2), and trust in stranger-couriers (E1) — represent the core opportunity space. Our cryptographic chain-of-custody protocol directly addresses F2 and E1, while the True Marketplace pricing model enables F1 by keeping costs low through walking/cycling couriers.

---

## Outcome Statements (Ulwick Format)

For use in quantitative surveys to measure importance and satisfaction:

### Senders

| # | Outcome Statement | Expected Importance | Expected Satisfaction |
|---|---|---|---|
| 1 | Minimise the time it takes to get a package delivered locally | 9 | 3 |
| 2 | Minimise the cost of same-day local delivery | 9 | 2 |
| 3 | Minimise the risk of the package being lost or stolen in transit | 10 | 4 |
| 4 | Minimise the effort to dispatch a package (steps, forms, packaging) | 7 | 5 |
| 5 | Minimise the time to find an available courier | 8 | 3 |
| 6 | Minimise uncertainty about when the package will arrive | 8 | 4 |
| 7 | Minimise the likelihood of a delivery dispute | 9 | 3 |
| 8 | Maximise confidence that the recipient personally received the item | 9 | 2 |
| 9 | Minimise the environmental impact of the delivery | 5 | 3 |
| 10 | Minimise the time to resolve a problem if something goes wrong | 7 | 2 |

### Couriers

| # | Outcome Statement | Expected Importance | Expected Satisfaction |
|---|---|---|---|
| 1 | Maximise earnings per hour of active delivery | 9 | 3 |
| 2 | Minimise detour from my existing route | 8 | 1 |
| 3 | Minimise the risk of being falsely accused of theft/damage | 9 | 4 |
| 4 | Maximise flexibility in choosing when and where to work | 8 | 6 |
| 5 | Minimise the complexity of the pickup/delivery process | 7 | 5 |
| 6 | Minimise the time waiting for a delivery to become available | 7 | 3 |
| 7 | Maximise transparency about what I'm carrying and where | 8 | 4 |
| 8 | Minimise the financial risk of participating (deposit concerns) | 7 | 2 |

---

## Switch Triggers & Hiring Criteria

What causes someone to "fire" their current solution and "hire" us?

### Push Forces (Away from current solution)

1. **Royal Mail:** "I spent 20 minutes queueing just to send a package 2 miles away"
2. **Uber Connect:** "They charged me £12 for a 10-minute delivery"
3. **DIY delivery (pharmacist driving):** "I had to close the shop for 30 minutes to deliver one prescription"
4. **Meeting strangers (C2C):** "I felt unsafe meeting a buyer at the tube station at 8pm"
5. **Not delivering at all:** "I lost the sale because the customer couldn't carry it home"

### Pull Forces (Towards our solution)

1. "A courier can come in 10 minutes for under £5"
2. "The QR handshake proves delivery happened — no more disputes"
3. "The £50 deposit means the courier has skin in the game"
4. "I can track the package in real-time"
5. "I'm supporting a green, local delivery network"

### Anxieties (Preventing switch)

1. "What if the courier steals my package?" → Addressed by £50 stake + cryptographic proof
2. "What if no couriers are available?" → Addressed by dense University Wedge launch
3. "Is this legal? Is the courier insured?" → Addressed by True Marketplace model + goods-in-transit coverage
4. "What if my customer has a bad experience?" → Addressed by real-time tracking + rating system
5. "I don't want to learn another app" → Addressed by 3-tap dispatch flow

### Habits (Preventing switch)

1. "I've always used Royal Mail" → Counter: show total annual time/cost waste
2. "My staff know the current process" → Counter: 10-minute onboarding, QR flow is simpler than a till
3. "I don't trust tech companies" → Counter: local founder, in-person onboarding, human support

---

*These JTBD hypotheses must be validated through customer discovery interviews. See [interview_questions.md](interview_questions.md) for the question bank designed to test each job.*
