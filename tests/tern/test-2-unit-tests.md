# Test 2: Unit Tests — Key Edge Cases

Running the highest-signal edge cases from each skill. Focusing on cases most likely to reveal NEW issues (not just re-confirm what Test 1 found).

---

## 2.1 brand-review: Performance claim without test data

**Input:** Paste ad copy: "The Bottle Parka keeps your water liquid in ANY conditions, guaranteed."
**Expected:** Flag "ANY conditions" as unsubstantiated superlative. Flag "guaranteed" as needing legal backing.

**Simulated output:** Correctly flags both.
- "ANY conditions" → High severity. Approved claim is "-20F for 4+ hours." Superlative without qualification.
- "guaranteed" → High severity. A guarantee implies a warranty or money-back promise. If Tern offers one, state the terms. If not, remove.

**Score:** Brand Fidelity 5, Strategic 5, Specificity 5, Completeness 4, Engagement 5, Adaptability 5. **29/30 Pass.**

**Finding:** None new. The skill handles performance claim verification well when products.md has specific approved claims.

---

## 2.2 campaign-plan: Single-product brand (4-step flow)

**Input:** "/campaign-plan BFCM" — but Tern only has The Bottle Parka, no other SKUs.
**Expected:** Adapt across all 4 steps. Offer hierarchy collapses (no bundles, no secondary SKUs). Site assets still tiered correctly. Channel plan still structured.

**What to evaluate in stepped flow:**
- Step 1: Offer hierarchy uses single-SKU variant (early access → free shipping → multi-unit discount → modest % off). Hero SKU protection = THE product.
- Step 2: Site creative assets still tiered. HP Banner, Collection Banner, Announcement Bar essential. But collection page is simpler (1 product + multi-unit option).
- Step 3: Channel plan adapts — fewer ad creative variants needed (1 product, fewer angles). Email still tiered.
- Step 4: Metrics include multi-unit attach rate as a KPI.

**Pre-fix score:** 20/30 — Partial pass.
**Post-fix score (v2.1):** 25/30 — Pass.
**Evaluation criteria for v2.2 (stepped flow):** Must also produce tiered site assets for a single-product campaign and gate correctly between steps.

**Finding (v2.1):** F15 resolved — Single-SKU variant in Offer Hierarchy by Product Type.

---

## 2.3 campaign-plan: Off-season campaign (4-step flow)

**Input:** "/campaign-plan summer sale for Tern winter gear"
**Expected:** Flag seasonality mismatch at Step 1. Strategy should be clearance, early-bird, or brand-building — not standard promo. Step 2 site assets should be minimal (no full campaign treatment for off-season).

**What to evaluate in stepped flow:**
- Step 1: Flags demand is structurally low. Proposes off-season strategy (clearance, pre-season, or brand-building). Theme reflects reality, not forced optimism.
- Step 2: Site assets are lighter — maybe just announcement bar + collection page for clearance items. Not full HP Banner treatment.
- Step 3: Channel plan is minimal — email to existing list, organic social for brand-building. Minimal paid spend.
- Step 4: Metrics focus on inventory cleared or email list growth, not revenue targets.

**Pre-fix score:** 17/30 — Fail.
**Post-fix score (v2.1):** 26/30 — Pass.
**Evaluation criteria for v2.2 (stepped flow):** Off-season should produce a deliberately lighter Step 2 (fewer essential site assets) and Step 3 (minimal channels). The stepped flow should adapt its scope, not just apply standard tiers to a non-standard campaign.

**Finding (v2.1):** F16 resolved — Off-Season campaign type + Sport/Activity Season Launch.

---

## 2.4 draft-content: Gift-giver audience vs self-purchase

**Input:** "/draft-content ad creative for The Bottle Parka — targeting gift-givers, not athletes"
**Expected:** Completely different hooks. Pain point is "impossible to shop for" not "frozen water bottle." Language shifts from performance specs to gift appeal.

**Simulated assessment:**
- Hooks should be: "For the person who already has every jacket, every boot, every piece of gear — except this."
- Gift-giver doesn't care about Thinsulate or -20F. They care about: (1) will this person love it? (2) is it unique? (3) is it the right price?
- The SKILL.md has no explicit "audience adaptation" guidance. It says to use `brand/customers.md` but doesn't instruct how to shift the entire messaging framework for a non-primary audience.

**Score:** Brand Fidelity 4, Strategic 3, Specificity 3, Completeness 3, Engagement 3, Adaptability 3. **19/30 — Fail.**

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

**Score:** Brand Fidelity 4, Strategic 3, Specificity 3, Completeness 3, Engagement 3, Adaptability 3. **19/30 — Fail.**

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

**Score:** Brand Fidelity 3, Strategic 3, Specificity 3, Completeness 3, Engagement 2, Adaptability 2. **16/30 — Fail.**

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

**Score:** Brand Fidelity 4, Strategic 3, Specificity 3, Completeness 3, Engagement 3, Adaptability 3. **19/30 — Fail.**

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

**Score:** Brand Fidelity 4, Strategic 3, Specificity 3, Completeness 3, Engagement 3, Adaptability 2. **18/30 — Fail.**

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

**Score:** Brand Fidelity 4, Strategic 4, Specificity 3, Completeness 4, Engagement 3, Adaptability 3. **21/30 — Partial pass.**

**Finding:**
| # | Issue | Severity | Notes |
|---|-------|----------|-------|
| F22 | seo-audit SKILL.md doesn't address category-creating products with no established search terms. Should guide: "If the product name has no search volume, target the problem it solves. Map customer pain point language to keyword opportunities." | Medium | Add problem-based keyword guidance for novel products |

---

## 2.10 campaign-plan: Site creative asset tiering (NEW — v2.2)

**Input:** "/campaign-plan Mother's Day campaign for Tern, targeting gift-givers"
**Expected:** Step 2 produces tiered site creative assets with copy direction specific to gift-giver campaign story. Essential tier includes HP Banner, Collection Banner, Announcement Bar. Assets like Cart Messaging move up to essential if there's a threshold offer (e.g., free shipping at $60).

**What to evaluate:**
- All 10 assets from the Site Creative Asset Checklist are considered
- Tiers adapted for THIS campaign (not just default tiers)
- Copy direction is specific: "For the mom who handles -20°F..." not "promotional messaging"
- Materials question asked at START of Step 2, not during Step 1
- Brand guide/UI kit consulted (brand/voice.md referenced for tone)
- Gate asks user to confirm/trim, not construct from scratch

---

## 2.11 campaign-plan: Channel tiering (NEW — v2.2)

**Input:** "/campaign-plan BFCM for Tern, budget $15K"
**Expected:** Step 3 tiers email and Meta (essential/recommended/optional) but keeps SMS and Google essentials-only. Output is concise — no walls of text.

**What to evaluate:**
- Email: Announcement + Last chance = essential. VIP early access = recommended. Rest = optional.
- Meta: 2-3 concepts + retargeting = essential. Hook variants + UGC = recommended. Awareness = optional.
- SMS: 2 sends max. No tiering, no fluff.
- Google: Shopping feed + branded search. That's it.
- Campaign timeline is a date/milestone table, not a verbose week-by-week narrative
- Budget is one table with no narrative padding
- Total output for Step 3 is scannable in under 2 minutes

---

## 2.12 campaign-plan: Step gates and flow (NEW — v2.2)

**Input:** "/campaign-plan product launch for Tern Phone Parka"
**Expected:** 4 steps with explicit gates. User is asked to confirm strategy before site assets are produced. Materials question appears at Step 2 opening, not earlier. Each gate asks a specific question, not a generic "shall I continue?"

**What to evaluate:**
- Opening orientation present (4-step pipeline in 3-4 lines)
- Step 1A: 3 theme options (Brand Story, Sharp Edge, Pattern Interrupt) — each has theme line, sample hooks, "why this works", narrative arc, competitive context
- Step 1A gate: "Which direction resonates?" (not "shall I continue?")
- Step 1B: locked strategy in table format after user picks/iterates
- Step 1B gate: "Strategy locked. Ready for site assets?"
- Step 2 opening: "What do you already have?" (materials question)
- Step 2 gate: "Here's the prioritized asset list. Anything to add, remove, or change?"
- Step 3 gate: "Channel plan and calendar look right?"
- Step 4 ends with: "What do you want me to draft first?" (not a gate — final output)
- No content from later steps bleeds into earlier steps
- Budget is NOT asked in Step 1 (deferred to Step 3)

---

## 2.13 draft-content: Hook quality + variant diversity (NEW — v2.3)

**Input:** "/draft-content ad creative for The Bottle Parka — targeting backcountry skiers"
**Expected:** 5 ad frameworks, each with 5-10 hook variants. Hooks must pass pattern interrupt, specificity, and swap tests. Variants must use genuinely different angles (min 4 distinct angles per 5+ set).

**What to evaluate:**
- Hooks use specific scenarios, numbers, or sensory details — not generic benefit statements
- No hook starts with brand name or "Introducing..."
- Variant set has 4+ distinct angle categories (pain point, scenario, social proof, contrarian, curiosity gap, direct benefit, comparison, identity)
- Swap test: hooks reference Tern-specific proof (-20F, 14,000ft, military-grade Thinsulate, $34)
- Tension before resolution: problem/gap appears before product in body copy
- CTA is specific (product name, price) not vague ("Shop now")
- Self-check checklist passed before delivery (no draft caveats like "you might want to strengthen...")

**Score threshold:** Engagement & Persuasion must be 4+ for this test to pass. This is the primary dimension being validated.

---

## 2.14 brand-review: Engagement quality assessment (NEW — v2.3)

**Input:** "/brand-review" — review the following ad copy:
> "Introducing the Bottle Parka — our newest product for outdoor enthusiasts! Keep your drinks cold (or hot) with our innovative insulation technology. Perfect for hiking, skiing, and more. Shop now and experience the difference!"

**Expected:** brand-review should flag engagement failures in ADDITION to voice/claim issues:
- Hook starts with "Introducing" and brand name (pattern interrupt fail)
- "outdoor enthusiasts" is generic (no specificity)
- "Keep your drinks cold (or hot)" — swap test fail, any insulated product brand could say this
- "innovative insulation technology" — no proof, no specifics, no Tern-ownable language
- "Perfect for hiking, skiing, and more" — generic list, "perfect for" is an avoided term
- "Shop now and experience the difference" — vague CTA, no product name, no price
- Summary should include engagement assessment line: "Engagement: Weak — [reason]"

**What to evaluate:**
- Engagement findings appear in the Detailed Findings table alongside voice/claim issues
- Severity assigned correctly (High for generic hooks that fail swap test)
- Before/after revisions IMPROVE engagement, not just fix on-brand issues
- Engagement assessment line present in Summary

---

## Unit Test Summary

| Test | Skill | Score | Pass? | Key Finding |
|------|-------|-------|-------|-------------|
| 2.1 Performance claim | brand-review | 29/30 | Yes | None new |
| 2.2 Single-product brand | campaign-plan | 20/30 | Partial | F15: Offer hierarchy needs single-SKU variant |
| 2.3 Off-season campaign | campaign-plan | 17/30 | Fail | F16: No off-season campaign guidance |
| 2.4 Gift-giver audience | draft-content | 19/30 | Fail | F17: No audience-specific messaging adaptation |
| 2.5 Non-consumable post-purchase | email-sequence | 19/30 | Fail | F18: Post-purchase template assumes consumable |
| 2.6 Full retention system | email-sequence | 16/30 | Fail | F19: No flow skip/applicability guidance |
| 2.7 No baseline data | performance-report | 19/30 | Fail | F20: No new-brand baseline protocol |
| 2.8 No direct competitor | competitive-brief | 18/30 | Fail | F21: No category creation analysis |
| 2.9 Novel product SEO | seo-audit | 21/30 | Partial | F22: No problem-based keyword guidance for novel products |
| 2.10 Site asset tiering | campaign-plan | — | NEW | v2.2: Site creative assets tiered with campaign-specific copy direction |
| 2.11 Channel tiering | campaign-plan | — | NEW | v2.2: Email/Meta tiered, SMS/Google essentials-only, concise output |
| 2.12 Step gates and flow | campaign-plan | — | NEW | v2.2: 4-step gates, deferred inputs, materials question timing |
| 2.13 Hook quality + variant diversity | draft-content | — | NEW | v2.3: Hook pattern interrupt, swap test, angle diversity |
| 2.14 Engagement quality assessment | brand-review | — | NEW | v2.3: Engagement findings in review, severity, engagement summary line |
