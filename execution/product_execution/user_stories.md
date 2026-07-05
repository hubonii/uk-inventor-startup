# User Stories — Local-Logistics Protocol

> Last updated: July 2026 | 48 User Stories across 4 Roles

---

## Roles

| Role | Description |
|---|---|
| **Sender** | Individual or business user who needs to send a package |
| **Courier** | Gig worker who delivers packages for payment |
| **Merchant** | B2B business customer with recurring delivery needs |
| **Admin** | Platform operator managing the system |

---

## Sender Stories (12)

### S-01: Account Registration
**As a** Sender, **I want to** create an account using my phone number, **so that** I can quickly start sending packages without a complex signup process.

**Acceptance Criteria:**
- [ ] Sender enters phone number and receives OTP via SMS within 10 seconds
- [ ] OTP is 6 digits and expires after 5 minutes
- [ ] After verification, sender sets display name and saves a payment method
- [ ] Account is active immediately after payment method added
- [ ] Duplicate phone numbers are rejected with clear error message

---

### S-02: Create Delivery Request
**As a** Sender, **I want to** describe my package and set pickup/drop-off locations, **so that** couriers can see what needs delivering and where.

**Acceptance Criteria:**
- [ ] Form captures: package type (document/small parcel/fragile/food), size (S/M/L), special instructions
- [ ] Address fields use autocomplete with geocoding validation
- [ ] Both addresses must be within the active service zone
- [ ] Estimated distance and delivery time displayed before submission
- [ ] Package photo upload is optional but encouraged (UI prompt)

---

### S-03: View Courier Quotes
**As a** Sender, **I want to** see price quotes from available couriers, **so that** I can choose the best combination of price, speed, and reliability.

**Acceptance Criteria:**
- [ ] At least 1 courier quote displayed within 30 seconds of request creation
- [ ] Each quote shows: courier name, profile photo, rating (stars), price, estimated pickup time, transport mode
- [ ] Quotes sorted by recommended (multi-factor) by default, with sort options for price and speed
- [ ] Quotes refresh automatically every 60 seconds
- [ ] "No couriers available" state shown with retry option and notification signup

---

### S-04: Confirm and Pay
**As a** Sender, **I want to** select a courier and pay securely, **so that** my delivery is confirmed and the courier is notified.

**Acceptance Criteria:**
- [ ] Sender taps "Confirm" on chosen courier quote
- [ ] Payment method charged (or authorised) immediately
- [ ] Confirmation screen shows: delivery ID, courier details, estimated pickup time
- [ ] Courier receives push notification within 5 seconds of confirmation
- [ ] Sender can cancel within 2 minutes for full refund (courier not yet en route)

---

### S-05: Track Delivery in Real Time
**As a** Sender, **I want to** see my delivery's live location on a map, **so that** I know exactly where my package is at all times.

**Acceptance Criteria:**
- [ ] Map shows courier's live position (updated every 10 seconds)
- [ ] Status bar shows current phase: Confirmed → Courier En Route → Package Picked Up → In Transit → Delivered
- [ ] Each status change triggers push notification
- [ ] ETA updates dynamically based on courier position
- [ ] Delivery timeline shows timestamps for each status change

---

### S-06: Pickup Handshake
**As a** Sender, **I want to** verify the courier's identity through a QR code scan, **so that** I have proof that I handed my package to the right person.

**Acceptance Criteria:**
- [ ] QR code displayed on sender's screen when courier arrives
- [ ] QR contains time-limited TOTP code (30-second rotation, 5-minute validity)
- [ ] Courier scans QR; success confirmation shown on both devices
- [ ] GPS location and timestamp recorded for both parties
- [ ] If QR scan fails 3 times, fallback to manual 6-digit code entry

---

### S-07: Receive Delivery Confirmation
**As a** Sender, **I want to** receive confirmation when my package is delivered, **so that** I know it arrived safely.

**Acceptance Criteria:**
- [ ] Push notification sent within 10 seconds of delivery handshake completion
- [ ] Confirmation includes: delivery time, recipient confirmation status, chain-of-custody receipt link
- [ ] Receipt shows full timeline: creation → pickup → transit → delivery with timestamps and GPS coordinates
- [ ] Receipt downloadable as PDF

---

### S-08: Rate Courier
**As a** Sender, **I want to** rate my courier after delivery, **so that** future senders can make informed choices.

**Acceptance Criteria:**
- [ ] Rating prompt appears after delivery confirmation (1-5 stars)
- [ ] Optional text comment (max 250 characters)
- [ ] Rating is mandatory before creating next delivery request
- [ ] Rating prompt can be dismissed but reappears on next app open
- [ ] Ratings are anonymous (courier sees star count, not sender identity with comment)

---

### S-09: View Delivery History
**As a** Sender, **I want to** see all my past deliveries, **so that** I can track spending and reorder to frequent destinations.

**Acceptance Criteria:**
- [ ] List view of all deliveries (most recent first)
- [ ] Each entry shows: date, from/to addresses, courier name, cost, status, rating given
- [ ] Filter by: date range, status (completed/cancelled/disputed)
- [ ] "Repeat delivery" button pre-fills form with same addresses and package type
- [ ] Export delivery history as CSV

---

### S-10: Cancel Delivery
**As a** Sender, **I want to** cancel a delivery before pickup, **so that** I'm not charged for a delivery I no longer need.

**Acceptance Criteria:**
- [ ] Cancel button available until courier confirms pickup (scans QR)
- [ ] Cancellation within 2 minutes of confirmation: full refund
- [ ] Cancellation after 2 minutes but before pickup: 50% refund (courier compensation)
- [ ] Cancellation after pickup: no refund (dispute process available)
- [ ] Courier notified immediately upon cancellation

---

### S-11: Set Favourite Addresses
**As a** Sender, **I want to** save frequently used addresses, **so that** I can create deliveries faster.

**Acceptance Criteria:**
- [ ] "Save this address" toggle on delivery creation form
- [ ] Saved addresses appear as suggestions when typing in address field
- [ ] Can label addresses (e.g., "Home", "Office", "Mum's house")
- [ ] Maximum 10 saved addresses per account
- [ ] Addresses can be edited or deleted from settings

---

### S-12: Contact Courier
**As a** Sender, **I want to** message my courier during an active delivery, **so that** I can provide additional instructions or coordinate pickup timing.

**Acceptance Criteria:**
- [ ] In-app chat available from match confirmation until delivery completion
- [ ] Messages delivered in real-time (WebSocket)
- [ ] Chat history preserved for dispute resolution (30-day retention)
- [ ] Quick-reply templates: "I'm running late", "Package is at reception", "Call me when you arrive"
- [ ] Phone number masked — no direct phone access between parties

---

## Courier Stories (12)

### C-01: Register as Courier
**As a** Courier, **I want to** sign up and verify my identity, **so that** I can start accepting delivery jobs.

**Acceptance Criteria:**
- [ ] Phone number OTP verification
- [ ] Government ID upload with image quality check
- [ ] Selfie liveness check (anti-spoofing)
- [ ] Entire KYC process completable in <15 minutes
- [ ] Clear progress indicator showing remaining steps

---

### C-02: Deposit Collateral Stake
**As a** Courier, **I want to** understand and deposit my £50 stake, **so that** I can activate my courier account with confidence that my deposit is protected.

**Acceptance Criteria:**
- [ ] Clear explanation of stake purpose, refund conditions, and deduction scenarios
- [ ] Payment via debit/credit card through Stripe
- [ ] Confirmation receipt with stake transaction ID
- [ ] Stake balance visible in courier profile at all times
- [ ] Refund process documented with estimated 14-day timeline

---

### C-03: Set Delivery Rates
**As a** Courier, **I want to** set my own delivery rates, **so that** I can earn what I consider fair for each job.

**Acceptance Criteria:**
- [ ] Default rate configurable in profile (applied to all jobs)
- [ ] Per-job rate override available when viewing job details
- [ ] Minimum rate floor enforced (£2.50)
- [ ] Suggested rate range shown based on distance, time, and historical data
- [ ] Rate displayed to sender includes 15% platform fee transparency note

---

### C-04: Browse Available Jobs
**As a** Courier, **I want to** see available delivery jobs near me, **so that** I can choose jobs that suit my location and schedule.

**Acceptance Criteria:**
- [ ] Job feed shows deliveries within courier's configured radius
- [ ] Each job shows: pickup/dropoff addresses (area only, not exact until accepted), package type, sender rating, estimated distance, time window
- [ ] Jobs sorted by proximity by default; sortable by price, distance, time
- [ ] Map view option showing job locations as pins
- [ ] Real-time updates — new jobs appear without manual refresh

---

### C-05: Accept Delivery Job
**As a** Courier, **I want to** accept a job and navigate to the pickup location, **so that** I can complete the delivery efficiently.

**Acceptance Criteria:**
- [ ] "Accept" button with confirmation dialog
- [ ] After acceptance, exact pickup address revealed with navigation link (Google Maps / Apple Maps)
- [ ] 10-minute window to reach pickup location (configurable per job)
- [ ] Sender notified of courier acceptance and ETA
- [ ] Courier can cancel before pickup with minor rating impact (tracked)

---

### C-06: Pickup Handshake (Scan QR)
**As a** Courier, **I want to** scan the sender's QR code to confirm package pickup, **so that** there's cryptographic proof I received the package.

**Acceptance Criteria:**
- [ ] Camera opens with QR scanner overlay
- [ ] Successful scan shows: package details, sender name, delivery address
- [ ] Courier confirms package matches description (checkbox)
- [ ] GPS and timestamp recorded automatically
- [ ] Failed scan after 3 attempts offers manual code entry fallback

---

### C-07: Navigate to Drop-Off
**As a** Courier, **I want to** see turn-by-turn navigation to the delivery address, **so that** I can deliver quickly without getting lost.

**Acceptance Criteria:**
- [ ] Deep link to preferred navigation app (Google Maps, Waze, Apple Maps)
- [ ] In-app simplified map showing destination pin and courier position
- [ ] Distance remaining and ETA displayed
- [ ] "I've arrived" button to notify recipient
- [ ] Contact recipient option (masked phone/in-app chat)

---

### C-08: Delivery Handshake (Present QR)
**As a** Courier, **I want to** present a QR code to the recipient for delivery confirmation, **so that** there's cryptographic proof I delivered the package.

**Acceptance Criteria:**
- [ ] QR code auto-generated when courier taps "Arrived at destination"
- [ ] Recipient scans courier's QR OR enters 6-digit code manually
- [ ] Delivery confirmed on both devices with visual and haptic feedback
- [ ] Payment released to courier upon confirmation
- [ ] "Recipient unavailable" flow: attempt contact → wait 10 min → return package flow

---

### C-09: View Earnings
**As a** Courier, **I want to** see my earnings in real-time, **so that** I can track my income and plan my schedule.

**Acceptance Criteria:**
- [ ] Dashboard shows: today's earnings, this week, this month, all-time
- [ ] Each delivery shows: amount earned, platform fee deducted, net payout
- [ ] Payout schedule displayed (instant/daily/weekly)
- [ ] Pending payouts vs completed payouts clearly distinguished
- [ ] Tax-friendly annual earnings export (P&L summary for self-assessment)

---

### C-10: Manage Availability
**As a** Courier, **I want to** toggle my availability on/off, **so that** I only receive job notifications when I'm ready to work.

**Acceptance Criteria:**
- [ ] One-tap "Go Online" / "Go Offline" toggle
- [ ] When online, GPS location shared with platform (every 10 seconds)
- [ ] When offline, no job notifications and no location tracking
- [ ] Schedule availability for future days (calendar view)
- [ ] Auto-offline after 30 minutes of no job acceptance

---

### C-11: View Rating and Trust Score
**As a** Courier, **I want to** see my rating and trust score, **so that** I understand my standing and can work to improve it.

**Acceptance Criteria:**
- [ ] Overall rating (1-5 stars, average of last 50 deliveries)
- [ ] Trust score (0-100) with breakdown by factor
- [ ] Current trust tier (Bronze/Silver/Gold) with progress to next tier
- [ ] Recent ratings feed (last 10, anonymised)
- [ ] Tips for improving score displayed for scores below 70

---

### C-12: Request Stake Refund
**As a** Courier, **I want to** request my £50 stake back when I stop couriering, **so that** I'm not locked into the platform.

**Acceptance Criteria:**
- [ ] "Close account and refund stake" option in settings
- [ ] Eligibility check: zero open disputes, no pending deliveries
- [ ] If eligible: 14-day processing period, then refund to original payment method
- [ ] If ineligible: clear message explaining blocking issues
- [ ] Confirmation email with refund timeline and tracking

---

## Merchant Stories (12)

### M-01: Merchant Registration
**As a** Merchant, **I want to** register my business for the delivery platform, **so that** I can start dispatching goods to my customers.

**Acceptance Criteria:**
- [ ] Business registration form: company name, registration number, address, category
- [ ] Companies House API lookup validates registration number
- [ ] Primary contact person details (name, email, phone)
- [ ] Billing setup via Stripe (card or direct debit)
- [ ] Account activated within 24 hours (manual KYB review)

---

### M-02: Create Single Delivery
**As a** Merchant, **I want to** dispatch a single delivery to a customer, **so that** my customer receives their purchase the same day.

**Acceptance Criteria:**
- [ ] Delivery form pre-fills merchant address as pickup
- [ ] Customer address entry with autocomplete
- [ ] Package type and value declaration
- [ ] Courier matched automatically (no manual selection required for merchants)
- [ ] Delivery added to merchant's active deliveries dashboard

---

### M-03: Batch Dispatch
**As a** Merchant, **I want to** upload multiple deliveries at once, **so that** I can dispatch all my daily orders efficiently.

**Acceptance Criteria:**
- [ ] CSV upload template downloadable from dashboard
- [ ] CSV validation: required fields, address format, package type
- [ ] Preview screen showing parsed deliveries with error highlighting
- [ ] One-click "Dispatch All" to submit batch for matching
- [ ] Individual delivery editing within batch before dispatch

---

### M-04: Track All Active Deliveries
**As a** Merchant, **I want to** see all my active deliveries on a single dashboard, **so that** I can monitor my operations in real-time.

**Acceptance Criteria:**
- [ ] Map view showing all active deliveries with status-coded pins
- [ ] List view with sortable columns: customer, status, courier, ETA, created time
- [ ] Status filter: All, Pending Match, In Transit, Delivered, Failed
- [ ] Click on delivery for detail view (timeline, courier info, tracking link)
- [ ] Auto-refresh every 30 seconds

---

### M-05: Customer Notification Branding
**As a** Merchant, **I want to** have delivery notifications sent under my brand, **so that** my customers have a seamless experience.

**Acceptance Criteria:**
- [ ] Merchant uploads logo and sets brand colour in settings
- [ ] Customer tracking page shows merchant branding (not Local-Logistics branding)
- [ ] SMS notifications include merchant name: "[MerchantName]: Your delivery is on its way!"
- [ ] Tracking link URL format: track.locallogistics.co/[merchant-slug]/[delivery-id]
- [ ] Email notifications use merchant logo in header

---

### M-06: View Analytics
**As a** Merchant, **I want to** see delivery analytics, **so that** I can optimise my operations and understand delivery performance.

**Acceptance Criteria:**
- [ ] Dashboard widgets: deliveries today/week/month, avg delivery time, avg cost, success rate
- [ ] Charts: deliveries over time (line), hourly distribution (bar), cost trend (line)
- [ ] Courier leaderboard: top couriers by deliveries completed and rating
- [ ] Delivery heatmap showing customer concentration
- [ ] Date range selector with preset options (today, this week, this month, custom)

---

### M-07: View and Pay Invoices
**As a** Merchant, **I want to** view my monthly invoices, **so that** I can manage my delivery spend.

**Acceptance Criteria:**
- [ ] Monthly invoice generated automatically on 1st of each month
- [ ] Invoice breakdown: SaaS fee + itemised delivery charges
- [ ] Invoice downloadable as PDF with VAT details
- [ ] Payment auto-charged via saved payment method (net-7)
- [ ] Email notification when invoice is generated and when payment is processed

---

### M-08: Manage API Keys
**As a** Merchant, **I want to** generate API keys for POS integration, **so that** deliveries can be triggered automatically from my existing systems.

**Acceptance Criteria:**
- [ ] "Create API Key" button in settings generates key pair (public + secret)
- [ ] Secret key shown once only; copy-to-clipboard functionality
- [ ] Keys can be named (e.g., "POS Integration", "Website")
- [ ] Keys can be revoked instantly
- [ ] Usage logs showing API calls per key

---

### M-09: Set Delivery Preferences
**As a** Merchant, **I want to** configure default delivery settings, **so that** dispatching is faster and consistent.

**Acceptance Criteria:**
- [ ] Default package type per merchant category (e.g., pharmacy → "medical supplies")
- [ ] Preferred courier pool (opt-in dedicated couriers)
- [ ] Default delivery window (e.g., "within 2 hours")
- [ ] Maximum delivery price threshold (auto-reject quotes above limit)
- [ ] Operating hours (no deliveries dispatched outside set hours)

---

### M-10: Manage Staff Access
**As a** Merchant, **I want to** add staff members to my account, **so that** my team can dispatch deliveries without sharing my login.

**Acceptance Criteria:**
- [ ] Invite staff via email
- [ ] Roles: Admin (full access), Dispatcher (create/track deliveries), Viewer (read-only)
- [ ] Staff see their own activity within the shared merchant account
- [ ] Admin can revoke staff access instantly
- [ ] Audit log of staff actions

---

### M-11: Request Dedicated Courier
**As a** Merchant, **I want to** request a dedicated courier for busy periods, **so that** I have guaranteed delivery capacity.

**Acceptance Criteria:**
- [ ] "Request dedicated courier" form: time period, estimated deliveries, location
- [ ] Platform matches available Gold-tier couriers
- [ ] Dedicated courier appears in merchant's courier pool
- [ ] Guaranteed availability during booked hours
- [ ] Pricing: premium rate (1.5x standard) for guaranteed capacity

---

### M-12: Export Chain-of-Custody Reports
**As a** Merchant, **I want to** download chain-of-custody reports for my deliveries, **so that** I have compliance documentation for regulated goods.

**Acceptance Criteria:**
- [ ] Generate report for single delivery or date range
- [ ] Report includes: delivery ID, package details, all handshake timestamps, GPS coordinates, courier identity, digital signatures
- [ ] Export as PDF (branded) or CSV (data)
- [ ] Reports retained for 7 years (regulatory compliance)
- [ ] Batch export for audits (up to 1,000 deliveries)

---

## Admin Stories (12)

### A-01: View Platform Dashboard
**As an** Admin, **I want to** see real-time platform metrics, **so that** I can monitor operational health.

**Acceptance Criteria:**
- [ ] Dashboard shows: active deliveries now, couriers online, match rate, avg delivery time, revenue today
- [ ] Trend comparison (today vs yesterday, this week vs last week)
- [ ] Alert indicators for anomalies (match time > 10min, delivery failure rate > 5%)
- [ ] Refresh interval: 30 seconds
- [ ] Mobile-responsive for on-the-go monitoring

---

### A-02: Manage Users
**As an** Admin, **I want to** search and manage all platform users, **so that** I can handle support requests and enforce policies.

**Acceptance Criteria:**
- [ ] Search by: name, phone, email, user ID
- [ ] User profile shows: account details, activity history, rating, trust score, stake status
- [ ] Actions: suspend, ban, reset password, add note, adjust trust score
- [ ] Suspension triggers notification to user with reason
- [ ] Audit trail of all admin actions on user accounts

---

### A-03: Manage Service Zones
**As an** Admin, **I want to** define and modify service zones, **so that** the platform only operates in areas with sufficient courier density.

**Acceptance Criteria:**
- [ ] Draw polygons on map to define zones
- [ ] Name and categorise zones (active, planned, paused)
- [ ] Set zone-specific parameters: minimum couriers for activation, rate floors
- [ ] Deliveries outside active zones are rejected with "coming soon" message
- [ ] Zone changes take effect immediately (no deploy required)

---

### A-04: Review Disputes
**As an** Admin, **I want to** review and resolve delivery disputes, **so that** both parties receive fair outcomes.

**Acceptance Criteria:**
- [ ] Dispute queue showing all open disputes (oldest first)
- [ ] Dispute detail: delivery timeline, both parties' claims, evidence (photos), chat history
- [ ] Resolution actions: refund sender (full/partial), deduct from courier stake, no action
- [ ] Resolution notification sent to both parties with explanation
- [ ] Resolution SLA tracking (target: 72 hours)

---

### A-05: View Financial Reports
**As an** Admin, **I want to** see financial reports, **so that** I can track revenue, costs, and financial health.

**Acceptance Criteria:**
- [ ] Revenue report: platform fees + SaaS subscriptions, daily/weekly/monthly
- [ ] Payout report: total courier payouts, pending, completed
- [ ] Stake report: total held, deductions, refunds
- [ ] P&L auto-generated monthly
- [ ] Export all reports as CSV or PDF

---

### A-06: Configure Platform Settings
**As an** Admin, **I want to** adjust platform configuration without code changes, **so that** I can respond quickly to operational needs.

**Acceptance Criteria:**
- [ ] Configurable: platform fee %, minimum rate floor, matching radius, TOTP validity window
- [ ] Feature flags: enable/disable features per zone or user segment
- [ ] Changes logged with admin identity and timestamp
- [ ] Preview mode: simulate configuration change impact before applying
- [ ] Rollback to previous configuration one-click

---

### A-07: Monitor System Health
**As an** Admin, **I want to** see system health metrics, **so that** I can identify and resolve technical issues quickly.

**Acceptance Criteria:**
- [ ] Uptime monitoring: API, database, payment gateway, SMS provider
- [ ] Error rate tracking (5xx errors per minute)
- [ ] Response time percentiles (p50, p95, p99)
- [ ] Active WebSocket connections count
- [ ] Alerting via Slack/email when thresholds breached

---

### A-08: Generate KPI Reports
**As an** Admin, **I want to** generate investor-ready KPI reports, **so that** I can communicate progress to stakeholders.

**Acceptance Criteria:**
- [ ] Templated report: MRR, GTV, active users, drops/day, LTV:CAC, churn rates
- [ ] Month-over-month trend charts
- [ ] Cohort analysis tables (courier and merchant retention)
- [ ] Exportable as PDF with company branding
- [ ] Scheduled auto-generation (monthly, sent to distribution list)

---

### A-09: Manage Anchor Courier Programme
**As an** Admin, **I want to** manage the Anchor Courier incentive programme, **so that** I can control subsidies and track programme effectiveness.

**Acceptance Criteria:**
- [ ] Enrol/remove couriers from Anchor programme
- [ ] Set guaranteed hourly rate and maximum weekly hours per courier
- [ ] Track: subsidy cost per courier, deliveries completed, organic demand filled
- [ ] Auto-calculate programme ROI (subsidy cost vs revenue generated)
- [ ] Programme end-date with gradual phase-out scheduling

---

### A-10: Handle GDPR Requests
**As an** Admin, **I want to** process data access and deletion requests, **so that** the platform complies with GDPR.

**Acceptance Criteria:**
- [ ] "Data Requests" queue in admin panel
- [ ] Subject Access Request (SAR): auto-generate downloadable data package (JSON/PDF)
- [ ] Right to Erasure: anonymise user data while preserving aggregate analytics
- [ ] Processing SLA: 30 days (GDPR requirement), target 7 days
- [ ] Audit log of all GDPR actions

---

### A-11: Manage Notifications
**As an** Admin, **I want to** manage notification templates and send platform-wide announcements, **so that** I can communicate with users effectively.

**Acceptance Criteria:**
- [ ] Template editor for: SMS, push notification, email
- [ ] Variable insertion: {user_name}, {delivery_id}, {amount}, etc.
- [ ] Broadcast announcements to: all users, all couriers, all merchants, specific zones
- [ ] Schedule broadcasts for future delivery
- [ ] Delivery tracking: sent, delivered, opened (email only)

---

### A-12: Onboard New City
**As an** Admin, **I want to** configure and launch a new city, **so that** expansion follows a standardised process.

**Acceptance Criteria:**
- [ ] City setup wizard: define zones, set local parameters, activate payment provider
- [ ] Checklist: legal review complete, minimum 20 couriers registered, 5 merchants signed
- [ ] Soft launch mode: invite-only with limited daily capacity
- [ ] City-specific analytics dashboard
- [ ] Go/no-go criteria checklist with sign-off

---

*Each user story is linked to its parent Epic in epics_and_features.md. Sprint assignments are detailed in sprint_planning.md.*
