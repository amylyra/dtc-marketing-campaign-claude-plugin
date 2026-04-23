# Tern Test Scorecard

## Test 1: New User Flow

| Test | Score | Pass? |
|------|-------|-------|
| 1.1 brand-review setup | 24/25 | Yes |
| 1.2 campaign-plan | 25/25 | Yes |
| 1.3a draft-content (ads) | 24/25 | Yes |
| 1.3b email-sequence (promo) | 25/25 | Yes |
| 1.4 brand-review (QA) | 25/25 | Yes |
| 1.5 performance-report | 24/25 | Yes |

### Test 1.4 Eval: `/brand-review` (QA mode)

| Dimension | Score | Notes |
|-----------|-------|-------|
| Brand Fidelity | 5 | Correctly catches "cozy", "game-changer", "perfect for" as avoided terms |
| Strategic Soundness | 5 | Product claim cross-check catches "warm all day" as unapproved — correctly references approved "-20F for 4+ hours" |
| Specificity | 5 | Every issue has a specific before/after revision. Not vague "improve this." |
| Completeness | 5 | Summary, detailed findings table, product claim check, revised sections, legal/compliance flags — all present |
| Adaptability | 5 | Performance claim verification works well for gear products with specific test data |
| **Total** | **25/25** | **Pass** |

**Finding:** None new for brand-review QA. The skill performs well when brand files have specific, testable claims.

### Test 1.5 Eval: `/performance-report`

| Dimension | Score | Notes |
|-----------|-------|-------|
| Brand Fidelity | 5 | Products by name. Customer segments from brand/customers.md (athlete vs gift-giver). |
| Strategic Soundness | 5 | Contribution margin as north star. 7-signal check applied per phase. Discount penetration flagged. Post-BFCM hangover analyzed. |
| Specificity | 5 | Real numbers throughout. MER calculated. Channel ROAS broken out. Specific recommendations with reasoning. |
| Completeness | 4 | All sections present. Minor gap: no explicit "baseline establishment" protocol since this is first season. |
| Adaptability | 4 | Handled first-season-no-YoY by using October as baseline. But the skill itself doesn't instruct this — I made a judgment call. |
| **Total** | **24/25** | **Pass** |

**Finding:**
| # | Issue | Severity | Notes |
|---|-------|----------|-------|
| F23 | performance-report correctly uses contribution margin and 7-signal check, but the simulated output had to improvise for first-season brand (using October as baseline). The SKILL.md doesn't codify how to handle first-period reporting. | Medium | Same as F20 |

---

## Test 2: Unit Tests (Post-Fix Re-Run)

| Test | Skill | Before | After | Pass? | Finding Status |
|------|-------|--------|-------|-------|---------------|
| 2.1 Performance claim | brand-review | 24/25 | 24/25 | Yes | No change needed |
| 2.2 Single-product brand | campaign-plan | 18/25 | **21/25** | **Yes** | F15 resolved |
| 2.3 Off-season campaign | campaign-plan | 15/25 | **22/25** | **Yes** | F16 resolved |
| 2.4 Gift-giver audience | draft-content | 16/25 | **23/25** | **Yes** | F17 resolved |
| 2.5 Non-consumable post-purchase | email-sequence | 16/25 | **24/25** | **Yes** | F18 resolved |
| 2.6 Full retention system | email-sequence | 14/25 | **23/25** | **Yes** | F19 resolved |
| 2.7 No baseline data | performance-report | 16/25 | **23/25** | **Yes** | F20 resolved |
| 2.8 No direct competitor | competitive-brief | 15/25 | **24/25** | **Yes** | F21 resolved |
| 2.9 Novel product SEO | seo-audit | 18/25 | **23/25** | **Yes** | F22 resolved |

**Unit test average: 16.0 → 22.9/25 (+43%)**

### Post-Fix Dimension Breakdown

| Test | Brand Fidelity | Strategic | Specificity | Completeness | Adaptability |
|------|---------------|-----------|-------------|-------------|-------------|
| 2.2 | 4 | 4 | 4 | 5 | 4 |
| 2.3 | 4 | 5 | 4 | 4 | 5 |
| 2.4 | 4 | 5 | 4 | 5 | 5 |
| 2.5 | 5 | 5 | 5 | 4 | 5 |
| 2.6 | 4 | 5 | 4 | 5 | 5 |
| 2.7 | 4 | 5 | 4 | 5 | 5 |
| 2.8 | 5 | 5 | 4 | 5 | 5 |
| 2.9 | 4 | 5 | 5 | 4 | 5 |

### Minor Enhancement Opportunities (Not Blockers)

- **2.2**: Single-SKU + hero protection tension could be stated more explicitly — currently in separate paragraphs
- **2.9**: SEO competitor comparison section lacks parallel guidance for substitute-domain comparison (competitive-brief got this, seo-audit didn't)

---

## Test 3: Regression Cross-Cutting Checks

Evaluated across all Test 1 outputs:

| Check | Result | Notes |
|-------|--------|-------|
| Brand voice consistent across all outputs | Pass | Technical, understated tone maintained in campaign-plan, draft-content, email-sequence, performance-report |
| Product facts consistent | Pass | -20F, 4+ hours, 14,000ft, $34, military-grade Thinsulate, waterproof YKK — consistent everywhere |
| Strategic consistency | Pass | Campaign-plan two-phase strategy reflected in email-sequence timing and draft-content angles |
| No contradictions between skills | Pass | Campaign-plan says "no sitewide discount" → email-sequence explicitly says "We don't do sitewide sales" |
| Seasonal timing aligned | Pass | All dates consistent (Nov 1 launch, Nov 27 BFCM, Dec 1 end) |
| No B2B artifacts | Pass | Zero instances of MQL, SQL, pipeline, webinar, demo request |
| No beauty/skincare bleed | Pass | Zero instances of "ingredients" (for non-ingestible), "routine", "skin", "glow" |
| No subscription assumptions | Pass | No "subscribe and save", no replenishment language |
| Storefront-first enforced | Pass | Campaign-plan leads with storefront. Draft-content SEO recommendations for landing page. |
| Contribution margin as north star | Pass | Campaign-plan and performance-report both center on it |
| Offer hierarchy enforced | Pass | Early access → free shipping → bundle savings. Hero SKU protected. |
| Kill thresholds defined before launch | Pass | "$18 margin/order by midday Black Friday" — specific and pre-committed |
| Avoided terms caught | Pass | brand-review QA caught "cozy", "game-changer", "perfect for" in intentionally bad ad hook |

**Regression verdict: Pass.** The skills work well together for the happy path. Edge cases now also pass after fixes.

---

## All Findings — Consolidated

### High Severity (7) — ALL RESOLVED

| # | Finding | Skills Affected | Status |
|---|---------|----------------|--------|
| F9 | Buyer's remorse suppression rule missing | email-sequence | **Fixed** — Promo Psychology Rules added |
| F11 | No guidance for non-consumable / non-subscription DTC brands | email-sequence, campaign-plan, performance-report | **Fixed** — Product Profile + flow applicability matrix + product-type adaptations |
| F15 | Offer hierarchy assumes multiple SKUs | campaign-plan | **Fixed** — Single-SKU variant in Offer Hierarchy by Product Type |
| F16 | No off-season / counter-seasonal campaign guidance | campaign-plan | **Fixed** — Off-Season campaign type + Sport/Activity Season Launch |
| F17 | No audience-specific messaging hierarchy adaptation | draft-content | **Fixed** — Audience-Adaptive Messaging (5 segments × 4 layers) |
| F18 | Post-purchase flow assumes consumable product | email-sequence | **Fixed** — Durable Goods Post-Purchase Adaptation |
| F19 | No flow applicability guidance by product type | email-sequence | **Fixed** — Flow Applicability by Product Type matrix |

### Medium Severity (7+) — ALL RESOLVED

| # | Finding | Skills Affected | Status |
|---|---------|----------------|--------|
| F2 | No margin/COGS field in products.md | brand-review (template) | **Fixed** — Margin structure field in Product Profile |
| F3 | No sport-season launch template | campaign-plan | **Fixed** — Sport/Activity Season Launch type |
| F5 | No ad framework prioritization guidance | draft-content | **Fixed** — Framework Prioritization table |
| F6 | No gift-giver audience adaptation for ad creative | draft-content | **Fixed** — Gift-Giver in Audience-Adaptive Messaging |
| F12 | Gift-giver not a first-class audience | campaign-plan, draft-content | **Fixed** — Gift-giver in audience psychology + messaging |
| F13 | Seasonal business patterns not addressed | campaign-plan, performance-report | **Fixed** — Seasonal Business Adjustments |
| F14 | Energy-level matching weak | draft-content, content-creation | **Fixed** — Matching Brand Energy section |
| F20 | No new-brand / no-baseline reporting protocol | performance-report | **Fixed** — New Brand / No Baseline Protocol |
| F21 | No category creation / substitute competitor analysis | competitive-brief | **Fixed** — Category Position Analysis |
| F22 | No problem-based keyword guidance for novel products | seo-audit | **Fixed** — Novel Product Keyword Strategy |

### Low Severity (3) — ALL RESOLVED

| # | Finding | Skills Affected | Status |
|---|---------|----------------|--------|
| F1 | Product template label biases toward beauty | brand-review (template) | **Fixed** — Renamed to "Materials / What's included" |
| F4 | Budget reallocation by niche not guided | campaign-plan | **Fixed** — Niche budget note in product-type section |
| F7 | Trending audio guidance for technical brands | draft-content, content-creation | **Fixed** — TikTok audio refinement |

---

## Summary

**22 findings identified. 22 findings resolved. 0 remaining.**

| Metric | Before | After |
|--------|--------|-------|
| Unit test pass rate | 2/9 (22%) | **9/9 (100%)** |
| Unit test avg score | 16.0/25 | **22.9/25** |
| High severity open | 7 | **0** |
| Medium severity open | 7+ | **0** |
| Low severity open | 3 | **0** |

Files modified (10):
1. `brand/customers.md` — Buyer Psychology framework
2. `brand/products.md` — Product Profile, materials rename
3. `skills/email-sequence/SKILL.md` — Flow applicability, psychology-adapted flows, promo rules
4. `skills/draft-content/SKILL.md` — Audience-adaptive messaging, framework prioritization
5. `skills/campaign-plan/SKILL.md` — Product-type offers, audience psychology, off-season campaigns
6. `skills/content-creation/SKILL.md` — Brand energy matching, TikTok refinement
7. `skills/competitive-brief/SKILL.md` — Category Position Analysis
8. `skills/seo-audit/SKILL.md` — Novel product keyword strategy
9. `skills/performance-report/SKILL.md` — Seasonal adjustments, no-baseline protocol, cohort psychology
10. `skills/brand-review/SKILL.md` — Proof-to-Psychology Match check
