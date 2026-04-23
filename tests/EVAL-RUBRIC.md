# Evaluation Rubric

How to score skill output quality — not just "did it run" but "is it good."

## Scoring Framework

Every skill output is scored on 5 dimensions. Each dimension is 1-5. A passing score is 4+ on every dimension. A 3 in any dimension means the output needs revision. A 2 or below means the skill instruction itself likely needs a fix.

| Score | Meaning |
|-------|---------|
| 5 | Ready to use. A DTC operator would ship this with minor tweaks. |
| 4 | Solid foundation. Needs light editing but the thinking is right. |
| 3 | Directionally correct but generic, incomplete, or needs significant rework. |
| 2 | Missed the point. Wrong strategy, wrong tone, or missing critical elements. |
| 1 | Broken. Produced B2B output, ignored brand context, or gave harmful advice. |

---

## 5 Evaluation Dimensions

### 1. Brand Fidelity (Does it sound like Tern?)

Not "did it mention the brand name" — did it actually absorb and reproduce the brand's voice, vocabulary, and worldview?

**Tern-specific checks:**
- Voice is technical and understated, not warm/bubbly/lifestyle
- Uses "field-tested", "expedition-grade", "purpose-built" naturally (not forced)
- Zero instances of "cozy", "cute", "game-changer", "hack"
- Product specs are woven into copy as proof, not listed as features
- Tone matches channel (TikTok = raw field test, not polished brand video; product page = specs-forward)
- The output could NOT be for a skincare brand with the product name swapped out

**Scoring:**
- 5: Reads like it was written by someone who knows Tern's brand deeply. Voice is distinct and consistent.
- 4: Voice is mostly right. One or two moments of generic DTC tone creep in.
- 3: Surface-level brand application. Uses the right product names but the copy could be for any outdoor brand.
- 2: Wrong voice. Sounds like a beauty brand or generic e-commerce. Avoided terms present.
- 1: Ignored brand context entirely.

**Red flags that auto-fail:**
- Any avoided term used unironically
- Beauty/wellness language ("routine", "glow", "ingredients" for non-ingestible products)
- Generic enthusiasm that contradicts understated voice ("OMG you'll LOVE this!")

### 2. Strategic Soundness (Is the advice actually good DTC strategy?)

Does the output reflect the economics-first principles in the plugin, or does it just produce content in the right format?

**Checks:**
- Offer hierarchy enforced: cheaper incentives recommended before deeper discounts
- Hero SKU protection: Bottle Parka ($34) never individually discounted
- Contribution margin referenced as the goal, not revenue or ROAS
- Storefront-first: site readiness flagged before outbound channels
- Kill thresholds defined with specific numbers, not vague
- Seasonal reality: acknowledges Nov-Feb revenue concentration
- No subscription assumptions for a non-subscription brand
- Audience-appropriate offers: different for new vs VIP vs gift-givers

**Scoring:**
- 5: Strategy is tight. An experienced DTC operator would agree with every recommendation. Economics are specific and defensible.
- 4: Strategy is sound. Minor gaps (e.g., kill threshold is vague, or budget allocation is generic).
- 3: Follows the template but doesn't think. Generic strategy that could apply to any brand.
- 2: Bad strategy. Recommends deep discounting hero SKU, ignores margin, or treats revenue as the goal.
- 1: Dangerous advice. Would actively harm the business if followed.

**Red flags that auto-fail:**
- Recommending sitewide % off without challenging it
- Ignoring contribution margin in a performance report
- Launching outbound campaigns before storefront is ready
- Suggesting subscription mechanics for a brand with no subscription

### 3. Specificity & Usefulness (Could you actually use this?)

The difference between a template with blanks filled in and a draft you could actually ship. Generic output is the #1 failure mode for marketing AI.

**Checks:**
- Product references are specific: "The Bottle Parka keeps water liquid to -20F for 4+ hours" not "our product performs in extreme conditions"
- Numbers are present: price points, temperature ratings, time durations, discount percentages, budget allocations
- Ad hooks are varied: 5+ hooks with genuinely different angles (not "Your gear is cold" reworded 5 times)
- Email subject lines are specific: reference the product, the season, or the pain point — not generic "Don't miss out"
- Calendar dates are real: tied to actual launch date and seasonal deadlines
- Competitor analysis cites observable evidence (ad formats, pricing, promo timing) not vague "they have strong brand presence"
- Recommendations are actionable: "Update Bottle Parka PDP with -20F test data and customer review pull quote" not "improve product pages"

**Scoring:**
- 5: Output is 80%+ usable as-is. Specific, concrete, actionable. An operator saves real time.
- 4: Good specificity. Most sections are concrete. A few spots need the operator to fill in details.
- 3: Half template, half substance. The structure is right but the content is generic fill-in-the-blank.
- 2: Mostly template. Product names are inserted but the actual advice/copy is interchangeable.
- 1: Pure template output. No brand, product, or situation specificity.

**Red flags that auto-fail:**
- Placeholder text remaining ("[insert product name]", "[your benefit here]")
- Ad hooks that are just the same idea reworded
- Calendar with no real dates
- Recommendations that start with "Consider..." or "You may want to..." (hedging = not useful)

### 4. Completeness (Did it produce everything the skill promises?)

Check the output against the skill's SKILL.md — every required section should be present and substantive.

**Per-skill checklists:**

#### brand-review setup
- [ ] All 6 sections completed (personality, voice attributes, tone by channel, products, customers, terminology)
- [ ] Each voice attribute has "we are / we are not / sounds like / does NOT sound like"
- [ ] Tone table covers all 8 channels
- [ ] Product entries have all fields (name, price, claims, materials, differentiator, objections, proof)
- [ ] Customer profiles have demographics, motivations, language, objections
- [ ] Terminology has preferred terms, avoided terms, product-specific language

#### brand-review (review mode)
- [ ] Summary with overall assessment
- [ ] Detailed findings table with severity levels
- [ ] Product claim cross-check table
- [ ] Before/after revisions for top 3-5 issues
- [ ] Legal/compliance flags section
- [ ] Channel appropriateness check

#### campaign-plan
- [ ] All 10 sections present (overview, audience, messages, channels, calendar, content pieces, metrics, budget, risks, checklist)
- [ ] Promo economics with margin impact and kill threshold
- [ ] Offer hierarchy rationale
- [ ] 10 pre-launch questions answered
- [ ] Daily check-in metrics defined
- [ ] Post-mortem framework referenced

#### draft-content
- [ ] Correct content type template used
- [ ] Messaging hierarchy present (why care → what is it → why this brand → CTA)
- [ ] Brand voice note included
- [ ] SEO recommendations for web content
- [ ] Platform-specific formatting (ad specs, character limits, aspect ratios)
- [ ] Multiple variants where specified (hooks, subject lines)

#### email-sequence
- [ ] Flow overview table
- [ ] Full message drafts (every email and SMS)
- [ ] Flow diagram with branching
- [ ] Timing and conditional logic
- [ ] SMS compliance section
- [ ] Performance benchmarks
- [ ] A/B test suggestions
- [ ] Suppression rules

#### competitive-brief
- [ ] Executive summary
- [ ] Per-competitor profiles (all subsections)
- [ ] Messaging comparison matrix
- [ ] Content & SEO gap analysis
- [ ] Promo intelligence
- [ ] Opportunities and threats
- [ ] Recommended actions (quick wins + strategic)

#### performance-report
- [ ] Executive summary
- [ ] Core metrics dashboard
- [ ] 7-signal promo health check (for post-mortems)
- [ ] Channel-specific metrics
- [ ] Guardrail check (discount penetration, full-price velocity)
- [ ] Recommendations
- [ ] Next period priorities

**Scoring:**
- 5: Every section present and substantive. Nothing skipped.
- 4: All major sections present. One or two minor subsections light.
- 3: Missing a required section or multiple sections are skeletal.
- 2: Multiple required sections missing. Output is incomplete.
- 1: Severely incomplete. Only produced a fraction of what the skill promises.

### 5. Adaptability (Did it actually handle the edge case?)

The most important eval dimension for unit tests. Did the skill genuinely adapt to the unusual input, or did it just run its default template and ignore the constraint?

**Checks:**
- Non-subscription brand: No replenishment flow suggested, no "subscribe and save" language
- Seasonal business: Acknowledges off-season, doesn't assume year-round marketing
- Hard goods (not beauty): Materials and performance specs, not ingredients and skin types
- Gift-giver persona: Shifts language from self-purchase to gifting when appropriate
- Low search volume niche: Targets problem queries, not product-name queries
- No reviews yet: Uses alternative social proof (field-test data, press, founder credibility)
- Adjacent competitor: Frames Hydro Flask as adjacent (built-in insulation) not direct (same product)
- Budget constraint: Reallocates channel mix, doesn't just scale everything down

**Scoring:**
- 5: Fully adapted. The constraint changed the output meaningfully. You can see the edge case reflected throughout.
- 4: Mostly adapted. Main output reflects the constraint, but a few sections revert to defaults.
- 3: Acknowledged but not adapted. "Note: this brand has no subscription" appears, but the email flow still suggests replenishment.
- 2: Ignored. Output is the same as it would be for a standard DTC beauty brand.
- 1: Contradicted. Output assumes the opposite of what was stated (e.g., suggests subscription for a non-subscription brand).

**Red flags that auto-fail:**
- Replenishment flow suggested for a non-consumable product
- "Subscribe and save" in copy for a brand with no subscription
- Beauty/wellness templates applied to hard goods without adaptation
- Year-round cadence plan for a seasonal business

---

## Eval Process

### For Unit Tests (Test 2)

Each edge case gets a scorecard:

```
Test: [test case name]
Skill: [skill name]
Input: [what was provided]

| Dimension | Score | Notes |
|-----------|-------|-------|
| Brand Fidelity | /5 | |
| Strategic Soundness | /5 | |
| Specificity & Usefulness | /5 | |
| Completeness | /5 | |
| Adaptability | /5 | |

Overall: /25
Pass: Yes/No (all dimensions 4+)
Red flags: [any auto-fails]
Action needed: [None / Revise output / Fix skill instruction]
```

### For Regression Test (Test 3)

Each phase gets a scorecard. Plus a cross-cutting eval:

**Cross-cutting regression checks:**
- [ ] Brand voice consistency across all 7+ content pieces (no voice drift between skills)
- [ ] Product facts consistent (same specs, same prices, same claims in every output)
- [ ] Strategic consistency (campaign-plan strategy reflected in draft-content and email-sequence)
- [ ] No contradictions between skills (e.g., campaign-plan says "no sitewide discount" but email-sequence includes one)
- [ ] Seasonal timing consistent (all dates align to the same campaign calendar)

### Determining Root Cause

When a score is 3 or below, determine whether the issue is:

1. **Skill instruction gap** — the SKILL.md doesn't tell Claude to handle this case. Fix: update the skill.
2. **Template rigidity** — the SKILL.md has a template that doesn't flex for this category/edge case. Fix: add conditional guidance.
3. **Brand context gap** — the brand/ files don't capture what Claude needs. Fix: update brand templates.
4. **Model behavior** — Claude has the instructions but doesn't follow them well. Fix: rephrase instructions for clarity, add examples, add emphasis.

This distinction matters because it tells you WHERE to fix the problem.

---

## Quality Baselines (What "Good" Looks Like)

### Ad Creative — Score 5 Example (Tern)

**Bad (score 2):**
> "Introducing the Bottle Parka — the perfect accessory for your outdoor adventures! Stay hydrated in style. Shop now!"

Why it fails: Generic. "Perfect accessory." "Stay hydrated in style." Could be any product. No specs. "In style" contradicts Tern's performance-first voice.

**Good (score 5):**
> "Your water bottle freezes at 10,000ft. You're 3 miles from the trailhead. Now what?"
> "The Bottle Parka. Military-grade Thinsulate keeps water liquid to -20F for 4+ hours. Field-tested at 14,000ft because your hydration shouldn't depend on the weather."

Why it passes: Specific scenario the customer recognizes. Exact specs (-20F, 4+ hours, 14,000ft). Technical materials (Thinsulate). "Field-tested" preferred term. No fluff. Tern voice.

### Campaign Plan — Score 5 Example (Tern)

**Bad (score 2):**
> "Offer: 20% off sitewide for ski season launch."

Why it fails: Sitewide % off is bottom of offer hierarchy. Doesn't protect hero SKU. No margin impact calculated. No challenge ("why not a cheaper incentive?").

**Good (score 5):**
> "Offer: Early access for email list (48 hours before public launch). Public launch: free shipping at $60 (drives bundle attach — Summit Kit is $89). BFCM only: $10 off The Full Send bundle ($118 → $108, 8.5% discount, protects individual SKU pricing). The Bottle Parka stays at $34. Kill threshold: if BFCM contribution margin drops below $X at midpoint, pull the bundle discount and revert to free shipping only."

Why it passes: Works down offer hierarchy. Hero SKU protected. Specific numbers. Kill threshold defined. Economics calculated.

### Email Subject Line — Score 5 Example (Tern)

**Bad (score 2):**
> "Don't Miss Out! 🎿"
> "Your Cart is Waiting"
> "Something Special for You"

Why it fails: Generic. No brand, no product, no specificity. Could be from any DTC brand.

**Good (score 5):**
> "Your water bottle froze on the last run. This fixes that."
> "The Bottle Parka: field-tested at 14,000ft"
> "-20F. 4 hours. Still liquid."

Why it passes: Specific to Tern. References the pain point. Uses approved specs. Understated tone.

---

## When to Update the Eval

- **Add a quality baseline** every time you find a great output (score 5) or a terrible one (score 2 or below) — these become reference examples
- **Add a red flag** when you discover a new failure mode that should auto-fail
- **Update per-skill checklists** when skills are updated with new sections
- **Add new edge cases** to Test 2 when the eval reveals gaps the unit tests don't cover
