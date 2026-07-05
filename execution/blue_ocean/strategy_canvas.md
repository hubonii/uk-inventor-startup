# Strategy Canvas: Local-Logistics Protocol

## Competitive Factor Comparison

The Strategy Canvas is the central diagnostic tool of Blue Ocean Strategy. It captures the current state of play in the known market space, showing which factors the industry competes on and what buyers receive.

---

## Players Compared

| Player | Description | Model |
|--------|-------------|-------|
| **Traditional Couriers** | Evri, Royal Mail, DPD, Hermes | Employed/contracted fleet, hub-and-spoke, national coverage |
| **Gig Platforms** | Lalamove, Stuart, Gophr | Gig-worker model, app-dispatched, urban same-day |
| **Local-Logistics Protocol** | Our offering | Permissionless protocol, collateralized staking, hyper-local |

---

## Strategy Canvas Scores (1–5 Scale)

| Competitive Factor | Traditional Couriers | Gig Platforms | Local-Logistics Protocol | Delta vs. Best Incumbent |
|---|:---:|:---:|:---:|:---:|
| Price (Lower = Better for Customer) | 2 | 3 | 5 | **+2** |
| Speed (Same-Day/On-Demand) | 1 | 4 | 4 | 0 |
| Trust / Safety | 4 | 2 | 5 | **+1** |
| Environmental Impact | 2 | 2 | 5 | **+3** |
| Courier Earnings | 2 | 3 | 5 | **+2** |
| Merchant Integration | 3 | 3 | 5 | **+2** |
| Geographic Coverage | 5 | 3 | 1 | -4 |
| Brand Premium | 4 | 2 | 2 | -2 |
| Technology Complexity | 4 | 3 | 2 | **+1** (lower = better) |
| Scalability | 4 | 3 | 5 | **+1** |

---

## Text-Based Strategy Canvas Visualization

```
Score
5 |          ●                    ●    ●    ●              ●         ●
  |                                                   
4 |     ▲         ▲    ■              ■                   ▲    ▲
  |                         ■                    ▲
3 |          ■    ■    ■         ■    ■                         ■    ■
  |                                        ●    ●
2 |     ●    ▲    ●         ▲    ▲              ▲    ●    ●
  |                    ▲    ●                   
1 |               ●                                            ●
  |___________________________________________________________________
       Price Speed Trust  Env  Earn  Merch  Geo  Brand  Tech  Scale

Legend:  ▲ Traditional Couriers   ■ Gig Platforms   ● Local-Logistics Protocol
```

---

## Factor-by-Factor Analysis

### 1. Price — LLP: 5 | Traditional: 2 | Gig: 3

**Our advantage:** Zero fleet costs, zero employee overhead, zero warehousing. Our cost structure is fundamentally lighter than any incumbent. A same-day local delivery costs the merchant £3–5 through our platform versus £6–9 via Stuart/Lalamove and £8–15 via traditional couriers for same-day options. The 15% platform fee on a courier-set rate of ~£3.80 yields merchant costs of ~£4.37 — undercutting gig platforms by 30–50%.

**Why this is sustainable:** We don't subsidize prices. The low cost is structural — we have no fleet depreciation, no driver employment costs, no warehouse rent. Our marginal cost per delivery is near-zero (compute + payment processing).

### 2. Speed — LLP: 4 | Traditional: 1 | Gig: 4

**Parity with gig platforms:** We match Lalamove/Stuart on speed (30–60 min delivery windows) because we use the same fundamental model — nearby couriers accepting jobs. We don't try to compete on 10-minute "dark store" speed; that requires inventory infrastructure we intentionally eliminate.

**Why not a 5:** We don't operate dark stores or pre-position inventory. Our 30-minute target is realistic for a courier who must collect from a merchant, not a warehouse. This is a deliberate strategic choice — we REDUCE speed expectations to ELIMINATE infrastructure costs.

### 3. Trust / Safety — LLP: 5 | Traditional: 4 | Gig: 2

**Our breakthrough:** Traditional couriers achieve trust through background checks, uniforms, and branding — expensive and slow. Gig platforms have a well-documented trust deficit (unvetted drivers, no chain-of-custody). We achieve **superior trust through cryptographic guarantees:**

- **£50 Collateralized Stake:** Courier puts "skin in the game" — economic alignment replaces background checks
- **TOTP QR Handshake:** Cryptographic proof of pickup and delivery — irrefutable chain of custody
- **Automatic Slashing:** Misconduct results in immediate, algorithmic financial penalty — faster than any HR process
- **Progressive Trust:** Couriers earn higher-value job access through successful delivery history

This is our **value innovation core** — we don't just match traditional courier trust, we exceed it through mathematics rather than bureaucracy.

### 4. Environmental Impact — LLP: 5 | Traditional: 2 | Gig: 2

**Structural advantage:** Traditional couriers operate diesel vans on hub-and-spoke routes. Gig platforms use cars for urban deliveries. We incentivize walking, cycling, and public transport couriers through our pricing model — a pedestrian courier keeping 100% of a £3.80 fare earns more per-hour than a driver paying for petrol.

**University Wedge amplifies this:** In the UCL/Bloomsbury zone, most couriers will be students on foot or bike. Average delivery distance is <1.5km. Carbon per delivery approaches zero.

**Visibility:** Every delivery displays estimated carbon saved vs. van delivery — making environmental impact a visible selling point for merchants.

### 5. Courier Earnings — LLP: 5 | Traditional: 2 | Gig: 3

**True Marketplace Pricing:** Couriers set their own rates. No algorithmic wage suppression. No surge pricing captured by the platform. The courier receives 85% of the total delivery fee (we take 15%). Compare:

| Platform | Courier Take Rate | Rate Setting | Transparency |
|----------|-------------------|--------------|--------------|
| Evri | ~£1.00/parcel | Company-set | Opaque |
| Stuart | ~60-65% | Algorithmic | Semi-transparent |
| Deliveroo | ~£3-4/delivery | Algorithmic | Opaque |
| **LLP** | **85%** | **Courier-set** | **Fully transparent** |

**Legal significance:** Courier-set pricing is the single strongest indicator of genuine self-employment under UK law (*Uber v Aslam* [2021] UKSC 5). This isn't just good economics — it's our legal architecture.

### 6. Merchant Integration — LLP: 5 | Traditional: 3 | Gig: 3

**Self-service SaaS model:** Merchants sign up, integrate our API or use our dashboard, and start dispatching within hours. No sales calls, no contracts, no minimum volumes.

- **API-first:** RESTful API with webhook callbacks — integrates into any POS, e-commerce platform, or custom system
- **Shopify/WooCommerce plugins:** One-click installation for the 80% of small merchants on standard platforms
- **Dashboard:** Non-technical merchants can dispatch manually via web dashboard
- **Aggregated billing:** Monthly invoice at £49/mo + per-delivery fees — no per-transaction complexity

Traditional couriers require account setup, credit checks, and minimum volumes. Gig platforms offer APIs but charge enterprise-tier pricing for access.

### 7. Geographic Coverage — LLP: 1 | Traditional: 5 | Gig: 3

**Deliberately low — this is a feature, not a bug.** We are hyper-local by design:

- **Phase 1:** UCL/Bloomsbury wedge (~2.5 km²)
- **Phase 2:** Expand to 3–4 adjacent London university wedges
- **Phase 3:** Top 10 UK university cities
- **Year 2+:** Selective international expansion

We score 1 because we don't pretend to offer national coverage. This is our REDUCE factor — we sacrifice breadth for depth. A merchant in Bloomsbury gets 15-minute courier availability; a merchant in rural Norfolk gets nothing. This is intentional.

### 8. Brand Premium — LLP: 2 | Traditional: 4 | Gig: 2

**Current state:** We have no brand recognition. Royal Mail has 500 years of trust equity. DPD has "best delivery experience" awards. We are a pre-launch startup.

**Future state:** "Delivered by LocalLogistics" becomes a trust mark — the green padlock of physical delivery. But today, we score 2.

**Path to brand premium:** The TOTP verification creates a memorable, distinctive delivery experience. Customers will remember the QR scan ritual. This builds brand through product experience, not advertising spend.

### 9. Technology Complexity (Lower = Better) — LLP: 2 | Traditional: 4 | Gig: 3

**Merchant-facing simplicity:** Our technology is sophisticated underneath but simple on the surface. A merchant needs: (1) a web dashboard or API key, (2) a printer for QR labels. That's it.

Traditional couriers require booking systems, label formats, pickup scheduling, tracking integration — significant complexity. Gig platforms are simpler but still require app installation and account verification.

**Our protocol is invisible:** The TOTP cryptography, staking mechanics, and reputation algorithms run silently. The merchant sees: "Dispatch" → "Courier Assigned" → "Picked Up" → "Delivered." Four states. Maximum simplicity.

### 10. Scalability — LLP: 5 | Traditional: 4 | Gig: 3

**Zero marginal infrastructure:** Adding a new merchant costs us nothing. Adding a new courier costs us nothing. We don't need to buy vans, lease warehouses, or hire managers.

**Network effects accelerate scale:** Each new merchant creates demand; each new courier creates supply. The platform becomes more valuable to both sides with each addition. Traditional couriers scale linearly (more packages = more vans). We scale exponentially (more participants = more network value).

**Protocol scalability:** The TOTP system is stateless — it scales horizontally with zero architectural changes. Our bottleneck is market density, not technology.

---

## Strategic Interpretation

### Where We Win (Scores ≥ 4, beating incumbents)
- **Price:** Structural cost advantage from zero-fleet model
- **Trust:** Cryptographic guarantees exceed bureaucratic checks
- **Environment:** Pedestrian/cycling couriers in dense urban zones
- **Courier Earnings:** True Marketplace pricing with 85% take rate
- **Merchant Integration:** Self-service SaaS with API-first design
- **Scalability:** Zero marginal cost per additional participant

### Where We Deliberately Sacrifice (Scores ≤ 2)
- **Geographic Coverage:** Hyper-local focus is intentional
- **Brand Premium:** Pre-launch startup reality

### Blue Ocean Insight

The traditional industry competes on geographic coverage and brand premium — factors that require massive capital. We compete on factors that require zero capital: trust (via cryptography), price (via zero-fleet), and earnings transparency (via protocol design). This is classic Blue Ocean positioning — we don't fight incumbents on their strengths; we make their strengths irrelevant.

---

*Strategy Canvas methodology: W. Chan Kim & Renée Mauborgne, Blue Ocean Strategy (2005)*
*Last updated: July 2026*
