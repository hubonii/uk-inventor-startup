# Referral Program — Local-Logistics Protocol

## Program Overview

The Local-Logistics referral program is a **double-sided incentive system** designed to drive organic growth from both sender and courier sides of the marketplace. The program is architected for viral growth while maintaining positive unit economics.

---

## 1. Sender Referral Program

### 1.1 Mechanics

```
┌─────────────────────────────────────────────────────────┐
│                  SENDER REFERS SENDER                   │
│                                                         │
│  Referrer (existing sender)                             │
│    └─→ Shares unique referral code/link                 │
│         └─→ Referee (new sender) signs up               │
│              └─→ Referee completes first drop            │
│                   └─→ BOTH get £3 credit                │
│                        ├─→ Referrer: £3 in-app credit   │
│                        └─→ Referee: £3 off first drop   │
└─────────────────────────────────────────────────────────┘
```

### 1.2 Program Details

| Parameter | Value |
|-----------|-------|
| Referrer reward | £3 in-app credit |
| Referee reward | £3 credit (applied to first delivery fee) |
| Activation trigger | Referee completes their first drop |
| Credit expiry | 90 days from issue |
| Max referrals per user | 20 per month |
| Fraud prevention | Unique phone number + unique device ID required per account |
| Referral code format | `[USERNAME]-INVITE` (e.g., `SARAH-INVITE`) |
| Shareable link | `locallogistics.co/r/[CODE]` |

### 1.3 Sharing Mechanisms

| Method | Implementation | Expected % of Shares |
|--------|---------------|---------------------|
| In-app share sheet | Native iOS/Android share with pre-written message | 40% |
| WhatsApp direct share | Deep link to WhatsApp with prefilled text | 30% |
| SMS | One-tap SMS with referral link | 10% |
| Instagram Stories | Branded shareable card with QR code | 10% |
| Copy link | Manual copy-paste for any platform | 10% |

### 1.4 Pre-Written Share Messages

**WhatsApp/SMS:**
> Hey! I've been using LocalLogistics to send stuff around Bloomsbury — it's like Uber but for packages. Use my code [CODE] and we both get £3 off 📦 [link]

**Instagram Story Card:**
> "I just sent [item] across campus in 18 minutes 🚀 Get £3 off your first delivery → [QR code]"

### 1.5 In-App Referral Experience

```
┌──────────────────────────────────┐
│  🎁 Get £3 — Give £3             │
│                                  │
│  Share your code with friends    │
│  and you BOTH get £3 credit      │
│  when they send their first      │
│  package.                        │
│                                  │
│  Your code: SARAH-INVITE         │
│                                  │
│  [📱 Share via WhatsApp]         │
│  [📤 Share via...]               │
│  [📋 Copy Link]                  │
│                                  │
│  ─────────────────────────────   │
│  Your referral stats:            │
│  Invites sent: 12                │
│  Friends joined: 4               │
│  Credits earned: £12             │
│                                  │
│  ─────────────────────────────   │
│  🏆 Top referrers this month:    │
│  1. @james — 8 referrals         │
│  2. @priya — 6 referrals         │
│  3. @tom — 5 referrals           │
└──────────────────────────────────┘
```

---

## 2. Courier Referral Program

### 2.1 Mechanics

```
┌─────────────────────────────────────────────────────────┐
│                COURIER REFERS COURIER                   │
│                                                         │
│  Referrer (existing courier)                            │
│    └─→ Shares unique courier referral code              │
│         └─→ Referee (new courier) signs up              │
│              └─→ Referee completes KYC                  │
│                   └─→ Referee completes 5 drops         │
│                        └─→ Referrer gets £5 bonus       │
│                             (Referee gets £5 too)       │
└─────────────────────────────────────────────────────────┘
```

### 2.2 Program Details

| Parameter | Value |
|-----------|-------|
| Referrer reward | £5 cash bonus (added to next payout) |
| Referee reward | £5 bonus after completing 5th drop |
| Activation trigger | Referee completes 5 drops (proves engagement) |
| Max referrals per courier | 10 per month |
| Fraud prevention | Unique KYC identity required; referred courier must complete drops in different locations than referrer |
| Referral code format | `COURIER-[NAME]-[4DIGITS]` |

### 2.3 Why 5 Drops (Not 1)?

The courier referral requires 5 completed drops before payout because:
1. **Quality filter:** Ensures the referred courier is genuinely engaged, not just signing up for a quick bonus
2. **Staking pipeline:** By drop 5, the courier reaches the staking unlock threshold — creating a committed user
3. **LTV validation:** A courier who completes 5 drops has a 75% probability of being active at Day 30 (vs 30% for 1-drop couriers)
4. **Economics:** £5 cost is recovered within 2 additional drops of platform fee (£0.60–0.90 per drop × 8+ drops)

### 2.4 Courier Share Mechanics

| Method | Implementation |
|--------|---------------|
| In-app referral card | Shareable graphic showing the courier's earnings: "I've earned £X this week — join me" |
| WhatsApp share | Pre-written message: "I'm earning £12+/hr delivering around Bloomsbury. Use my code [CODE] to sign up and we both get £5 → [link]" |
| Unique QR code | Each courier gets a printable QR code (for sharing IRL, posting on campus boards) |

---

## 3. Merchant Referral Program

### 3.1 Mechanics

```
┌─────────────────────────────────────────────────────────┐
│              MERCHANT REFERS MERCHANT                   │
│                                                         │
│  Referrer (existing merchant)                           │
│    └─→ Introduces another local business                │
│         └─→ Referee merchant signs up + completes       │
│              10 dispatches                              │
│              └─→ Referrer: 1 month free subscription    │
│                   Referee: 1 month free subscription    │
└─────────────────────────────────────────────────────────┘
```

### 3.2 Program Details

| Parameter | Value |
|-----------|-------|
| Referrer reward | 1 month free subscription (£49 value) |
| Referee reward | 1 month free subscription (£49 value) |
| Activation trigger | Referee completes 10 dispatches |
| Max referrals per merchant | 5 per quarter |
| Process | Referrer introduces via email or in-person; founder follows up |

---

## 4. Anti-Fraud Measures

### 4.1 Fraud Vectors & Countermeasures

| Fraud Vector | Countermeasure |
|-------------|---------------|
| Self-referral (multiple accounts) | Unique phone number + unique device fingerprint required per account |
| Collusion (friends creating accounts just for bonus) | Referee must complete genuine drops (GPS verification of distinct pickup/dropoff) |
| Bot signups | CAPTCHA on signup + phone number OTP verification |
| Referral code farming | Monthly cap per referrer (20 senders, 10 couriers) |
| Fake deliveries to trigger referral | All drops validated via TOTP handshake at both ends + GPS + timestamp analysis |
| Account recycling | Deactivated accounts cannot be re-registered with same phone/email for 6 months |

### 4.2 Fraud Detection Signals

| Signal | Action |
|--------|--------|
| > 5 referrals from same IP address | Flag for manual review |
| Referred user completes only 1 drop then goes inactive | No immediate action; pattern tracked |
| > 3 referred users from same Wi-Fi network | Flag; likely same household |
| Referral code shared on cashback/deal sites | Monitor; consider pausing code if abuse detected |
| Referred courier's drops are all < 0.1 mile | Flag as potential fake drops |

---

## 5. Viral Coefficient Analysis

### 5.1 Sender Viral Coefficient

| Variable | Value | Basis |
|----------|-------|-------|
| i = invitations sent per user | 4.5 | Average across referral programs in consumer apps |
| c = conversion rate per invitation | 12% | Industry benchmark for utility apps; adjusted for hyperlocal |
| **K = i × c** | **0.54** | Each sender brings 0.54 new senders |

**Interpretation:** K < 1, so the sender referral alone won't create exponential growth. But it reduces CAC significantly — each paid acquisition generates 0.54 free acquisitions, effectively reducing CAC by 35%.

### 5.2 Courier Viral Coefficient

| Variable | Value | Basis |
|----------|-------|-------|
| i = invitations sent per courier | 3.0 | Couriers share with friends/classmates |
| c = conversion rate per invitation | 18% | Higher than sender — "earn money" is a strong CTA |
| **K = i × c** | **0.54** | Each courier brings 0.54 new couriers |

### 5.3 Cross-Side Viral Effects

The most powerful viral dynamic is **cross-marketplace referral** — where activity on one side drives growth on the other:

| Effect | Mechanism | Coefficient |
|--------|-----------|-------------|
| Recipient → Sender | Package recipient sees LocalLogistics in action; becomes a sender | 0.15 (15% of recipients sign up) |
| Sender → Courier | Sender tells a friend about earnings opportunity | 0.05 |
| Courier → Sender | Courier recommends service to friends/family | 0.08 |
| Merchant → Sender | Merchant's customers discover delivery option | 0.20 per merchant per month |

### 5.4 Aggregate Viral Coefficient

```
Total effective K = Sender K + Cross-side effects
                  = 0.54 + 0.15 + 0.05 + 0.08
                  = 0.82

With merchant amplification (per 15 merchants):
Adjusted K = 0.82 + (15 × 0.20 × conversion adjustment)
           ≈ 0.82 + 0.12
           ≈ 0.94
```

**Target: K ≥ 1.0 by Month 6** — achieved by optimising share mechanics, increasing invitation rate, and growing merchant base.

---

## 6. Referral Program Metrics & Targets

### 6.1 Monthly Targets

| Month | Referral Invites Sent | New Senders via Referral | New Couriers via Referral | Total Referral Cost |
|-------|-----------------------|------------------------|--------------------------|-------------------|
| 1 | 150 | 18 | 8 | £78 + £40 = £118 |
| 2 | 400 | 48 | 20 | £144 + £100 = £244 |
| 3 | 800 | 96 | 35 | £288 + £175 = £463 |
| 4 | 1,200 | 144 | 50 | £432 + £250 = £682 |
| 5 | 1,800 | 216 | 65 | £648 + £325 = £973 |
| 6 | 2,500 | 300 | 80 | £900 + £400 = £1,300 |

### 6.2 Referral Program KPIs

| KPI | Target | Measurement |
|-----|--------|-------------|
| Referral participation rate | ≥ 25% of active senders share their code | Weekly |
| Invitation-to-signup conversion | ≥ 12% | Weekly |
| Signup-to-first-drop conversion (referred users) | ≥ 60% | Weekly |
| Referred user 30-day retention | ≥ 50% (vs 35% for paid-acquired users) | Monthly |
| Cost per referred acquisition (sender) | ≤ £3.00 | Monthly |
| Cost per referred acquisition (courier) | ≤ £5.00 | Monthly |
| Referral as % of total new users | ≥ 30% by Month 3 | Monthly |

### 6.3 Referral Program Budget (6 Months)

| Category | 6-Month Total |
|----------|---------------|
| Sender referral credits (referrer side) | £2,490 |
| Sender referral credits (referee side) | £2,490 |
| Courier referral bonuses (referrer side) | £1,290 |
| Courier referral bonuses (referee side) | £1,290 |
| Merchant referral credits | £490 |
| **Total referral program cost** | **£8,050** |
| **Projected users acquired via referral** | **822 senders + 258 couriers** |
| **Blended referral CAC** | **£7.45** |

---

## 7. Referral Program Optimisation Roadmap

### Phase 1 (Month 1–2): Launch & Learn
- Launch basic referral with fixed £3/£5 incentives
- A/B test share message copy (2 variants)
- Track all funnel metrics
- Identify top referrers — offer them "Ambassador" status

### Phase 2 (Month 3–4): Optimise
- Test variable incentive amounts (£2 vs £3 vs £5 for senders)
- Introduce tiered rewards: 1st referral = £3, 5th = £5, 10th = £10
- Add referral leaderboard with monthly prizes
- Test "Give £5, Get £5" vs "Give £3, Get £3" (higher incentive may increase K)

### Phase 3 (Month 5–6): Scale
- Launch "Referral Week" events — double incentives for 7 days
- Partner with UCL societies: society-wide referral codes with group rewards
- Introduce "Ambassador Program" — top 10 referrers get branded merch + exclusive events
- Test gamified referral: "Unlock Gold status by referring 10 friends"

---

## 8. Referral vs Paid Acquisition — Unit Economics

| Metric | Paid Acquisition (Ads) | Referral Acquisition |
|--------|----------------------|---------------------|
| CAC | £5–8 | £3–5 |
| First-drop conversion | 40% | 60% |
| 30-day retention | 35% | 50% |
| LTV (6-month projected) | £18 | £28 |
| LTV:CAC ratio | 2.6x | 7.0x |
| Time to first drop | 4.2 days | 1.8 days |

**Conclusion:** Referred users are **2.7x more valuable** than paid-acquired users, with lower CAC, faster activation, and higher retention. The referral program should be the primary growth engine by Month 3.
