# Retention Strategy — Local-Logistics Protocol

## Overview

Retention is the silent killer of marketplaces. A 5% improvement in retention can increase lifetime value by 25–95%. This playbook defines retention mechanics for all three sides of the marketplace: senders, couriers, and merchants.

**Retention Targets:**

| User Type | Day 7 | Day 30 | Day 90 | Day 180 |
|-----------|-------|--------|--------|---------|
| Senders | 65% | 40% | 28% | 20% |
| Couriers | 75% | 55% | 40% | 30% |
| Merchants | 95% | 90% | 85% | 80% |

---

## 1. Sender Retention

### 1.1 Retention Thesis

Senders retain when: **(a)** delivery is fast and reliable, **(b)** they develop a habit, and **(c)** switching to an alternative is harder than staying.

### 1.2 Streak Rewards

**Mechanic:** Senders earn cumulative rewards for consecutive weeks of sending at least 1 package.

| Streak | Reward | Psychological Hook |
|--------|--------|--------------------|
| Week 1 | "Welcome" badge + £0 | Onboarding — establish baseline |
| 2-week streak | £1 credit | First reward — "I'll keep going to not lose it" |
| 4-week streak | £3 credit | Sunk cost — "I've built a streak, can't stop now" |
| 8-week streak | £5 credit + "Super Sender" badge | Status — visible badge on profile |
| 12-week streak | £10 credit + priority matching | Tangible benefit — faster service |
| 26-week streak | Free delivery + "Founding Sender" badge | Loyalty — publicly recognised |
| 52-week streak | 1 month free subscription (if applicable) + personalised thank-you from founder | Emotional — "this platform knows me" |

**Streak Break Recovery:**
- If a sender misses 1 week: "Your streak is about to reset! Send something this week to keep it alive → [Send Now]"
- If streak breaks: "Your 6-week streak ended 😢 Start a new one today — send something and get £1 credit"
- Grace period: 1 "streak freeze" per quarter (paid: £1.50)

### 1.3 Subscription Discounts

**"Sender Pass" — Monthly Subscription:**

| Tier | Monthly Fee | Included Drops | Discount vs Pay-As-You-Go | Target Segment |
|------|-----------|---------------|--------------------------|----------------|
| Lite | £4.99/mo | 3 drops | 15% off each | Occasional senders |
| Regular | £9.99/mo | 8 drops | 22% off each | Weekly senders |
| Unlimited | £19.99/mo | Unlimited | ~35% off (at 15+ drops) | Power senders / small businesses |

**Subscription retention advantage:**
- Subscribers have 3.5x higher 90-day retention than pay-as-you-go users (industry benchmark)
- Subscription creates "use it or lose it" psychology — drives habitual behaviour
- Monthly billing creates predictable revenue + billing relationship

### 1.4 Re-Engagement Sequences

| Trigger | Timing | Channel | Message |
|---------|--------|---------|---------|
| No drop in 7 days | Day 7 | Push + Email | "Miss us? Your favourite courier [name] is nearby — send something 📦" |
| No drop in 14 days | Day 14 | SMS | "It's been 2 weeks! Here's £2 off your next delivery → [code]" |
| No drop in 30 days | Day 30 | Email + Push | "We've missed you, [Name]. 50% off your next drop this week only" |
| No drop in 60 days | Day 60 | Email | "Things have changed since you left → [new features list]. Come back with a free delivery" |
| No drop in 90 days | Day 90 | Personal email from founder | "Hi [Name], I noticed you haven't used LocalLogistics in a while. I'd love to know why — can I buy you a coffee?" |

### 1.5 Sender Gamification

| Feature | Description | Retention Lever |
|---------|-------------|----------------|
| Drop counter | Lifetime drops displayed prominently in profile | Progress + investment |
| Sender leaderboard | "Top Senders in Bloomsbury this month" | Competition + social proof |
| Achievement badges | "Night Owl" (sent after 8 PM), "Early Bird" (before 9 AM), "Multi-Sender" (3 drops in 1 day) | Collection psychology |
| Favourite courier | Mark a courier as "favourite" — they get priority for your drops | Personal connection |
| Delivery timeline | Visual history of all past deliveries with photos and routes | Nostalgia + investment |

---

## 2. Courier Retention

### 2.1 Retention Thesis

Couriers retain when: **(a)** earnings are competitive and predictable, **(b)** they feel valued and part of a community, and **(c)** the tier system creates aspirational progression.

### 2.2 Earnings Guarantees (First 30 Days)

| Week | Guarantee | Condition |
|------|-----------|-----------|
| Week 1 | £12/hr for first 10 hours | Must accept ≥ 80% of offered drops |
| Week 2 | £11/hr for first 10 hours | Must accept ≥ 75% of offered drops |
| Week 3 | £10/hr for first 8 hours | Must accept ≥ 70% of offered drops |
| Week 4 | No guarantee (organic earnings expected to exceed £12/hr) | — |

**Guarantee cost model:**
- Expected average shortfall: £3/hr per courier in Week 1, declining to £0 by Week 4
- Total cost per courier onboarded: ~£80
- ROI: A retained courier generates £0.60–0.90/drop in platform fees; at 15 drops/week, breaks even in 2 weeks

### 2.3 Tier System

```
┌─────────────────────────────────────────────────────────┐
│                   COURIER TIER SYSTEM                   │
│                                                         │
│  🥉 BRONZE (0–49 drops)                                │
│  ├── Standard matching priority                         │
│  ├── Basic earnings dashboard                           │
│  └── Community WhatsApp access                          │
│                                                         │
│  🥈 SILVER (50–199 drops)                               │
│  ├── Priority matching (see drops 15 sec early)         │
│  ├── Access to merchant premium drops                   │
│  ├── Weekly earnings summary email                      │
│  ├── Silver badge visible to senders                    │
│  └── Monthly courier meetup invitation                  │
│                                                         │
│  🥇 GOLD (200+ drops)                                   │
│  ├── Top-priority matching (see drops 30 sec early)     │
│  ├── Access to all premium/scheduled drops              │
│  ├── Dedicated ops support line                         │
│  ├── Gold badge visible to senders + merchants          │
│  ├── Quarterly earnings bonus (5% of quarter's total)   │
│  ├── Referral bonus doubled (£10 instead of £5)         │
│  ├── Invited to product feedback sessions               │
│  └── "Gold Courier" featured on LocalLogistics social   │
│                                                         │
│  💎 PLATINUM (500+ drops, by invitation)                │
│  ├── All Gold benefits                                  │
│  ├── Beta access to new features                        │
│  ├── Mentorship role (train new couriers)               │
│  ├── Revenue share on mentees' drops (2%)               │
│  ├── Annual courier appreciation event                  │
│  └── Consideration for ops team hire                    │
└─────────────────────────────────────────────────────────┘
```

**Tier progression timeline:**

| Tier | Drops Required | At 3 drops/day | At 5 drops/day |
|------|---------------|---------------|---------------|
| Bronze | 0 | Day 1 | Day 1 |
| Silver | 50 | Week 3 | Week 2 |
| Gold | 200 | Week 10 | Week 6 |
| Platinum | 500 | Week 24 | Week 15 |

### 2.4 Courier Community Building

| Activity | Frequency | Description | Budget |
|----------|-----------|-------------|--------|
| WhatsApp community group | Daily | Tips sharing, route advice, memes, banter | £0 |
| Monthly courier meetup | Monthly | Pizza + beer, feedback session, founder Q&A, leaderboard awards | £100/event |
| "Courier of the Month" spotlight | Monthly | Featured on social media + £25 bonus | £25/mo |
| Quarterly earnings celebration | Quarterly | Top 10% of earners get dinner + thank-you gift | £200/event |
| Courier feedback panel | Monthly | 5 couriers advise on product decisions, paid £20/session | £100/mo |

### 2.5 Courier Earnings Optimisation Tools

| Tool | Description | Retention Lever |
|------|-------------|----------------|
| Demand heatmap | Real-time map showing where drops are most likely | Helps couriers earn more → happier |
| Earnings forecast | "If you work 2 more hours today, you'll earn ~£24" | Motivational; helps planning |
| Peak hour alerts | "Lunch rush starting in 30 min — high demand expected" | Drives availability during high-value periods |
| Weekly earnings report | Breakdown by day, hour, and route with tips for optimisation | Financial clarity → trust |
| Tax estimation tool | "Your estimated quarterly tax: £X. Set aside £Y per week" | Practical value; reduces stress |

### 2.6 Courier Churn Prevention

| Signal | Intervention | Owner | SLA |
|--------|-------------|-------|-----|
| No drops in 5 days | Push notification: "Drops available near you — earn £X today" | Automated | Immediate |
| No drops in 10 days | Personal WhatsApp from ops: "Everything OK? How can we help?" | Ops | 24 hrs |
| Earnings dropped > 30% week-over-week | SMS: "We noticed your earnings dipped. Here are 3 tips to earn more this week" | Automated | Immediate |
| Negative rating trend | 1:1 call: constructive feedback + re-training offer | Ops | 48 hrs |
| Courier deactivates account | Exit survey (2 min) + founder follow-up call | Founder | 24 hrs |
| Competitor poaching (courier mentions competitor) | Match offer + highlight tier benefits + "loyalty bonus" | Founder | Same day |

---

## 3. Merchant Retention

### 3.1 Retention Thesis

Merchants retain when: **(a)** delivery demonstrably increases their revenue, **(b)** the service is operationally zero-friction, and **(c)** switching costs are high (data, relationships, integration).

### 3.2 Volume Discounts

| Monthly Drop Volume | Platform Fee (Standard: 15%) | Effective Saving |
|---------------------|-------------------------------|-----------------|
| 1–30 drops | 15% | — |
| 31–75 drops | 13% | £2–6/mo |
| 76–150 drops | 11% | £8–18/mo |
| 151–300 drops | 9% | £20–40/mo |
| 300+ drops | 7% (negotiated) | £40+/mo |

**Psychology:** Volume discounts reward merchants for growth and create a "ratchet effect" — once a merchant hits a tier, they're incentivised to stay above the threshold.

### 3.3 Analytics Dashboard

| Feature | Description | Value to Merchant | Retention Lock-In |
|---------|-------------|-------------------|-------------------|
| Delivery volume trends | Weekly/monthly graph of dispatches | Business intelligence | Data loss on switching |
| Customer heatmap | Where deliveries go most frequently | Target marketing | Unique insight |
| Peak time analysis | When dispatch volume is highest | Staffing optimisation | Operational dependency |
| Average delivery time | Track service quality over time | Customer service data | SLA monitoring |
| Customer satisfaction scores | NPS and ratings from delivery recipients | Reputation management | Customer voice |
| Revenue attribution | "Estimated revenue from delivery customers: £X" | ROI proof | Justifies subscription |
| Comparative benchmarks | "You dispatch 40% more than similar pharmacies" | Competitive intelligence | Ego + motivation |

### 3.4 Merchant Success Programme

| Milestone | Action | Owner |
|-----------|--------|-------|
| First dispatch | Congratulations email + quick-start guide | Automated |
| 10th dispatch | Personal call: "How's it going? Any issues?" | Founder |
| 50th dispatch | Case study request: "Can we feature your success?" | Growth |
| 100th dispatch | Gift: branded mug + handwritten thank-you | Founder |
| 6-month anniversary | In-person review: ROI analysis, feature roadmap preview | Founder |
| 1-year anniversary | Public recognition: "Founding Merchant" badge + press feature | Growth |

### 3.5 Merchant Integration & Lock-In

| Integration | When | Description | Switching Cost Created |
|-------------|------|-------------|----------------------|
| POS system integration | Month 3 | Auto-trigger delivery when order is placed in POS | Technical switching cost |
| Inventory sync | Month 4 | Real-time stock visibility for delivery-eligible items | Operational dependency |
| Customer database | Month 5 | Merchant sees delivery customer profiles and preferences | Data loss on switching |
| Automated dispatch rules | Month 6 | "If order > £10, auto-offer delivery" | Process dependency |
| API access | Month 6 | Custom integrations with merchant's website/app | Deep technical lock-in |

### 3.6 Merchant Churn Prevention

| Signal | Intervention | Owner | SLA |
|--------|-------------|-------|-----|
| < 3 dispatches in 2 weeks | In-person visit: "What's blocking dispatches?" | Founder | 48 hrs |
| Staff turnover (new face at merchant) | Free re-training for new staff | Ops | Same week |
| Complaint about courier quality | Immediate courier feedback + reassignment + follow-up | Ops | 4 hrs |
| Subscription payment fails | Personal call (not automated email): "Hey, your payment bounced — let me help" | Finance | 24 hrs |
| Merchant mentions considering cancellation | Emergency meeting: root cause analysis + retention offer | Founder | Same day |
| Negative Google review mentioning LocalLogistics | Alert → investigate → respond → remediate | Growth | 2 hrs |

### 3.7 Merchant Retention Offers (Last Resort)

| Situation | Offer | Cost | ROI Threshold |
|-----------|-------|------|--------------|
| Merchant at risk (low usage) | 1 month free subscription | £49 | Retain if merchant dispatches ≥ 5/month |
| Merchant considering competitor | 3 months at 50% off + dedicated support | £73.50 | Retain if merchant dispatches ≥ 10/month |
| Merchant churned (win-back) | 2 months free + feature walkthrough + new staff training | £98 | Only if merchant had > 10 dispatches/month historically |

---

## 4. Cross-Marketplace Retention Mechanics

### 4.1 Interconnected Retention

The strongest retention comes from **cross-side dependencies:**

| Mechanic | How It Works | Retention Impact |
|----------|-------------|-----------------|
| **Favourite courier** | Senders mark preferred couriers; those couriers get priority for their drops | Sender + Courier retention (personal bond) |
| **Merchant loyalty** | Senders earn points for ordering from the same merchant | Sender + Merchant retention |
| **Courier streaks** | Couriers earn bonuses for consecutive days active; shown to senders as "reliability badge" | Courier retention → improves sender experience |
| **Community stories** | Weekly email featuring a sender story, courier story, and merchant story | All sides feel part of something |
| **Platform milestones** | "LocalLogistics just completed its 10,000th delivery! 🎉" shared with all users | Collective pride; shared identity |

### 4.2 Seasonal Retention Strategies

| Period | Risk | Strategy |
|--------|------|----------|
| **University term start (Sept/Jan)** | New students = acquisition opportunity, but also churn of graduates | "Freshers' Welcome" campaign; handoff from graduating to incoming students |
| **Exam season (Dec/May)** | Senders increase (need to send documents); Couriers decrease (studying) | Courier surge bonuses; "Study break and earn" messaging |
| **Summer (June–Aug)** | University population drops 60%; risk of liquidity collapse | Pivot messaging to local residents; maintain merchant relationships; reduced ops hours |
| **Christmas (Dec)** | Gift sending spike; courier availability drops | Gift-specific features; "Send a gift in 20 minutes"; holiday bonuses for couriers |
| **Bank holidays** | Reduced activity | Reduced courier requirements; special promotions |

---

## 5. Retention Metrics Dashboard

### 5.1 Weekly Retention Review

| Metric | Sender | Courier | Merchant |
|--------|--------|---------|----------|
| WAU / MAU ratio | ≥ 0.35 | ≥ 0.50 | ≥ 0.70 |
| Churn rate (monthly) | < 15% | < 12% | < 5% |
| Reactivation rate (churned users returning) | ≥ 10% | ≥ 8% | ≥ 20% |
| NPS (rolling 30-day) | ≥ 45 | ≥ 35 | ≥ 55 |
| Support ticket volume (per 100 users) | < 5 | < 8 | < 3 |
| Feature adoption rate (new features) | ≥ 20% in first week | ≥ 30% in first week | ≥ 40% in first week |

### 5.2 Cohort Analysis Framework

Track each monthly cohort separately:

| Cohort | Month 0 | Month 1 | Month 2 | Month 3 | Month 6 |
|--------|---------|---------|---------|---------|---------|
| January Senders | 100% | 42% | 30% | 25% | 18% |
| February Senders | 100% | 45% | 33% | 28% | 21% |
| March Senders | 100% | 48% | 36% | 30% | — |

**Healthy signal:** Each successive cohort retains better than the previous one (improving product + retention tactics working).

---

## 6. Retention Investment Budget

### 6.1 Monthly Retention Spend

| Category | Monthly Budget | % of Revenue (at scale) |
|----------|---------------|------------------------|
| Streak rewards / credits (senders) | £400 | 4% |
| Courier guaranteed earnings (Month 1 only) | £2,400 → £0 | 8% → 0% |
| Courier tier bonuses | £200 | 2% |
| Courier community events | £150 | 1.5% |
| Merchant analytics dashboard (engineering) | £0 (built into product) | 0% |
| Merchant success programme (gifts, visits) | £100 | 1% |
| Re-engagement campaigns (SMS, email) | £75 | 0.8% |
| **Total (at steady state, Month 4+)** | **£925/mo** | **~9%** |

### 6.2 ROI of Retention

| Scenario | Without Retention Investment | With Retention Investment |
|----------|----------------------------|--------------------------|
| Monthly sender churn | 22% | 13% |
| 6-month sender LTV | £14 | £28 |
| Monthly courier churn | 18% | 10% |
| 6-month courier LTV (platform fees generated) | £180 | £350 |
| Revenue at Month 6 (projected) | £3,200/mo | £6,800/mo |

**£925/mo retention spend generates an estimated £3,600/mo in additional revenue — 3.9x ROI.**
