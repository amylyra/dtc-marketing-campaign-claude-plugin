# Test 2: Unit Tests — Key Edge Cases

Running the highest-signal edge cases from each skill. Focusing on cases most likely to reveal NEW issues (not just re-confirm what Test 1 found).

---

## 2.1 brand-review: Performance claim without test data

**Input:** Paste ad copy: "The Bottle Parka keeps your water liquid in ANY conditions, guaranteed."
**Expected:** Flag "ANY conditions" as unsubstantiated superlative. Flag "guaranteed" as needing legal backing.

**Simulated output:** Correctly flags both.
- "ANY conditions" → High severity. Approved claim is "-20F for 4+ hours." Superlative without qualification.
- "guaranteed" → High severity. A guarantee implies a warranty or money-back promise. If Tern offers one, state the terms. If not, remove.

**Score:** Brand Fidelity 5, Strategic 5, Specificity 5, Completeness 4, Adaptability 5. **24/25 Pass.**

**Finding:** None new. The skill handles performance claim verification well when products.md has specific approved claims.

---

## 2.2 campaign-plan: Single-product brand

**Input:** "/campaign-plan BFCM" — but Tern only has The Bottle Parka, no other SKUs.
**Expected:** Adapt. No bundle offers. No offer hierarchy around secondary SKUs. Focus on volume, gift sets, threshold offers.

**Simulated assessment:**
- Offer hierarchy collapses: can't use "% off secondary SKUs" or "bundles" — there's only one product.
- Options become: early access → free shipping → GWP (add a branded sticker/carabiner at $X threshold) → modest % off on multi-unit (buy 2+ Bottle Parkas, save $5 each for gift-giving) → sitewide % off (last resort, meaning % off the one product).
- Hero SKU protection is THE product — discounting it at all is riskier.
- Gift-giver angle: "Buy one for you, one for your ski buddy" — multi-unit play.

**Score:** Brand Fidelity 4, Strategic 4, Specificity 3, Completeness 4, Adaptability 3. **18/25 — Partial pass.**

**Finding:**
| # | Issue | Severity | Notes |
|---|-------|----------|-------|
| F15 | campaign-plan SKILL.md offer hierarchy assumes multiple SKUs. Single-product brands break the hierarchy at steps 4-6 (GWP, bundles, % off secondary). No guidance for single-SKU offer strategy. | High | Offer hierarchy needs a single-product variant |

---

## 2.3 campaign-plan: Off-season campaign

**Input:** "/campaign-plan summer sale for Tern winter gear"
**Expected:** Flag seasonality mismatch. Suggest alternatives: clearance, early-bird next season, or brand-building.

**Simulated assessment:**
- Skill correctly identifies the campaign goal but does NOT have explicit guidance for off-season campaigns.
- A good output would: (1) flag that demand is structurally low in summer, (2) suggest clearance positioning for old colorways/inventory, (3) suggest early-bird pre-season pricing for next season, (4) recommend brand-building content (summer training, off-season gear prep) over promo.
- The SKILL.md has no "off-season" campaign type or seasonal mismatch detection.

**Score:** Brand Fidelity 4, Strategic 3, Specificity 3, Completeness 3, Adaptability 2. **15/25 — Fail.**

**Finding:**
| # | Issue | Severity | Notes |
|---|-------|----------|-------|
| F16 | campaign-plan has no guidance for off-season campaigns or seasonal mismatch detection. A winter gear brand running a summer sale needs different strategy: clearance, pre-season, or brand-building — not the standard promo framework. | High | Add off-season/counter-seasonal campaign type |

---

## 2.4 draft-content: Gift-giver audience vs self-purchase

**Input:** "/draft-content ad creative for The Bottle Parka — targeting gift-givers, not athletes"
**Expected:** Completely different hooks. Pain point is "impossible to shop for" not "frozen water bottle." Language shifts from performance specs to gift appeal.

**Simulated assessment:**
- Hooks should be: "For the person who already has every jacket, every boot, every piece of gear — except this."
- Gift-giver doesn't care about Thinsulate or -20F. They care about: (1) will this person love it? (2) is it unique? (3) is it the right price?
- The SKILL.md has no explicit "audience adaptation" guidance. It says to use `brand/customers.md` but doesn't instruct how to shift the entire messaging framework for a non-primary audience.

**Score:** Brand Fidelity 4, Strategic 3, Specificity 3, Completeness 3, Adaptability 3. **16/25 — Fail.**

**Finding:**
| # | Issue | Severity | Notes |
|---|-------|----------|-------|
| F17 | draft-content SKILL.md doesn't instruct how to adapt messaging hierarchy for different audience segments. Gift-giver "why should I care?" is completely different from athlete "why should I care?" — but the skill treats audience as an input field, not a framework modifier. | High | Add audience-specific messaging hierarchy guidance |

---

## 2.5 email-sequence: Non-consumable post-purchase flow

**Input:** "/email-sequence post-purchase flow for Tern"
**Expected:** Adapt for durable goods. No replenishment. Focus on care/use tips, UGC/review request, cross-sell other products, referral.

**Simulated assessment:**
The template (#3 in SKILL.md) has 7 touchpoints:
1. Order confirmation + cross-sell ✓
2. Shipping notification + brand story ✓
3. Delivery confirmation + care tips ✓ (but template says "care/usage tips" — need adaptation for gear vs beauty)
4. Review request ✓
5. **Replenishment reminder** ✗ — N/A for durable goods
6. **Second purchase incentive** — needs rethinking. For Tern, this is "you bought the Bottle Parka, meet the Phone Parka" not "buy another Bottle Parka"
7. Cross-sell ✓ but needs to be "other Tern products" not "refill" or "restock"

**Score:** Brand Fidelity 4, Strategic 3, Specificity 3, Completeness 3, Adaptability 3. **16/25 — Fail.**

**Finding:**
| # | Issue | Severity | Notes |
|---|-------|----------|-------|
| F18 | Post-purchase flow template steps 5-6 assume consumable/replenishment product. For durable goods: step 5 should be "new product launch notification" or "seasonal check-in" and step 6 should be "cross-sell within product line" not "replenishment incentive." | High | Add conditional paths in post-purchase template for consumable vs durable |

---

## 2.6 email-sequence: "Build my entire retention system"

**Input:** "/email-sequence — build all the flows for Tern, we're starting from scratch"
**Expected:** Prioritize. Skip replenishment. Adapt order for a non-consumable seasonal brand.

**Simulated assessment:**
- SKILL.md priority order: welcome → abandoned cart → post-purchase → browse abandonment → win-back...
- For Tern: welcome ✓, abandoned cart ✓, post-purchase ✓ (but needs durable goods adaptation)
- **Replenishment (#9): should be skipped entirely** — product lasts years
- **Win-back (#5): needs seasonal adaptation** — lapsed Tern customer isn't someone who forgot to reorder. They may have bought one product and not needed another until a new product launched or a new season started.
- **Birthday (#12): low priority** — Tern isn't a lifestyle/relationship brand. Birthday emails feel off-brand for "ski patrol veteran" voice.
- The SKILL.md doesn't guide which flows to SKIP based on product type, only which to prioritize.

**Score:** Brand Fidelity 3, Strategic 3, Specificity 3, Completeness 3, Adaptability 2. **14/25 — Fail.**

**Finding:**
| # | Issue | Severity | Notes |
|---|-------|----------|-------|
| F19 | email-sequence SKILL.md lists 12 flow types in priority order but has no guidance on which flows to SKIP for certain product types. Replenishment makes no sense for durable goods. Birthday feels off-brand for performance gear. The skill should include a "flow applicability" matrix by product type. | High | Add flow applicability guidance: which flows apply to consumable vs durable vs seasonal products |

---

## 2.7 performance-report: New brand with no baseline

**Input:** "/performance-report monthly summary" — Tern's first month of sales, no prior data
**Expected:** Use industry benchmarks instead of YoY. Establish this period as baseline.

**Simulated assessment:**
- The SKILL.md says "Comparison baseline — prior period, same period last year, or counterfactual" but has no guidance for when NONE of these exist.
- A new brand has no prior period, no YoY, and no counterfactual (they weren't running before).
- The skill should: (1) benchmark against DTC industry averages, (2) benchmark against category-specific data if available, (3) explicitly state "establishing baseline" for future comparison, (4) focus on trend direction rather than absolute comparisons.

**Score:** Brand Fidelity 4, Strategic 3, Specificity 3, Completeness 3, Adaptability 3. **16/25 — Fail.**

**Finding:**
| # | Issue | Severity | Notes |
|---|-------|----------|-------|
| F20 | performance-report SKILL.md has no guidance for brands with no baseline data (first period, new brand). Should include: industry benchmark reference, baseline establishment protocol, and focus on trend-over-time rather than period-over-period comparison. | Medium | Add "New Brand / No Baseline" section to performance-report |

---

## 2.8 competitive-brief: No direct competitor

**Input:** "/competitive-brief — nobody else makes goggle warmers, who do we compare against?"
**Expected:** Identify adjacent competitors and substitute solutions. Frame as category creation opportunity.

**Simulated assessment:**
- The SKILL.md says to research competitors through DTC sources, but doesn't have guidance for when there IS no direct competitor.
- Adjacent competitors: anti-fog sprays, anti-fog wipes, double-lens goggles (built-in anti-fog), heated goggles (Smith I/O MAG, etc.)
- The analysis should frame this as: "You're creating a category. Your competition is the current workaround, not another brand."
- The SKILL.md doesn't distinguish between direct competitors and substitute solutions.

**Score:** Brand Fidelity 4, Strategic 3, Specificity 3, Completeness 3, Adaptability 2. **15/25 — Fail.**

**Finding:**
| # | Issue | Severity | Notes |
|---|-------|----------|-------|
| F21 | competitive-brief SKILL.md assumes competitors are other brands in the same category. No guidance for category creation (no direct competitor) or substitute/workaround analysis. Should include: "If no direct competitor exists, analyze substitute solutions and workarounds the customer currently uses." | Medium | Add category creation / substitute analysis guidance |

---

## 2.9 seo-audit: Niche product with no search volume

**Input:** "/seo-audit for Tern — 'bottle parka' has essentially zero search volume"
**Expected:** Pivot to problem-based queries. "Keep water from freezing hiking" instead of product-name queries.

**Simulated assessment:**
- The SKILL.md has "DTC-Specific Keyword Patterns" including "Best [product type] for [need]" which helps
- But it doesn't explicitly address what to do when your PRODUCT NAME isn't a search term
- For Tern: target "insulated water bottle sleeve", "keep water from freezing while hiking", "winter hydration gear", "water bottle freezing skiing" — all problem-based
- The skill should guide: "If your product name is novel or category-creating, target the PROBLEM your product solves, not the product name"

**Score:** Brand Fidelity 4, Strategic 4, Specificity 3, Completeness 4, Adaptability 3. **18/25 — Partial pass.**

**Finding:**
| # | Issue | Severity | Notes |
|---|-------|----------|-------|
| F22 | seo-audit SKILL.md doesn't address category-creating products with no established search terms. Should guide: "If the product name has no search volume, target the problem it solves. Map customer pain point language to keyword opportunities." | Medium | Add problem-based keyword guidance for novel products |

---

## Unit Test Summary

| Test | Skill | Score | Pass? | Key Finding |
|------|-------|-------|-------|-------------|
| 2.1 Performance claim | brand-review | 24/25 | Yes | None new |
| 2.2 Single-product brand | campaign-plan | 18/25 | Partial | F15: Offer hierarchy needs single-SKU variant |
| 2.3 Off-season campaign | campaign-plan | 15/25 | Fail | F16: No off-season campaign guidance |
| 2.4 Gift-giver audience | draft-content | 16/25 | Fail | F17: No audience-specific messaging adaptation |
| 2.5 Non-consumable post-purchase | email-sequence | 16/25 | Fail | F18: Post-purchase template assumes consumable |
| 2.6 Full retention system | email-sequence | 14/25 | Fail | F19: No flow skip/applicability guidance |
| 2.7 No baseline data | performance-report | 16/25 | Fail | F20: No new-brand baseline protocol |
| 2.8 No direct competitor | competitive-brief | 15/25 | Fail | F21: No category creation analysis |
| 2.9 Novel product SEO | seo-audit | 18/25 | Partial | F22: No problem-based keyword guidance for novel products |
