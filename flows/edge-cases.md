# Edge Cases

## Brand-Side

### Campaign budget exhausted mid-run
- Auto-pause campaign immediately
- Notify brand via dashboard alert
- Allow quick wallet recharge to resume
- Affiliate links remain valid but inactive until resumed

### Creator goes inactive post-acceptance
- Flag if no link activity after X days
- Notify brand with option to reassign campaign slot
- Creator account flagged for review

### Fraudulent click patterns detected
- Hold payout automatically
- Alert brand on dashboard
- Flag creator account for manual review
- Do not auto-terminate — allow appeal window

### Brand uploads duplicate products in CMS
- Detect duplicates on bulk upload via SKU matching
- Surface warning before confirming upload
- Allow override if intentional (e.g. regional variants)

---

## Creator-Side

### Affiliate link shared outside approved channels
- UTM tracking still captures source data
- Source flagged as unrecognized in analytics
- Brand notified for visibility — not auto-penalized in v1

### Withdrawal requested before hold period ends
- Show pending status with exact unlock date
- No manual override in v1
- Clear messaging on why hold exists to reduce support load

### Storefront product goes out of stock on brand side
- Auto-hide product from creator storefront
- Notify creator with reason
- Product reinstated automatically when restocked

### Creator deletes social account post-verification
- Account remains active on platform
- Flag for re-verification at next login
- Campaign links remain functional — not tied to social auth

---

## Platform-Level

### Third-party community API downtime
- Graceful degradation — community tab shows maintenance state
- Core campaign and earnings features unaffected
- No cascading failure to payout or analytics systems

### Payment gateway failure during payout
- Queue payout for retry with exponential backoff
- Notify creator of delay with estimated resolution
- Log transaction for manual review if retry fails

### AI matching returns no results
- Fall back to manual search and filter automatically
- No error state shown to brand — seamless fallback
- Log empty result queries to improve model training data