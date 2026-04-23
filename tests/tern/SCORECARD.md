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

**Unit test average (v2.1): 16.0 → 22.9/25 (+43%)**

### v2.2 Stepped Flow Tests (campaign-plan)

| Test | Skill | Score | Pass? | Notes |
|------|-------|-------|-------|-------|
| 2.2 Single-product (re-run) | campaign-plan | **24/25** | Yes | Offer hierarchy compressed, site assets adapted (Nav Merch/Inline Promo N/A), multi-unit attach KPI |
| 2.3 Off-season (re-run) | campaign-plan | **24/25** | Yes | Lighter output all steps — Step 2 minimal assets, Step 3 email+organic only, Step 4 inventory-cleared metrics |
| 2.10 Site asset tiering (NEW) | campaign-plan | **25/25** | Yes | All 10 assets considered, tiers adapted for campaign, brand-specific copy direction |
| 2.11 Channel tiering (NEW) | campaign-plan | **24/25** | Yes | Email/Meta tiered, SMS/Google essentials-only, scannable output |
| 2.12 Step gates + flow (NEW) | campaign-plan | **24/25** | Yes | All gates correct, no bleed-forward, budget deferred to Step 3 |

**Stepped flow test average: 24.2/25**

### Post-Fix Dimension Breakdown (v2.1)

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

### v2.2 Dimension Breakdown

| Test | Brand Fidelity | Strategic | Specificity | Completeness | Adaptability |
|------|---------------|-----------|-------------|-------------|-------------|
| 2.2 (re-run) | 5 | 5 | 4 | 5 | 5 |
| 2.3 (re-run) | 5 | 5 | 4 | 5 | 5 |
| 2.10 | 5 | 5 | 5 | 5 | 5 |
| 2.11 | 5 | 5 | 4 | 5 | 5 |
| 2.12 | 5 | 5 | 4 | 5 | 5 |

### Minor Enhancement Opportunities (Not Blockers)

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

## Test 4: End-to-End Regression — Mother's Day Campaign

Full campaign traced through all 5 skill phases for Tern (durable goods, gift-giver audience, seasonal campaign).

**Scenario**: Mother's Day 2026 campaign targeting gift-givers. Budget $5K-7K. Timeline Apr 21–May 10.

### Phase Scores

| Phase | Skill | Score | Pass? |
|-------|-------|-------|-------|
| 4.1 | campaign-plan | 25/25 | Yes |
| 4.2 | draft-content | 25/25 | Yes |
| 4.3 | email-sequence | 25/25 | Yes |
| 4.4 | brand-review (QA) | 25/25 | Yes |
| 4.5 | performance-report | 25/25 | Yes |

### Phase Details

**4.1 campaign-plan** — Gift-giver-focused Mother's Day campaign. Offer hierarchy enforced: free gift wrapping + free shipping + GWP at $100+ (no % discount). Two-phase calendar (awareness Apr 21–May 3, conversion May 4–10). Kill threshold: ROAS < 2.5x by May 1. All 10 campaign-plan sections present. Gift-giver buyer psychology applied to channel allocation (Pinterest, Instagram prioritized over TikTok for gifting intent).

**4.2 draft-content** — 5 ad frameworks with gift-giver audience-adaptive messaging across all 4 layers. UGC Testimonial and "3 Reasons Why" prioritized for gift-givers (matches trust hierarchy: peer recommendations > expert opinion). Full gift guide with 4 price tiers ($34 single item → $150+ premium bundle) using actual Tern products. Hook variants: 5-10 per framework. No self-purchase language in gift-giver creative.

**4.3 email-sequence** — 7-message promo flow (Apr 24–May 5) with countdown urgency escalation. 7-message gift-giver post-purchase flow with critical adaptation: no product-usage emails sent to the buyer (who doesn't have the product). Post-purchase flow focuses on gift tracking, delivery confirmation, and "did they love it?" follow-up. SMS variants for every email. Durable goods flow applicability enforced (no replenishment, no subscription).

**4.4 brand-review (QA)** — Fed intentionally bad content containing 6 banned terms ("cozy", "game-changer", "perfect for", "best thing ever", "you need this", "obsessed"), sitewide discount violation, subscription language for non-subscription brand, unsubstantiated performance claims, and proof-to-psychology mismatch (data/specs shown to social-proof-driven gift-giver audience). Caught all violations. Provided 5 specific before/after rewrites. Flagged proof-to-psychology mismatch as medium severity.

**4.5 performance-report** — Post-mortem: $28,400 revenue, 18.6% contribution margin ($5,282 CM). 7-signal check: 6 pass, 1 monitor (post-promo hangover TBD — campaign just ended). Seasonal business adjustments applied (Mother's Day as standalone tentpole, no YoY available — used pre-campaign April baseline). Cohort psychology: gift-acquired cohort tracked separately with 90-day reactivation window. Gift-recipient activation plan included.

### Cross-Cutting Regression Checks

| Check | Result | Notes |
|-------|--------|-------|
| Brand voice consistent | Pass | Technical, understated tone across all 5 phases |
| Product facts consistent | Pass | -20F, 4+ hours, 14,000ft, $34 Waterbottle Parka, military-grade Thinsulate — consistent |
| Strategic consistency | Pass | Two-phase calendar in campaign-plan reflected in email timing and content angles |
| No contradictions | Pass | No % discount in campaign-plan → no % discount in email or ad copy |
| Seasonal timing aligned | Pass | All dates consistent (Apr 21 start, May 4 conversion push, May 10 end, May 11 Mother's Day) |
| No B2B artifacts | Pass | Zero B2B language |
| No beauty/skincare bleed | Pass | Zero beauty category language |
| No subscription assumptions | Pass | No subscription language for durable goods brand |
| Storefront-first enforced | Pass | Campaign-plan leads with storefront landing page. Gift guide lives on site. |
| Contribution margin as north star | Pass | Campaign-plan margin target and performance-report CM calculation aligned |
| Offer hierarchy enforced | Pass | Free gift wrapping → free shipping → GWP. No % off. Hero SKU protected. |
| Kill thresholds pre-committed | Pass | ROAS < 2.5x by May 1 → pause paid, shift to email/SMS only |
| Gift-giver psychology applied | Pass | All 5 phases adapted for gift-giver: trust hierarchy, no self-purchase language, gift-recipient tracking |
| Proof-to-psychology match | Pass | brand-review caught mismatch when wrong proof type used for gift-giver audience |
| Durable goods adaptations | Pass | No replenishment, no subscription, cross-sell focus in post-purchase |

**Regression verdict: Pass.** Full end-to-end campaign works across all 5 skill phases with gift-giver audience, durable goods product type, and seasonal campaign type — all edge cases that were failing before v2.1.0 fixes.

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

**22 findings identified. 22 findings resolved. 0 remaining. v2.2 stepped flow: 0 new findings.**

| Metric | v2.0 | v2.1 | v2.2 | v2.3 |
|--------|------|------|------|------|
| Eval dimensions | 5 (/25) | 5 (/25) | 5 (/25) | **6 (/30)** |
| Unit test pass rate | 2/9 (22%) | **9/9 (100%)** | **12/12 (100%)** | — (re-run pending) |
| Unit test avg score | 16.0/25 | **22.9/25** | **24.2/25** (stepped flow) | /30 scale |
| E2E regression (Test 4) | — | **5/5 phases, 25/25 each** | — | — |
| High severity open | 7 | **0** | **0** | **0** |
| Medium severity open | 7+ | **0** | **0** | **0** |
| Low severity open | 3 | **0** | **0** | **0** |

> **Scoring scale change (v2.3):** Added 6th eval dimension — Engagement & Persuasion. Scores are now /30. Historical scores (v2.0–v2.2) remain on original /25 scale. New tests and re-runs use /30.

### v2.4 Changes (Connected Pipeline)

All 8 skills wired into a connected pipeline with shared context:
1. **Research saves** — `/competitive-brief` and `/seo-audit` save findings to `research/` directory
2. **Campaign brief saves** — `/campaign-plan` saves locked strategy + creative direction to `campaigns/` directory
3. **Auto-loading** — `/campaign-plan` loads research for richer theme options. `/draft-content` loads campaign brief + research for concept brainstorming and keyword targeting. `/email-sequence` loads brief for arc-aware sends. `/brand-review` loads brief for campaign alignment QA. `/performance-report` loads brief for actuals vs targets.
4. **Creative direction in Step 3** — each email send and Meta concept gets an angle + arc phase
5. **Smart handoff in Step 4** — lists specific concepts from Step 3 to draft next
6. **3 theme options enriched** — renamed to Brand Story / Sharp Edge / Pattern Interrupt, each with sample hooks, "why this works", narrative arc, competitive context
7. **Orientation opening** — users see the 4-step pipeline + brief handoff before work starts

Files modified: `skills/campaign-plan/SKILL.md`, `skills/draft-content/SKILL.md`, `skills/email-sequence/SKILL.md`, `skills/brand-review/SKILL.md`, `skills/competitive-brief/SKILL.md`, `skills/seo-audit/SKILL.md`, `skills/performance-report/SKILL.md`, `CLAUDE.md`, `README.md`, `tests/EVAL-RUBRIC.md`, `tests/tern/test-1.2-campaign-plan.md`, `tests/tern/test-2-unit-tests.md`

### v2.3 Changes (Content Quality Standards)

1. `skills/draft-content/SKILL.md` — Added Copy Quality Standards section: hook quality criteria, variant diversity rules, competitive distinctiveness (swap test), persuasion signals, self-check before delivery
2. `skills/brand-review/SKILL.md` — Added Engagement & Persuasion Quality review dimension: hook strength, variant diversity, swap test, persuasion structure scoring with severity guide
3. `tests/EVAL-RUBRIC.md` — Added 6th dimension (Engagement & Persuasion), updated scoring to /30, updated per-skill completeness checklists, added hook variant and brand-review engagement quality baselines

### v2.2 Changes (Stepped Campaign Flow)

`skills/campaign-plan/SKILL.md` restructured from single-pass 10-section brief to 4-step conversational flow:
1. **Step 1: Strategy** — campaign theme, audience psychology, offer mechanic, kill threshold
2. **Step 2: Site Creative Assets** — tiered checklist (essential/recommended/only-if-needed), brand-specific copy direction, brand guide/UI kit consultation
3. **Step 3: Channels + Calendar** — email/Meta tiered, SMS/Google essentials-only, milestone timeline table
4. **Step 4: Metrics + Execution** — 3-5 KPIs, risks, condensed checklist

Supporting files updated: `CLAUDE.md`, `README.md`, `tests/EVAL-RUBRIC.md`

### v2.1 Changes (22 Findings Fixed)

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
