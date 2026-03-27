# PRD — Performance Marketing & Creator Monetization Platform

## Problem Statement
Brands had no reliable way to run performance-based influencer
campaigns with measurable ROI. Creators lacked a unified platform
to manage brand deals, track earnings, and build monetization
streams independent of one-off campaigns.

## Goals
| Goal | Metric |
|---|---|
| Reduce brand campaign setup time | Time to first campaign launch |
| Give brands measurable ROI | Campaign conversion rate |
| Reduce creator income unpredictability | Revenue streams per creator |
| Reduce payout fraud and disputes | Payout dispute rate |
| Increase creator platform retention | Storefront activation rate |

## Users

### Brands
Marketing teams at D2C and service companies running
performance-based campaigns at scale.

Pain points:
- No attribution on influencer spend
- Paying for fake engagement with no fraud protection
- Manual coordination across multiple creators
- No way to run multiple campaigns simultaneously

### Creators
Content creators across niches — fashion, finance,
lifestyle, services — monetizing their audience.

Pain points:
- Unpredictable, deal-dependent income
- No unified earnings dashboard
- Delayed or missed payouts
- No owned monetization layer independent of brands

## Scope

### In (v1)
- Brand onboarding, wallet, and billing
- Hierarchical product CMS
- Custom form builder per product
- Campaign wizard with CPC, CPV, CPP, CPCall models
- Unique affiliate link generation per campaign
- AI-powered creator discovery and matching
- Real-time campaign analytics and fraud detection
- Creator onboarding with OAuth social verification
- Creator storefront builder
- Campaign marketplace for creators
- UTM-based affiliate attribution
- Unified creator earnings dashboard
- Automated payouts with hold period logic
- Community features via third-party API
- Course and subscription builder

### Out (v1)
- Native video hosting
- In-app content creation tools
- Direct brand-creator messaging
- Multi-touch attribution across creators

## Assumptions
- Creators have existing social media presence at signup
- Brands have product catalogs ready to upload
- Payment gateway handles regulatory compliance

## Risks
| Risk | Mitigation |
|---|---|
| Creator fraud (fake followers) | Engagement rate checks at onboarding |
| Brand spend with no conversions | Performance-based models only — no flat fees |
| Third-party API dependency (community) | Graceful degradation if API goes down |
| Cold start on AI matching | Manual search available until data is sufficient |
| Payout disputes | Hold period + transaction logs |