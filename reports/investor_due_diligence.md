# Investor-Grade Due Diligence Package

**Company:** Local-Logistics Protocol (formerly Commuter-Share)
**Sector:** B2B SaaS / Logistics Infrastructure
**Date:** July 2026

---

## 1. Executive Summary
Local-Logistics Protocol is an asset-light, B2B SaaS trust infrastructure company. We have decoupled trust from employment in the local logistics sector. By utilizing a proprietary "Cryptographic Chain-of-Custody" (Collateralized Staking + TOTP Handshakes), we allow independent local merchants (pharmacies, hardware stores) to safely dispatch high-value goods using unvetted, organic gig-workers. We do not hire couriers, we do not subsidize rides, and we do not carry logistics insurance. We simply provide the protocol.

## 2. Investment Memo
**Thesis:** The urban logistics market is plagued by low margins and massive capital burn (e.g., Gorillas, Getir) because companies attempt to vertically integrate fleets and real estate. By pivoting from a courier company to a **Decoupled Logistics Protocol**, we capture venture-scale SaaS margins. We shift the operational burden to the network while monetizing the transaction and the routing software.
**Recommendation:** Strong Buy. The pivot neutralizes traditional logistics risk profiles (worker misclassification, theft shrinkage, micro-transaction API bleed).

## 3. Market Analysis
- **TAM:** Global hyper-local last-mile delivery.
- **Trend:** The collapse of 15-minute VC-subsidized grocery delivery has left independent high-street retailers without a cheap, reliable, same-day delivery option. Traditional couriers (Evri, Royal Mail) cannot provide instant local drops cost-effectively.
- **Target Audience:** High-volume, high-density local commerce (pharmacies, independent hardware, print shops) located in dense "University Wedges".

## 4. Competitive Analysis
Based on an audit of 150 global competitors:
- **Food Delivery (UberEats, Deliveroo):** Massive driver liquidity but focused exclusively on high-margin food/restaurant APIs.
- **Traditional Couriers (Evri, DPD):** Excellent national routing, terrible/expensive instant local point-to-point.
- **B2B Routing SaaS (Bringg, Onfleet):** Provide enterprise routing but do not provide the P2P trust layer for unvetted crowdsourced fleets.
- **Our Moat:** We are the only platform providing a zero-trust cryptographic handshake specifically designed for unvetted pedestrian/cyclist gig-workers.

## 5. SWOT Analysis
- **Strengths:** Zero capital expenditure on fleets, immunity to *Uber v Aslam* worker classification, self-insuring network via staking.
- **Weaknesses:** Highly dependent on initial geographic density (the cold-start problem).
- **Opportunities:** Licensing the SaaS protocol to existing mid-sized courier firms globally.
- **Threats:** Stripe/payment gateways altering their fixed-fee structures, or the FCA reclassifying collateralized staking as regulated e-money.

## 6. Porter's Five Forces
1. **Threat of New Entrants (Medium):** Software is easily replicated, but achieving two-sided hyper-local density is brutally difficult.
2. **Power of Suppliers / Couriers (High):** Gig-workers are mercenary. If the "True Marketplace" pricing doesn't yield £10+/hour, they will abandon the app.
3. **Power of Buyers / Merchants (Medium):** Local shops are price-sensitive but highly loyal once integrated into their POS.
4. **Threat of Substitutes (High):** Merchants defaulting back to using family members or "cash-in-hand" local riders.
5. **Competitive Rivalry (Extreme):** Logistics is a bloodbath, but pure SaaS infrastructure has significantly fewer direct competitors.

## 7. Business Model
We operate a Hybrid B2B Local Commerce & True Marketplace model:
- **B2B SaaS Subscription:** Local shops pay £49/month for access to the routing dispatch dashboard and discounted network fees.
- **Marketplace Platform Fee:** A 15% transaction fee added to the courier's self-set minimum rate.

## 8. Unit Economics
Relying on £5 micro-transactions is fatal. Our optimized unit economics utilize **Aggregated Billing**:
- **Courier Rate:** ~£4.00 (Self-Set by Courier).
- **Platform Fee (15%):** £0.60.
- **API Costs:** £0.00 per transaction (Onfido KYC is a one-time onboarding cost; handshakes are free TOTP).
- **Stripe Costs:** -£0.03 (Amortized via weekly aggregated billing or B2B monthly invoicing).
- **Net Margin:** ~£0.57 per drop. 

## 9. Financial Analysis
- **Capital Efficiency:** Because we do not subsidize deliveries, our cash burn is restricted purely to R&D (software engineering) and localized B2B Field Sales. 
- **The "Anchor Courier" Budget:** For the first 90 days in a new node (e.g., UCL Campus), we will spend £15,000/month on "Anchor Couriers" (paid shift workers) to guarantee SLAs for early B2B clients until organic P2P density takes over.

## 10. Security Review
- **Collateralized Staking:** Couriers authorize a £50 hold on their card to accept high-value items. If the item is stolen, the stake is slashed to refund the sender.
- **Chain of Custody:** Handshakes are strictly above-ground (mandating 4G/5G). Sender and courier scan dynamic TOTP QR codes to create an immutable GPS-stamped receipt.
- **Tamper-Evident Bags:** Standardized sealing guarantees the courier cannot inspect or alter the contents.

## 11. GDPR Assessment
- **Data Minimization:** No background checks means we don't store sensitive criminal records. Biometric KYC (Onfido) is delegated to a compliant third party.
- **Camera Sandbox:** Package proof-of-pickup photos are sandboxed, never touching the user's personal camera roll, preventing accidental leaks of shipping labels or sender addresses.

## 12. UK Legal Review
- **Employment Law:** We survive the Supreme Court's *Uber BV v Aslam* ruling by operating a "True Marketplace." Couriers set their own "Minimum Acceptable Rate per Mile." We act purely as a SaaS intermediary, stripping away the pricing control that defines worker status.
- **Financial Compliance:** The £50 stake is a pre-authorized card hold (Stripe Issuing), not a stored-value wallet, bypassing strict FCA e-money regulations.

## 13. Technical Architecture Review
- **Frontend:** React Native (iOS/Android). Stripped of unnecessary offline BLE libraries for stability.
- **Backend:** Node.js / Express microservices hosted on AWS.
- **Database:** PostgreSQL with PostGIS extensions for rapid spatial indexing and geographic matching.
- **Integrations:** Stripe (Payments/Issuing), Onfido (One-time KYC).

## 14. Product Roadmap
- **Phase 1 (Months 1-3):** Build core TOTP handshake protocol and True Marketplace pricing slider. Launch "UCL Wedge" with paid Anchor Couriers.
- **Phase 2 (Months 4-6):** Onboard 15 independent pharmacies. Phase out Anchor Couriers as organic student density reaches 500 active users.
- **Phase 3 (Months 7-12):** Expand to 3 additional university nodes. Introduce B2B POS integrations.

## 15. Funding Strategy
- **Pre-Seed / Seed:** Raising £750k to fund 12 months of runway.
- **Allocation:** 50% Engineering (building the SaaS protocol), 30% Local B2B Field Sales, 20% Anchor Courier subsidies (Liquidity bootstrapping).
- **Target Investors:** B2B SaaS funds, PropTech funds, and UK Innovator Founder Endorsing Bodies.

## 16. Exit Opportunities
- **Acquisition by Aggregators:** Software providers like Deliverect or Bringg acquiring the protocol to offer P2P capabilities to their restaurant clients.
- **Acquisition by Legacy Logistics:** DPD, UPS, or Royal Mail acquiring the technology to modernize their hyper-local point-to-point capabilities without hiring unionized workforces.
