# B2B Web Dashboard

## 1. Target Audience
Local SME retailers (Coffee roasters, vintage shops, local bakeries) who need to dispatch 5-50 items per day.

## 2. Core Features (Phase 2)
- **Bulk CSV Upload:** Upload a spreadsheet of names, phone numbers, and postcodes. The system geocodes them and creates 50 draft packages.
- **API Access:** Webhook and REST API access so they can integrate directly into their Shopify stores (e.g., when an order is placed, generate a delivery intent).
- **Consolidated Billing:** Instead of paying £5 individually via Apple Pay per package, the retailer is invoiced monthly via Stripe Billing.

## 3. Technology Stack
- **Frontend:** Next.js (React) hosted on Vercel.
- **Styling:** Tailwind CSS with shadcn/ui components.
- **Auth:** NextAuth.js linking to the core PostgreSQL user database.

## 📝 Remaining Unknowns (TODOs)
- **Shopify App Store:** Determine the technical requirements and review process for building an official Shopify Plugin for our service.
