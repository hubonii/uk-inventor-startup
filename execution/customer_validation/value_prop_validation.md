# Value Proposition Validation

## Local-Logistics Protocol — Testing Whether Our Solution Resonates

> **Last Updated:** July 2026
> **Status:** Pre-MVP — Experiment designs ready for execution
> **Prerequisite:** Problem validation (H1-H4) must pass before running these tests

---

## Our Value Proposition

### For Merchants (Senders):
> **Get packages delivered locally in under 1 hour for under £5, with cryptographic proof of delivery — so you never lose a customer to "we don't deliver" again.**

### For Couriers:
> **Earn £3-8 per delivery by carrying packages on walks you're already taking. Set your own price. Get protected by £50 sender-visible collateral.**

### For Receivers:
> **Get your items same-day from local shops, with real-time tracking and a secure QR handshake — faster than Amazon, greener than a van.**

---

## Experiment 1: Landing Page Smoke Test

### Objective
Test whether the value proposition generates enough interest to warrant building an MVP. Measure: email signup rate (demand signal).

### Design

**What we build:** A single-page website with our value proposition, key benefits, and an email signup form ("Get early access").

**Three Landing Page Variants (A/B/C Test):**

| Variant | Headline | Subhead | Target Audience |
|---|---|---|---|
| **A: Speed + Price** | "Same-Hour Local Delivery. Under £5." | "Your local shops, delivered to your door by walking couriers. Faster than Amazon, cheaper than Uber." | General consumers |
| **B: Trust + Security** | "The Delivery Service That Proves It Was Delivered." | "Cryptographic QR handshakes. £50 courier deposits. Real-time tracking. Your packages, protected." | Trust-conscious senders (pharmacies, high-value) |
| **C: Green + Local** | "Zero-Emission Delivery From Your Neighbourhood." | "Walking and cycling couriers carry your parcels. No vans. No emissions. Just neighbours helping neighbours." | Sustainability-motivated audience |

**Traffic Source:**
- £200 Google Ads budget (targeting "local delivery London," "same day courier cheap")
- £100 Instagram/Facebook ads (targeting UCL students, Bloomsbury residents, Vinted sellers)
- £0 organic: Post in Reddit communities, student forums, pharmacy WhatsApp groups
- Total budget: £300

**Metrics:**

| Metric | Target | Measurement |
|---|---|---|
| Unique visitors | 500+ | Google Analytics |
| Email signup rate | ≥8% (40+ signups) | Signup form conversions |
| Best-performing variant | Statistically significant winner | A/B test tool (Google Optimize or Posthog) |
| Visitor source with highest intent | Segment by source | UTM tracking |
| Bounce rate | <60% | Google Analytics |

**Success Criteria:**
- ✅ ≥8% email signup rate (strong interest signal)
- ✅ ≥200 visitors from target geography (WC1/N1/NW1)
- ⚠️ 5-8% signup rate (moderate interest, need to refine messaging)
- ❌ <5% signup rate (value proposition doesn't resonate)

**Timeline:** 2 weeks (1 week to build + launch, 1 week to run ads and collect data)

### Landing Page Wireframe

```
┌─────────────────────────────────────────┐
│  Logo                          [Courier? →] │
├─────────────────────────────────────────┤
│                                         │
│  [HEADLINE - varies by variant]         │
│                                         │
│  [SUBHEAD - varies by variant]          │
│                                         │
│  [Email] [Get Early Access →]           │
│                                         │
├─────────────────────────────────────────┤
│  HOW IT WORKS                           │
│  1. 📦 Tap to request a courier         │
│  2. 🔐 Scan QR to confirm handover     │
│  3. 🚶 Courier walks it to recipient    │
│  4. ✅ QR handshake confirms delivery   │
├─────────────────────────────────────────┤
│  WHY IT'S SAFE                          │
│  • £50 courier deposit (slashed if      │
│    delivery fails)                      │
│  • Cryptographic proof of delivery      │
│  • Real-time tracking                   │
│  • Verified courier IDs                 │
├─────────────────────────────────────────┤
│  PRICING                                │
│  From £3 per delivery. Couriers set     │
│  their own rates. No surge pricing.     │
├─────────────────────────────────────────┤
│  [Email] [Join the Waitlist →]          │
│                                         │
│  "Launching in Bloomsbury, Summer 2026" │
└─────────────────────────────────────────┘
```

---

## Experiment 2: Concierge MVP (Manual Operations)

### Objective
Test whether real people will actually use the service when it exists — not just say they would.

### Design

**What we build:** Nothing. We manually operate the service using WhatsApp, Google Sheets, and our own legs.

**How it works:**
1. Sign up 3-5 pharmacies and 2-3 hardware shops from our interview pool
2. Give each merchant a WhatsApp number: "Text us when you need a delivery"
3. When a request comes in, a founder (or a hired student courier) picks up and delivers
4. Use a printed QR code on paper to simulate the handshake (founder verifies manually)
5. Track everything in Google Sheets: time, cost, distance, merchant feedback, recipient feedback

**Concierge MVP Workflow:**

```
Merchant WhatsApp  →  Founder receives  →  Founder/courier  →  Delivery  →  Manual QR
"Need delivery to      request, confirms     picks up package    walks/cycles    handshake
123 Euston Rd"         ETA, assigns          from shop          to address      + confirmation
                       courier
```

**Duration:** 4 weeks (or until 50 deliveries completed)

**Metrics:**

| Metric | Target | Measurement |
|---|---|---|
| Deliveries completed | 50+ | Manual count |
| Average delivery time | <60 minutes | Timestamp tracking |
| Merchant satisfaction | ≥8/10 | Post-delivery WhatsApp survey |
| Recipient satisfaction | ≥8/10 | Post-delivery SMS survey |
| Repeat usage (same merchant requests again) | ≥70% | Tracking |
| Cost per delivery (to us) | <£8 (subsidised) | Expense tracking |
| Courier earning per delivery | £3-5 | Payment records |
| Delivery failure rate | <5% | Incident tracking |

**Success Criteria:**
- ✅ ≥3 of 5 merchants use the service 3+ times in 4 weeks (habit formation)
- ✅ Average merchant satisfaction ≥8/10
- ✅ Average delivery time <60 minutes
- ✅ Zero delivery failures in first 20 deliveries
- ❌ Kill: <2 merchants use it more than once (no repeat demand)
- ❌ Kill: Average delivery time >90 minutes (courier supply insufficient)

**Budget:** £500 (courier payments for 50 deliveries at ~£5 each, subsidised)

---

## Experiment 3: Wizard of Oz App Test

### Objective
Test app UX with real users, but with manual backend operations. The merchant thinks they're using a real app; behind the scenes, a human is matching and dispatching.

### Design

**What we build:** A simple mobile app (or web app) with:
- Delivery request form (pickup address, dropoff address, item description)
- Fake "matching" screen (shows "Finding a courier..." for 30 seconds)
- Tracking screen (shows a generic map with a moving dot)
- QR code generation for handshake

**What we DON'T build:** Actual courier matching algorithm, payment processing, or route optimization. A founder manually:
- Receives the request notification
- Messages a courier on WhatsApp
- Manually updates the tracking screen
- Manually confirms delivery

**Duration:** 3 weeks, with 5-8 merchants

**Metrics:**

| Metric | Target | Measurement |
|---|---|---|
| App usability (can merchants create a request in <2 min?) | ≥90% success | Observation + timing |
| QR handshake completion rate | ≥85% | Manual tracking |
| "Real app" believability | ≥70% don't realise it's manual | Post-test debrief |
| Merchant NPS | ≥40 | NPS survey |

**Success Criteria:**
- ✅ Merchants can dispatch a delivery in <2 minutes without assistance
- ✅ QR handshake works smoothly ≥85% of the time
- ✅ NPS ≥40 (strong satisfaction signal)
- ❌ Kill: UX is too confusing; >30% need help to complete a request

---

## Experiment 4: B2B Subscription Pre-Sale

### Objective
Test whether merchants will commit money upfront (not just express interest) for a monthly subscription.

### Design

**What we do:** After a merchant has used the Concierge MVP 3+ times and expressed satisfaction, pitch them the B2B subscription:

> "We're launching a proper platform in [Month]. For £49/month, you get unlimited access to our courier network, a delivery dashboard, weekly invoicing, and CQC-ready audit logs. We're offering the first 10 pharmacies a Founder's Rate of £29/month for the first 6 months. Would you like to reserve your spot?"

**The Ask:** £29/month pre-commitment (charged when the platform launches). No contract, cancel anytime.

**Metrics:**

| Metric | Target | Measurement |
|---|---|---|
| Pre-sale conversion rate | ≥30% of merchants who used Concierge MVP | Close rate |
| Revenue committed | ≥£145/mo (5 × £29) | Stripe/payment tracking |
| Objections logged | All | Objection database |

**Success Criteria:**
- ✅ ≥3 of 8 merchants commit to £29/month pre-sale (strong signal)
- ✅ ≥1 merchant pays immediately (strongest signal)
- ⚠️ 1-2 merchants commit (moderate signal, investigate objections)
- ❌ Kill: 0 merchants commit after using the Concierge MVP

---

## Experiment 5: Courier Supply Activation Test

### Objective
Test whether we can recruit and retain enough couriers in the wedge to maintain <15 minute response times.

### Design

**What we do:**
1. Recruit 20 students via campus posters and Instagram ads
2. Onboard them with a 10-minute walkthrough (simulated, no real app)
3. Ask them to set their availability for 1 week
4. Send simulated delivery requests at various times
5. Measure response rate and time-to-accept

**Metrics:**

| Metric | Target | Measurement |
|---|---|---|
| Couriers recruited in 1 week | ≥20 | Signup count |
| Couriers who actually set availability | ≥60% (12) | Tracking |
| Response rate to simulated requests | ≥40% | Accept rate |
| Average time-to-accept | <5 minutes | Timestamp |
| Deposit willingness (surveyed, not charged) | ≥50% | Survey |

**Success Criteria:**
- ✅ ≥12 couriers set availability
- ✅ ≥40% response rate to requests
- ✅ Average time-to-accept <5 minutes
- ❌ Kill: <5 couriers set availability (supply pool too thin)

---

## Experiment 6: Value Prop Message Testing (Qualitative)

### Objective
Test which framing of our value proposition resonates most with each segment.

### Design

**What we do:** In the final 5 minutes of each discovery interview, show 3 value proposition cards and ask: "Which of these would make you most likely to try a new delivery service?"

**Cards:**

| Card | Message | Emphasis |
|---|---|---|
| **Card A** | "Same-hour delivery, under £5. No vans — just walking couriers." | Price + Speed |
| **Card B** | "Every delivery cryptographically verified. £50 courier deposit. Proof your package arrived." | Trust + Security |
| **Card C** | "Your local shops, delivered. Zero emissions. Support your high street." | Sustainability + Community |

**Analysis:**

| Segment | Expected Winner | Rationale |
|---|---|---|
| Pharmacies | Card B (Trust) | Compliance and liability are top concerns |
| Hardware/Print | Card A (Price + Speed) | Competing with Amazon on convenience |
| C2C Resellers | Card A (Price + Speed) | Price-sensitive, speed-motivated |
| Students | Card A (Price + Speed) or Card C (Green) | Price-sensitive but environmentally conscious |

**Metrics:** Card preference count by segment, qualitative feedback on why.

---

## Experiment Sequencing

```
                Week 1-8        Week 9-12       Week 13-16      Week 17-20
                ┌───────────┐   ┌───────────┐   ┌───────────┐   ┌───────────┐
Exp 1:          │ Landing   │   │           │   │           │   │           │
Landing Page    │ Page Test │   │           │   │           │   │           │
                └───────────┘   │           │   │           │   │           │
                                │           │   │           │   │           │
Exp 6:          │ Message   │   │           │   │           │   │           │
Message Test    │ Testing   │   │           │   │           │   │           │
(embedded in    │ (in       │   │           │   │           │   │           │
interviews)     │ interviews)│  │           │   │           │   │           │
                └───────────┘   │           │   │           │   │           │
                                │           │   │           │   │           │
Exp 5:          │           │   │ Courier   │   │           │   │           │
Courier Supply  │           │   │ Supply    │   │           │   │           │
                │           │   │ Test      │   │           │   │           │
                │           │   └───────────┘   │           │   │           │
                                                │           │   │           │
Exp 2:          │           │   │           │   │ Concierge │   │           │
Concierge MVP   │           │   │           │   │ MVP       │   │           │
                │           │   │           │   │ (4 weeks) │   │           │
                │           │   │           │   └───────────┘   │           │
                                                                │           │
Exp 3:          │           │   │           │   │           │   │ Wizard of │
Wizard of Oz    │           │   │           │   │           │   │ Oz App    │
                │           │   │           │   │           │   │ (3 weeks) │
                │           │   │           │   │           │   └───────────┘
                                                                
Exp 4:          │           │   │           │   │           │   │ B2B Pre-  │
B2B Pre-Sale    │           │   │           │   │           │   │ Sale      │
                │           │   │           │   │           │   └───────────┘
```

---

## Total Validation Budget

| Experiment | Budget | Duration |
|---|---|---|
| Exp 1: Landing Page | £300 (ads) + £50 (domain/hosting) = £350 | 2 weeks |
| Exp 2: Concierge MVP | £500 (courier subsidies) + £50 (materials) = £550 | 4 weeks |
| Exp 3: Wizard of Oz | £200 (basic app/Bubble.io) + £100 (courier payments) = £300 | 3 weeks |
| Exp 4: B2B Pre-Sale | £0 (conversation-based) | 1 week |
| Exp 5: Courier Supply | £100 (recruitment ads) + £50 (materials) = £150 | 1 week |
| Exp 6: Message Testing | £0 (embedded in interviews) | Parallel |
| **Total** | **£1,350** | **~12 weeks** |

---

## Go/No-Go Decision Matrix

After all experiments:

| Outcome | Decision |
|---|---|
| Landing page ≥8% signup + Concierge MVP ≥3 repeat merchants + ≥1 B2B pre-sale | ✅ **GO: Build real MVP** |
| Landing page 5-8% + Concierge MVP 2 repeat merchants + message refinement needed | ⚠️ **ITERATE: Refine value prop, run experiments again** |
| Landing page <5% + Concierge MVP <2 repeat merchants + 0 pre-sales | ❌ **PIVOT or KILL** |

---

*Results from these experiments feed directly into [mvp_validation.md](../product_validation/mvp_validation.md) and [assumption_mapping.md](../product_validation/assumption_mapping.md).*
