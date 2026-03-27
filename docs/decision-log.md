# Decision Log

## 1. Performance-based campaign types over flat fees
**Options considered:**
- Flat fee per post
- Performance-based (CPC, CPV, CPP, CPCall)

**Decision:** Performance-based models only

**Why:** Flat fees gave brands zero accountability.
Performance models tied spend directly to measurable outcomes.

**Tradeoff:** More complex tracking and payout logic.
Worth it because it was the core value proposition for brands.

---

## 2. Storefront as a creator-owned asset
**Options considered:**
- Creators only share affiliate links
- Creators get a branded storefront page

**Decision:** Full storefront builder with templates

**Why:** Reduced creator dependency on brand deals.
Gave creators an owned surface to drive sales from social bio.
Increased platform stickiness for creators.

**Tradeoff:** Added significant scope to v1.
Prioritized it because creator retention depended on it.

---

## 3. Third-party community integration vs in-house build
**Options considered:**
- Build community features from scratch
- Integrate via third-party API

**Decision:** Third-party API integration

**Why:** Community is a deep product surface.
In-house build would have delayed launch by months.

**Tradeoff:** Platform dependency and limited customization.
Acceptable for v1 — revisit in v2 if usage justifies it.

---

## 4. Payout hold period
**Options considered:**
- Instant payouts
- 30-day hold period

**Decision:** 30-day hold before creator withdrawals

**Why:** Reduce chargeback and fraud risk.
Brands needed a window to flag invalid conversions.

**Tradeoff:** Friction for creators.
Mitigated by showing pending earnings clearly in dashboard
so creators always know what's coming.

---

## 5. Form builder tied to products not campaigns
**Options considered:**
- Forms created per campaign
- Forms created per product, reusable across campaigns

**Decision:** Forms tied to Product IDs

**Why:** Same product appears in multiple campaigns.
Reusable forms reduced brand-side setup overhead significantly.

**Tradeoff:** Slightly more complex data model.
Worth it for the reduction in repetitive brand-side work.

---

## 6. AI matching with manual fallback
**Options considered:**
- Purely manual search and filter
- AI-only recommendation
- AI with manual fallback

**Decision:** AI-powered with manual search as fallback

**Why:** Cold start problem — AI needs sufficient data
to make reliable recommendations.
Manual search ensures brands can still find creators
on day one before the model is trained sufficiently.

**Tradeoff:** More UI surface to maintain.
Acceptable until AI recommendations reach reliable accuracy.