# Viral Loops — Local-Logistics Protocol

## Overview

This document identifies, designs, and quantifies **three core viral loops** embedded into the Local-Logistics Protocol. Each loop is a self-reinforcing growth mechanism where usage of the product by one user creates exposure that drives acquisition of new users — without paid marketing.

---

## Viral Loop 1: Package Receipt Sharing (Recipient → Sender)

### 1.1 The Insight

Every delivery has **two parties**: the sender and the recipient. The recipient experiences the product without ever downloading the app. This is the single most powerful viral surface — every drop creates a potential new user.

### 1.2 Loop Mechanics

```
Sender sends package via LocalLogistics
    │
    ▼
Recipient gets SMS: "A package is on its way from [Sender] via LocalLogistics"
    │
    ▼
Recipient tracks delivery in real-time (mobile web — no app needed)
    │
    ▼
Courier arrives → Recipient scans QR code on phone (first touch!)
    │
    ▼
Delivery confirmed → Recipient sees:
    │
    ├─→ "Want to send something back? Get £3 off your first delivery"
    │
    └─→ [Download App] button with pre-filled referral from sender
         │
         ▼
    Recipient becomes a Sender → Loop repeats
```

### 1.3 Touchpoints & Design

| Touchpoint | Channel | Content | Conversion Lever |
|------------|---------|---------|-----------------|
| T1: "Package incoming" notification | SMS + email | "📦 [Sender Name] is sending you something via LocalLogistics. Track it live → [link]" | Curiosity; real-time tracking |
| T2: Tracking page | Mobile web | Live courier location on map, ETA countdown, courier profile photo | Product demonstration |
| T3: QR handoff moment | In-person | Recipient scans QR code on their phone — first interaction with protocol | Wow moment; "that was easy" |
| T4: Post-delivery screen | Mobile web | "Delivered ✓ — Want to send something? Get £3 off → [Download]" | Immediate CTA while experience is fresh |
| T5: Follow-up SMS (24 hrs later) | SMS | "Did your package arrive OK? Send something yourself → £3 off first delivery [link]" | Reminder for non-converters |

### 1.4 Viral Coefficient Calculation

| Variable | Value | Basis |
|----------|-------|-------|
| Drops per sender per month | 3.5 | Projected average |
| Unique recipients per drop | 0.85 | Some recipients are repeat (e.g., same flatmate) |
| Recipients who view tracking page | 80% | SMS open rate × click rate |
| Tracking viewers who see CTA | 95% | CTA is embedded in tracking flow |
| CTA viewers who download app | 8% | Conservative; product demo increases intent |
| Downloaders who complete first drop | 55% | Higher than cold acquisition (already experienced product) |
| **Effective K₁** | **0.127** | 3.5 × 0.85 × 0.80 × 0.95 × 0.08 × 0.55 |

**Per 1,000 senders per month: 127 new senders acquired organically via receipt sharing**

### 1.5 Optimisation Levers

| Lever | Current | Optimised | Impact on K₁ |
|-------|---------|-----------|-------------|
| Add "Share with recipient" prompt to sender | 80% see tracking | 90% see tracking | K₁ → 0.143 |
| Improve CTA design (larger button, social proof) | 8% download | 12% download | K₁ → 0.190 |
| Add "Send something back" feature (reverse delivery) | N/A | 5% of recipients do reverse drop | K₁ → 0.190 + 0.05 bonus |
| Make QR handoff moment more memorable (sound, animation) | Functional | Delightful | Indirect; increases sharing |

---

## Viral Loop 2: Courier Earnings Social Proof

### 2.1 The Insight

Gig workers love sharing earnings. Every Uber driver who tells a friend "I made £150 yesterday" is doing free marketing. LocalLogistics couriers — especially students — will share earnings on social media and in WhatsApp groups, creating organic supply-side growth.

### 2.2 Loop Mechanics

```
Courier completes drops and earns money
    │
    ▼
App generates shareable "Earnings Card":
  ┌─────────────────────────────┐
  │  🏃 Today's Earnings         │
  │                             │
  │  £47.20 earned              │
  │  8 drops completed          │
  │  3 hrs 15 min active        │
  │  = £14.52/hr               │
  │                             │
  │  ─────────────────────────  │
  │  Top delivery: 0.3 mi      │
  │  in 11 minutes ⚡           │
  │                             │
  │  locallogistics.co/courier  │
  │  Earn while you walk 🚶     │
  └─────────────────────────────┘
    │
    ▼
Courier shares on Instagram Story / WhatsApp / TikTok
    │
    ▼
Friends see earnings → "How do I sign up?"
    │
    ▼
Click link → Download app → KYC → First drop
    │
    ▼
New courier earns money → shares THEIR earnings card → Loop repeats
```

### 2.3 Earnings Card Design Principles

1. **Aspirational but believable:** Show hourly rate prominently (£14.52/hr makes people think "I could do that")
2. **Branded but subtle:** LocalLogistics logo small; focus on the earnings number
3. **Instagram-native:** Designed for Stories (9:16 ratio, bold typography, dark mode compatible)
4. **One-tap sharing:** Generate card + open share sheet in 1 tap from earnings screen
5. **Customisable:** Courier can choose to show/hide specific metrics
6. **Milestone cards:** Special designs for "First £100," "50th Drop," "Gold Tier Unlocked"

### 2.4 Sharing Triggers

| Trigger | When | Push Notification | Earnings Card Variant |
|---------|------|-------------------|--------------------|
| Daily earnings summary | End of active day | "Nice work! You earned £X today → Share your win" | Daily recap card |
| Weekly earnings summary | Sunday evening | "This week: £X earned, Y drops. Your best week yet!" | Weekly recap card |
| Hourly rate milestone | £15+/hr day | "You earned over £15/hr today — that beats most gig apps!" | Hourly rate card |
| Drop milestone | 10th, 25th, 50th, 100th drop | "🎉 50 drops completed! Share your journey" | Milestone card |
| Tier promotion | Bronze → Silver → Gold | "You've been promoted to Silver! Share the news" | Tier card |
| Earnings milestone | First £100, £500, £1,000 | "You just passed £1,000 lifetime earnings!" | Lifetime card |

### 2.5 Viral Coefficient Calculation

| Variable | Value | Basis |
|----------|-------|-------|
| Active couriers per month | 200 | 90-day target |
| Couriers who share earnings card | 35% | Student demographic is share-heavy |
| Shares per sharing courier per month | 2.5 | Weekly habit for active couriers |
| Average reach per share (unique viewers) | 80 | Instagram Story / WhatsApp group reach |
| Viewers who are in target demo (student, local) | 40% | Geographic + demo filter |
| Relevant viewers who click signup link | 3% | Lower than direct referral — passive exposure |
| Clickers who complete signup + KYC | 25% | Self-selected, earnings-motivated |
| KYC'd who complete first drop | 70% | Strong intent from social proof |
| **New couriers per month via earnings sharing** | **29** | 200 × 0.35 × 2.5 × 80 × 0.40 × 0.03 × 0.25 × 0.70 |
| **Effective K₂ (courier-side)** | **0.147** | 29 / 200 |

**Per 200 active couriers per month: 29 new couriers acquired organically via earnings social proof**

### 2.6 Amplification Tactics

| Tactic | Description | Expected Impact |
|--------|-------------|----------------|
| "Share to Earn" bonus | Courier gets £0.50 credit when they share an earnings card (capped at 4/month) | +30% sharing rate |
| Courier spotlight | Feature top earner of the week on LocalLogistics Instagram (with consent) | +20% shares (aspiration effect) |
| TikTok content kit | Provide couriers with branded video templates: "POV: I just earned £X delivering" | New channel; 5–10 new couriers/mo |
| Earnings leaderboard | Public (opt-in) weekly leaderboard in-app; shareable link | +15% sharing rate |

---

## Viral Loop 3: Merchant "Delivered by LocalLogistics" Branding

### 3.1 The Insight

Every merchant delivery carries the LocalLogistics brand to a customer's door. The courier wears/carries branded materials, the tracking SMS mentions LocalLogistics, and the merchant displays signage. This creates **ambient brand awareness** that converts over time — similar to how "Powered by Shopify" drives B2B growth.

### 3.2 Loop Mechanics

```
Merchant signs up for LocalLogistics
    │
    ▼
Merchant displays branding:
  • Window sticker: "We deliver via LocalLogistics"
  • Counter card: "Get it delivered in 20 minutes"
  • Receipt/bag sticker: "Delivered by LocalLogistics"
    │
    ▼
Customer in shop sees branding → "What's LocalLogistics?"
    │
    ├─→ Customer scans QR on counter card → becomes a SENDER
    │
    └─→ Customer tells another MERCHANT about the service
         │
         ▼
    Merchant contacts LocalLogistics → becomes a new MERCHANT
         │
         ▼
    New merchant displays branding → Loop repeats
```

### 3.3 Brand Touchpoints

| Touchpoint | Location | Design | Conversion Mechanism |
|------------|----------|--------|---------------------|
| Window sticker | Shop front | "We deliver in 20 min ⚡ Powered by LocalLogistics" + QR | Foot traffic → scan → download |
| Counter tent card | Point of sale | "Need this delivered? Scan here → 20-min delivery" + QR | Purchase moment → "add delivery" |
| Receipt sticker | On bag/receipt | "Delivered by LocalLogistics 📦" + URL | Passive brand exposure |
| Merchant website badge | Merchant's website/Google listing | "LocalLogistics Verified Merchant" badge | Online discovery → click-through |
| Courier bag/lanyard | Carried by courier | Small "LocalLogistics" logo on courier bag | Street-level brand awareness |
| Tracking SMS | Sent to delivery recipient | "Your order from [Merchant] is being delivered by LocalLogistics" | Digital brand exposure |

### 3.4 Viral Coefficient Calculation

#### Path A: Merchant Branding → New Senders

| Variable | Value | Basis |
|----------|-------|-------|
| Active merchants | 15 | 90-day target |
| Avg daily foot traffic per merchant | 60 | Small local shop average |
| Customers who notice branding | 30% | Eye-tracking studies for POS displays |
| Noticers who scan QR or visit URL | 2% | Low-intent; ambient exposure |
| Scanners who download app | 40% | High intent — actively curious |
| Downloaders who complete first drop | 45% | Moderate — may explore first |
| **New senders per month via merchant branding** | **15** | 15 × 60 × 30 × 0.30 × 0.02 × 0.40 × 0.45 |

#### Path B: Merchant Branding → New Merchants

| Variable | Value | Basis |
|----------|-------|-------|
| Active merchants | 15 | 90-day target |
| Other merchants who notice (neighbours, suppliers) | 3 per merchant per month | Word of mouth in local business community |
| Noticing merchants who enquire | 20% | Strong intent — business value prop |
| Enquirers who sign up | 50% | High conversion — peer social proof |
| **New merchants per month via merchant branding** | **4.5** | 15 × 3 × 0.20 × 0.50 |

#### Combined K₃

| Path | New Users/Month | K₃ |
|------|----------------|-----|
| Path A (new senders) | 15 | 0.030 (per sender base; more meaningful as absolute) |
| Path B (new merchants) | 4.5 | 0.300 (per merchant base) |

### 3.5 Merchant Branding Kit

| Item | Specs | Cost per Merchant |
|------|-------|-------------------|
| Window sticker (exterior) | A4, vinyl, weatherproof, QR code | £3.50 |
| Counter tent card | A5, card stock, double-sided, QR code | £1.50 |
| Receipt stickers (roll of 500) | 50mm circle, "Delivered by LocalLogistics" | £8.00 |
| Website badge (digital) | SVG/PNG, "LocalLogistics Verified Merchant" | £0 |
| Courier bag insert cards (50) | Business card size, QR to sender signup | £2.50 |
| **Total per merchant** | | **£15.50** |

---

## 4. Combined Viral Model

### 4.1 All Loops Combined

```
                    ┌─────────────────────┐
                    │   SENDER BASE       │
                    │   (grows over time)  │
                    └────┬───────────┬─────┘
                         │           │
           ┌─────────────▼─┐   ┌────▼──────────────┐
           │ Loop 1:       │   │ Loop 3 (Path A):   │
           │ Receipt       │   │ Merchant branding  │
           │ Sharing       │   │ → new senders      │
           │ K₁ = 0.127    │   │ K₃a = ~15/mo      │
           └───────────────┘   └────────────────────┘
                         │
           ┌─────────────▼──┐
           │ COURIER BASE   │
           │ (grows)        │
           └────┬───────────┘
                │
           ┌────▼──────────────┐
           │ Loop 2:           │
           │ Earnings Social   │
           │ Proof             │
           │ K₂ = 0.147        │
           └───────────────────┘
                         │
           ┌─────────────▼──┐
           │ MERCHANT BASE  │
           │ (grows)        │
           └────┬───────────┘
                │
           ┌────▼──────────────┐
           │ Loop 3 (Path B):  │
           │ Merchant → Merchant│
           │ K₃b = 0.300       │
           └───────────────────┘
```

### 4.2 Monthly Organic Growth Contribution (At 200 Couriers, 500 Senders, 15 Merchants)

| Loop | New Users/Month | User Type | CAC |
|------|----------------|-----------|-----|
| Loop 1: Receipt Sharing | 63 | Senders | £0 |
| Loop 2: Earnings Social Proof | 29 | Couriers | £0 |
| Loop 3a: Merchant → Sender | 15 | Senders | £0 |
| Loop 3b: Merchant → Merchant | 4–5 | Merchants | £0 |
| **Total organic acquisition** | **~112** | **Mixed** | **£0** |

### 4.3 Viral Growth Projections

| Month | Total Users | Paid Acquired | Virally Acquired | Viral % of Growth |
|-------|-------------|--------------|------------------|------------------|
| 1 | 70 | 60 | 10 | 14% |
| 2 | 180 | 130 | 50 | 28% |
| 3 | 350 | 220 | 130 | 37% |
| 4 | 550 | 290 | 260 | 47% |
| 5 | 800 | 340 | 460 | 58% |
| 6 | 1,100 | 370 | 730 | 66% |

**By Month 6, viral loops should drive 2/3 of all new user acquisition.**

---

## 5. Viral Loop Optimisation Framework

### 5.1 Measurement Dashboard

| Metric | Loop 1 | Loop 2 | Loop 3 |
|--------|--------|--------|--------|
| Impressions | Tracking page views | Earnings card views (social) | Branding exposure (foot traffic × noticers) |
| Clicks | CTA taps on tracking page | Signup link clicks from shares | QR scans from merchant materials |
| Signups | New accounts with recipient source | New courier accounts with social source | New accounts with merchant QR source |
| Activation | First drop completed | First drop completed | First drop completed / merchant onboarded |
| Viral coefficient | K₁ | K₂ | K₃ |

### 5.2 A/B Test Roadmap

| Test | Hypothesis | Loop | Priority |
|------|-----------|------|----------|
| Tracking page CTA: "Send something back" vs "Download app" | Reverse-delivery CTA increases conversion | 1 | High |
| Earnings card: Show hourly rate vs total earned | Hourly rate is more shareable (relatable) | 2 | High |
| Counter card: "20-minute delivery" vs "Cheaper than Deliveroo" | Speed messaging outperforms price | 3 | Medium |
| Share timing: Immediate vs 1-hour delay after drop | Immediate sharing captures emotional peak | 2 | Medium |
| Recipient SMS: Include sender's name vs anonymous | Personal name increases open rate | 1 | High |
| Earnings card format: Static image vs animated | Animated gets more engagement on Stories | 2 | Low |

### 5.3 Viral Loop Health Indicators

| Indicator | Healthy | Warning | Action |
|-----------|---------|---------|--------|
| K₁ (Receipt Sharing) | ≥ 0.10 | < 0.05 | Redesign tracking page CTA; test SMS copy |
| K₂ (Earnings Social Proof) | ≥ 0.10 | < 0.05 | Increase sharing incentives; improve card design |
| K₃ (Merchant Branding) | ≥ 0.20 (merchant K) | < 0.10 | Upgrade branding materials; increase counter card visibility |
| Overall viral % of growth | ≥ 30% by Month 3 | < 15% by Month 3 | Fundamental reassessment of viral strategy |
| Sharing rate (couriers) | ≥ 30% | < 15% | Add "share to earn" incentive |
| QR scan rate (merchant materials) | ≥ 1.5% of foot traffic | < 0.5% | Redesign materials; test placement |

---

## 6. Long-Term Viral Vision

### 6.1 Network Viral Effects (Month 12+)

As the platform scales, new viral loops emerge:

| Loop | Mechanism | Expected K |
|------|-----------|-----------|
| **Courier fleet visibility** | Couriers walking with branded bags become walking billboards | 0.02 per active courier |
| **Merchant cluster effect** | When 3+ merchants on same street use LocalLogistics, foot traffic amplifies | 1.5x K₃ amplifier |
| **Student word-of-mouth** | Campus culture makes LocalLogistics "what everyone uses" | Unmeasurable; tipping point effect |
| **PR / earned media** | Viral stories ("student makes £500/week walking") generate press | Spike-based; 100–500 signups per article |
| **API partnerships** | Other apps integrate LocalLogistics → exposure to their user base | Variable; partnership-dependent |

### 6.2 Path to K ≥ 1.0

```
Month 1–3:  K ≈ 0.35  │  Viral loops contributing, but paid dominates
Month 4–6:  K ≈ 0.65  │  Viral growing; paid CAC declining as % of total
Month 7–9:  K ≈ 0.85  │  Approaching viral breakeven
Month 10–12: K ≈ 1.05  │  Self-sustaining growth — viral exceeds churn
Month 13+:  K ≈ 1.15  │  Network effects compound; expansion drives new loops
```

**When K > 1.0, every user we lose to churn is replaced (and exceeded) by viral acquisition — the growth engine becomes self-sustaining.**
