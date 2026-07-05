# Objection Database

## Local-Logistics Protocol — Every Reason They'll Say No (And How We Respond)

> **Last Updated:** July 2026
> **Status:** Pre-Validation — Rebuttals are hypothetical; update with real interview data
> **Usage:** Reference for sales conversations, investor pitches, and product decisions

---

## How to Use This Database

1. Before every sales conversation, review the objections for that stakeholder type
2. After every conversation, add new objections you encountered
3. Track objection frequency — the most common ones should shape our product and messaging
4. Test rebuttals — if a rebuttal doesn't work, revise it

---

## A. Sender (Merchant) Objections

### A1: Trust & Safety

| # | Objection | Root Cause | Rebuttal |
|---|---|---|---|
| A1.1 | "What if the courier steals my package?" | Fundamental trust deficit with strangers | "Every courier puts down a £50 refundable deposit. If a delivery fails, the deposit is slashed. Plus, our TOTP QR handshake creates cryptographic proof of every handover — the courier can't deny they had the package." |
| A1.2 | "I don't know these people. How can I trust them?" | No brand/reputation proxy for couriers | "We verify every courier's identity (government ID + selfie match). They have a rating history visible to you before you accept them. And the £50 deposit means they have real money on the line." |
| A1.3 | "What about insurance? What if something is damaged?" | Liability and compensation concerns | "We provide goods-in-transit coverage up to £250 per delivery. For higher-value items, we offer an optional insurance top-up. The QR handshake photos provide evidence for any claim." |
| A1.4 | "I can't hand prescriptions to random strangers. It's a compliance issue." | GPhC/CQC regulatory requirements | "Our chain-of-custody protocol creates a digital audit trail that's actually stronger than your current paper records. Every handover is timestamped, GPS-tagged, and cryptographically verified. We're working with pharmacy compliance consultants to ensure it meets CQC standards." |
| A1.5 | "What if the courier doesn't show up?" | Reliability anxiety | "We have a pool of active couriers in your area. If your matched courier cancels, we auto-rematch within 3 minutes. In the rare case no courier is available, we notify you immediately so you can make other arrangements." |

### A2: Pricing & Economics

| # | Objection | Root Cause | Rebuttal |
|---|---|---|---|
| A2.1 | "£4-5 per delivery is too expensive." | Price anchoring to "free" or "I do it myself" | "You're currently spending 25 minutes per delivery run. At your hourly rate, that's £12 in lost dispensing time. Our £4 delivery saves you £8 in opportunity cost every time." |
| A2.2 | "Why do I need a £49/month subscription AND per-delivery fees?" | Perceived double-charging | "The subscription gives you the dashboard, weekly invoicing, CQC audit logs, and priority support. Without it, you can still use the platform on a pay-per-drop basis — the subscription is optional but saves you admin time." |
| A2.3 | "My patients can't afford £4 delivery." | Concern about passing costs to price-sensitive patients | "Many pharmacies absorb the delivery cost for vulnerable patients — it's cheaper than losing them to online pharmacies. Alternatively, you can charge a subsidised rate (£2) and absorb the difference. The NHS prescription revenue you retain far exceeds the delivery cost." |
| A2.4 | "I can just ask my staff member to drop it off." | Sunk cost fallacy (staff is "free") | "Your staff member's time has a cost, even if it's not visible. When they're delivering, they're not serving walk-in customers. And there's no proof of delivery — if a patient claims they didn't receive it, you have no protection." |

### A3: Operational & Technical

| # | Objection | Root Cause | Rebuttal |
|---|---|---|---|
| A3.1 | "I don't have time to learn a new app." | Change resistance, tech anxiety | "Our dispatch flow is 3 taps: enter address, describe package, confirm. We'll set everything up for you in 15 minutes and leave a quick-reference card at your counter. If your staff can use WhatsApp, they can use this." |
| A3.2 | "We don't have Wi-Fi in the shop." | Infrastructure limitation | "The app works on mobile data — no Wi-Fi needed. It also works offline for creating delivery requests, syncing when you're back online." |
| A3.3 | "What if my customer doesn't have a smartphone for the QR?" | Recipient technology gap (especially elderly patients) | "We offer a PIN-based fallback. The recipient receives a 4-digit code by SMS. They tell the courier the code, and the delivery is confirmed. No smartphone needed." |
| A3.4 | "I need delivery at 7am before we open. Your couriers won't be around." | Operating hours mismatch | "We currently focus on 8am-8pm delivery. As our courier pool grows, we'll expand hours. For now, you can schedule deliveries in advance so a courier is pre-assigned for early morning slots." |

---

## B. Courier Objections

| # | Objection | Root Cause | Rebuttal |
|---|---|---|---|
| B1.1 | "£50 deposit? That's a lot of money." | Upfront financial barrier | "It's fully refundable when you stop couriering. You'll earn it back in 5-8 deliveries. The deposit is what makes senders trust you — it's why they'll hand you their packages instead of using Royal Mail." |
| B1.2 | "What if the customer says I didn't deliver and I lose my £50?" | Fear of false accusations | "The QR handshake protects you. When the recipient scans your QR code, it creates irrefutable proof that the handover happened. No one can falsely claim non-delivery." |
| B1.3 | "£3-4 per delivery isn't enough." | Earnings expectation anchored to Deliveroo | "£3-4 for a 10-minute walk on a route you're already taking. That's £18-24/hour equivalent — much higher than Deliveroo (£9-11/hr). You're not making a dedicated trip; you're monetising a walk you'd take anyway." |
| B1.4 | "How many deliveries will actually be available?" | Demand uncertainty | "We're launching in a dense area specifically to ensure enough demand. In the Bloomsbury wedge, we expect 50-100+ deliveries per day. You can see real-time demand on your heatmap before you even accept a job." |
| B1.5 | "I don't want to carry someone's heavy stuff." | Physical burden concern | "You see the package description and estimated weight before accepting. You choose which deliveries to take. If it says '2 bags of cement,' you can skip it." |
| B1.6 | "What if I get a bad rating unfairly?" | Reputation risk | "Ratings are two-way — you rate senders too. If a sender consistently gives unfair ratings, we flag it. And one bad rating doesn't tank your score; we use a rolling average." |
| B1.7 | "Am I employed by you? Do I need to pay tax?" | Employment status anxiety | "You're an independent contractor. You set your own prices, your own hours, and you're never required to accept a delivery. We provide tax guidance in the app. If you earn over £1,000/year, you'll need to register for self-assessment — we'll remind you and point you to free resources." |
| B1.8 | "What if the package is illegal?" | Legal liability concern | "All senders are verified. Packages are described at dispatch. You can inspect the package before accepting (it won't be sealed opaquely). If anything seems suspicious, you can decline and report it with zero penalty." |

---

## C. Merchant (B2B Sales) Objections

| # | Objection | Root Cause | Rebuttal |
|---|---|---|---|
| C1.1 | "We already have a courier service." | Incumbent solution | "Who do you use? How much does it cost? Most courier services charge £8-15 per delivery and require pre-booking. We're half the price and on-demand. Happy to run a side-by-side test for a week — no commitment." |
| C1.2 | "Delivery isn't a priority for us right now." | Underestimating the problem | "I understand. Quick question: in the last month, how many customers said 'I'll come back later' and didn't? If it's more than 2-3, delivery might be more of a priority than you think." |
| C1.3 | "What happens if your startup fails? I'll have built a dependency." | Vendor risk | "Fair concern. We don't lock you into anything — no contracts, cancel anytime. And even if we disappeared tomorrow, you'd go back to your current process. There's zero migration risk." |
| C1.4 | "I need to talk to my accountant/partner/manager first." | Delayed decision (stalling) | "Of course. Would it help if I sent you a one-page summary with pricing and how it works? What's a good time for me to follow up — end of this week?" |
| C1.5 | "My customers won't pay for delivery." | Assumption about customer price sensitivity | "Have you tested that? In our research, 65% of customers said they'd pay £4-6 for same-day local delivery rather than making a second trip. Would you like to test it with a sign on your counter: 'Same-day delivery available — £4.50'?" |
| C1.6 | "I'd rather hire my own delivery person." | Control preference | "A dedicated driver costs £25-30K/year including National Insurance. At £4.50/drop and 5 deliveries/day, we cost £5,850/year — one-fifth the price. And you only pay when you use it." |

---

## D. Investor Objections

| # | Objection | Root Cause | Rebuttal |
|---|---|---|---|
| D1.1 | "This is just Uber Connect. What's different?" | Competitive positioning confusion | "Uber Connect is a taxi that carries a package. We're a walking/cycling courier network with a cryptographic chain-of-custody protocol. Our couriers cost 80% less (they're walking anyway), our trust layer is fundamentally different (collateralised staking + TOTP QR), and we're building B2B SaaS revenue on top." |
| D1.2 | "How do you solve the chicken-and-egg problem?" | Classic marketplace concern | "Geographic density. We launch in a 2km² wedge around UCL where both supply (students) and demand (pharmacies, shops) are co-located. We seed supply by recruiting student couriers through campus channels and seed demand with concierge-style merchant onboarding. 50-100 drops/day in 2km² creates liquidity." |
| D1.3 | "The margins seem thin. £0.57/drop is nothing." | Unit economics concern | "£0.57 per drop × 200 drops/day = £114/day = £2,964/month from drops alone. Add £735/month in B2B SaaS subscriptions (higher margin). At scale, marginal cost per drop approaches zero — we're just routing messages. The thin margin is by design: it keeps the market defensible." |
| D1.4 | "What stops Amazon from crushing you?" | Competitive moat concern | "Amazon is building logistics for Amazon products. They have zero interest in carrying a pharmacy prescription 0.8 miles. Our moat is the trust protocol (TOTP + staking), the B2B integration with pharmacy/retail POS systems, and the local network effects in dense wedges. It's Shopify vs Amazon: we enable local merchants, not compete with them." |
| D1.5 | "This is a courier company, not a tech company." | Valuation / category concern (especially for visa) | "We're a SaaS trust infrastructure company. The courier network is a distribution channel for our cryptographic chain-of-custody protocol. The same protocol could be licensed to any sector that needs stranger-to-stranger trust: property key handover, event ticket transfer, secondhand luxury authentication. We just happen to start with parcels." |
| D1.6 | "What about worker classification? Uber v Aslam." | Employment law risk | "Our True Marketplace model is structurally different from Uber's. Couriers set their own prices (true market-making, not algorithmic control). They choose when, where, and whether to work. They're never penalised for declining. There's no login requirement, no shift system, no uniform. We've designed the model specifically to satisfy the Autoclenz/Aslam criteria for genuine self-employment." |
| D1.7 | "The TAM seems small. A 2km² wedge?" | Scale concern | "The wedge is our beachhead, not our TAM. London has 120+ similar university wedges. UK cities with 20K+ students: 80+. The same model works in any dense urban area globally. But we don't pitch a $10B TAM — we pitch a £325K beachhead that we dominate first, then expand." |
| D1.8 | "Why would I invest pre-revenue?" | Stage concern | "You're not investing in revenue. You're investing in a validated problem (50 interviews), a working protocol (TOTP + staking architecture), a paying pilot (concierge MVP with 3+ pharmacies), and a founder with domain conviction. The revenue follows the validation." |
| D1.9 | "Is the founder visa a risk? What if it's not granted?" | Immigration/visa dependency | "The Innovator Founder Visa requires endorsement from a Home Office-approved body. Our SaaS trust infrastructure angle is strong — it's a genuine innovation with IP potential. We've engaged [endorsing body] and received positive preliminary feedback. Even in the unlikely event of visa delay, the company is UK-registered and can operate with a co-founder or hire." |
| D1.10 | "How do you handle fraud? What if couriers and recipients collude?" | Fraud risk | "Collusion requires the courier and recipient to share the TOTP code in advance, which they can't because it's time-based and generated at the moment of handover. The GPS verification confirms the courier was physically at the delivery location. And the £50 deposit means the courier has more to lose than gain from a single fraudulent transaction." |

---

## E. Regulator Objections

| # | Objection | Root Cause | Rebuttal |
|---|---|---|---|
| E1.1 | "Prescription delivery requires proper chain of custody." (GPhC/CQC) | Regulatory compliance | "Our TOTP QR protocol creates a chain of custody that is more robust than paper-based systems: every handover is timestamped, GPS-tagged, and cryptographically verified. We'd welcome the opportunity to demonstrate the system to your inspection team." |
| E1.2 | "Are your couriers trained for pharmaceutical delivery?" | Training requirements | "Our courier onboarding includes a mandatory module on safe handling of pharmacy packages, including temperature-sensitive items and patient confidentiality. We can share our training materials for review." |
| E1.3 | "How do you handle controlled substances?" | Controlled drug regulation | "For Schedule 2-5 controlled drugs, we implement additional safeguards: tamper-evident packaging, no-contact handover (package is sealed and must be signed for with additional ID verification), and real-time GPS tracking with geofencing. However, we recommend pharmacies continue in-person delivery for Schedule 2 CDs until our protocol is formally reviewed." |
| E1.4 | "What about GDPR? You're sharing patient addresses with couriers." | Data protection | "Courier access to delivery addresses is minimised — they see the address only during the active delivery, and it's purged from their device after completion. Patient names are never shared; we use anonymised delivery IDs. Our data protection officer has reviewed the process for GDPR compliance." |
| E1.5 | "Are your couriers self-employed or workers?" (HMRC) | Employment classification | "Our couriers meet all criteria for genuine self-employment under the Autoclenz/Aslam framework: they set their own prices, choose their own hours, face no penalties for declining work, can send substitutes, and provide their own equipment. We do not exercise control over the manner of their work. We maintain this classification actively and would welcome HMRC review." |
| E1.6 | "What about goods-in-transit insurance?" | Insurance requirements | "All deliveries are covered by our goods-in-transit insurance policy (underwritten by [TBC]). Standard coverage is up to £250 per item. For higher-value items, senders can purchase additional coverage at the point of dispatch." |

---

## Objection Frequency Tracker

Update this table after every sales conversation, interview, or investor meeting:

| Objection | Stakeholder | Times Heard | Rebuttal Effective? | Action Needed |
|---|---|---|---|---|
| A1.1 (courier theft) | Sender | 0 | TBD | — |
| A2.1 (too expensive) | Sender | 0 | TBD | — |
| B1.1 (£50 deposit) | Courier | 0 | TBD | — |
| D1.2 (chicken & egg) | Investor | 0 | TBD | — |
| D1.5 (not a tech company) | Investor | 0 | TBD | — |
| ... | | | | |

---

*This database should be treated as a living document. After each customer interaction, add new objections and update rebuttal effectiveness scores. The most frequently encountered objections with weak rebuttals should trigger product changes (see [feature_prioritization.md](../product_validation/feature_prioritization.md)).*
