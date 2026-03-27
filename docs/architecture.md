# Architecture Overview

## System Design Philosophy
Build a two-sided marketplace where both sides
(brands and creators) operate independently
but are connected through a shared campaign and
attribution layer. Each side has its own onboarding,
dashboard, and monetization surface.

---

## Brand-Side Architecture

### Onboarding & Profile
- Company profile stored with industry categorization
- Wallet setup linked to payment gateway
- Billing configuration for campaign funding and platform fees

### Product CMS
- Hierarchical structure: Category → Subcategory → Product
- Each product stores: name, description, variants,
  pricing, inventory status
- Bulk upload via CSV for large catalogs
- Real-time preview of catalog structure
- Products are the base unit — campaigns and forms
  are always linked to a Product ID

### Form Builder
- Forms are decoupled from campaigns and tied to Product IDs
- Same form is reusable across multiple campaigns
  for the same product
- Field types: text, dropdown, checkbox, date
- Form objectives: lead generation, pre-order,
  customer feedback
- Forms embeddable in affiliate links and external
  landing pages
- Submissions stored against Product ID + Campaign ID
  for attribution

### Campaign Wizard
- Step 1: Select product(s) from CMS
- Step 2: Choose campaign type
  - CPC — Cost per Click
  - CPV — Cost per View
  - CPP — Cost per Purchase
  - CPCall — Cost per Call
- Step 3: Set budget and bid amount
- Step 4: Define audience targeting
  (age, location, interests)
- Step 5: Set campaign duration and schedule
- Step 6: Affiliate links auto-generated
  with UTM parameters per product per campaign

### Creator Discovery
- AI-powered matching engine
  based on: niche, engagement rate,
  audience size, location,
  past campaign performance
- Manual search and filter as fallback
  during cold start phase
- Collaboration invite flow
  with status tracking: Pending / Accepted / Rejected

### Campaign Dashboard
- Real-time metrics: clicks, views, conversions, ROI
- Breakdown by: creator, product, campaign type
- Fraud detection: anomaly alerts on click patterns
- Controls: pause, resume, edit budget
- Exportable reports: PDF and CSV

### Payment Dashboard
- Wallet balance and recharge
- Automated payouts to creator wallets
  post campaign settlement
- Transaction history with downloadable invoices
- Platform fee deducted at settlement

---

## Creator-Side Architecture

### Onboarding & Profile
- SSO via social platforms using OAuth
- Profile: niche, social handles, audience size
- Verification via social media authentication

### Storefront Builder
- Pre-built templates by category
  (fashion, services, lifestyle, etc.)
- Add products from partnered brands
- Customize layout, colors, branding
- Storefront URL linkable from social media bio
- Responsive across web and mobile

### Campaign Marketplace
- Browse active campaigns by niche, brand, payout type
- View campaign requirements before accepting
- Accept campaign → affiliate link generated
  and delivered to creator
- Share links via storefront or directly on social channels

### Affiliate Attribution Layer
- Every link tagged with UTM parameters:
  - utm_source: platform
  - utm_medium: campaign type
  - utm_campaign: campaign ID
  - utm_content: creator ID
- Clicks and conversions tracked in real-time
- Source flagged if link shared outside approved channels

### Analytics Dashboard
- Campaign metrics: clicks, conversions, orders, revenue
- Storefront metrics: product views, sales, revenue
- Course and subscription metrics: purchases, renewals
- Community metrics: subscriber count, engagement
- Payout status and history per campaign

### Monetization Layer
Four revenue streams consolidated in one platform:

1. Campaign Commissions
   - Earned per click, view, purchase, or call
   - Based on campaign type and agreed bid

2. Storefront Sales
   - Direct product sales via creator storefront
   - Revenue tracked separately from campaign commissions

3. Community Subscriptions
   - Followers subscribe to creator community
   - Monthly or yearly subscription plans
   - Integrated via third-party community API

4. Course and Subscription Sales
   - Creators build courses: video, text, quizzes
   - One-time purchase or subscription access
   - Revenue tracked in unified earnings dashboard

### Earnings & Payout
- All revenue streams consolidated in one dashboard
- Payout hold period applied post campaign settlement
  for fraud and chargeback protection
- Hold period visible to creator with unlock date
- Withdrawal options: bank transfer, digital wallets
- Automated payout triggered after hold clears
- Transaction log maintained for all withdrawals

---

## Shared Infrastructure

### Authentication
- Brand side: Email OTP or SSO (Google, LinkedIn)
- Creator side: Email or SSO (Google, Instagram)
  with OAuth social verification
- Session management with secure token storage

### Affiliate Link System
- Unique link generated per product per campaign per creator
- UTM parameters embedded at generation
- URL shortening for clean sharing
- Link remains valid but inactive if campaign is paused
- Link activity tracked independently of campaign status

### Fraud Detection
- Anomaly detection on click patterns
  (velocity, geographic clustering, device fingerprinting)
- Alerts surfaced on brand dashboard before payout
- Payout held automatically on flagged campaigns
- Manual review window before account action taken

### Payout Engine
- Settlement triggered at campaign end
- Hold period applied per campaign type
- Dispute window open for brands during hold
- On hold clearance: payout queued automatically
- Retry logic with exponential backoff on gateway failure
- All transactions logged with downloadable receipts

### Community Integration
- Third-party community platform integrated via API
- WebSocket used for real-time community updates
- Graceful degradation: community tab shows maintenance
  state if API is down
- Core campaign and payout features unaffected by
  community API downtime

### Analytics & Reporting
- Real-time event tracking on all user actions
  (clicks, conversions, form submissions, payouts)
- Breakdown available by: creator, product,
  campaign, time period
- Exportable as PDF and CSV
- Historical data retained for trend analysis

---

 