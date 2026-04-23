# Evaluation Rubric

How to score skill output quality — not just "did it run" but "is it good."

## Scoring Framework

Every skill output is scored on 6 dimensions. Each dimension is 1-5. A passing score is 4+ on every dimension. A 3 in any dimension means the output needs revision. A 2 or below means the skill instruction itself likely needs a fix.

| Score | Meaning |
|-------|---------|
| 5 | Ready to use. A DTC operator would ship this with minor tweaks. |
| 4 | Solid foundation. Needs light editing but the thinking is right. |
| 3 | Directionally correct but generic, incomplete, or needs significant rework. |
| 2 | Missed the point. Wrong strategy, wrong tone, or missing critical elements. |
| 1 | Broken. Produced B2B output, ignored brand context, or gave harmful advice. |

---

## 6 Evaluation Dimensions

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
- [ ] Summary includes engagement assessment line ("Engagement: Strong/Needs work/Weak — reason")
- [ ] Detailed findings table with severity levels (includes engagement findings)
- [ ] Product claim cross-check table
- [ ] Before/after revisions for top 3-5 issues
- [ ] Legal/compliance flags section
- [ ] Channel appropriateness check
- [ ] Hook strength evaluated (pattern interrupt, specificity)
- [ ] Swap test applied (competitive distinctiveness flagged if fails)
- [ ] Variant diversity checked (if multi-variant content reviewed)

#### campaign-plan (4-step flow)
- [ ] Opening orientation present (4-step pipeline explained in 3-4 lines)
- [ ] Step 1A: 3 theme options presented (Safe Bet, Competitive Edge, Wild Card) — each has one-line name + 2-3 sentence pitch, all readable in under 30 seconds
- [ ] Step 1A gate asks user to pick, mix, or riff — not "shall I continue?"
- [ ] Step 1B: theme iterated based on user feedback, then locked strategy in table format (theme, audience, messages, offer, kill threshold, promo economics)
- [ ] Step 1B gate confirms strategy lock before proceeding to assets
- [ ] Step 2 complete: site creative asset checklist tiered (essential/recommended/only-if-needed), copy direction per asset tied to campaign story, brand guide/UI kit consulted
- [ ] Step 3 complete: email tiered (essential/recommended/optional), Meta tiered, SMS essentials only, Google essentials only, campaign timeline table, budget allocation
- [ ] Step 4 complete: 3-5 KPIs with targets, 2-3 risks with mitigations, condensed execution checklist (top 5 questions)
- [ ] Gates present between each step (user sign-off requested)
- [ ] Materials question asked at start of Step 2 (not Step 1)
- [ ] Output is concise and scannable (tables, bullets, not walls of text)

#### draft-content
- [ ] Correct content type template used
- [ ] Messaging hierarchy present (why care → what is it → why this brand → CTA)
- [ ] Brand voice note included
- [ ] SEO recommendations for web content
- [ ] Platform-specific formatting (ad specs, character limits, aspect ratios)
- [ ] Multiple variants where specified (hooks, subject lines)
- [ ] Hook quality self-check passed (pattern interrupt, specificity, platform-native)
- [ ] Variant diversity: 4+ distinct angles in any 5+ variant set
- [ ] Swap test passed: copy is not usable by a competitor with a name change
- [ ] Audience-adaptive messaging applied when non-primary audience specified

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

### 5. Engagement & Persuasion (Is the copy actually compelling?)

Would this content perform in market — not just pass a brand check, but actually stop a scroll, open an email, or drive a click? This dimension catches the gap between "correct" and "competitive."

**Checks:**
- Hook / headline / subject line passes the pattern interrupt test — would it stop a scroll between competitor content?
- Hooks use specificity (scenarios, numbers, sensory details), not generic benefits or cleverness
- Variants are genuinely diverse angles, not the same idea reworded (minimum 4 distinct angles in 5+ variant sets)
- Swap test: a competitor could NOT put their name on this and use it
- Tension before resolution — problem or gap appears before the product/solution
- Proof is placed at the moment of doubt, not just listed as features
- CTA is specific (product name, price, action) not vague ("Shop now", "Learn more")
- Urgency is real (deadline, inventory, season) not manufactured ("Don't miss out!")
- Objections are anticipated and addressed, not ignored

**Scoring:**
- 5: Copy is ready to run. Hooks are thumb-stopping. Variants are diverse. Would outperform typical category content. An operator would test this immediately.
- 4: Strong foundation. One or two hooks need sharpening, or proof placement could be tighter. Minor competitive lift needed.
- 3: Correct but not compelling. Hooks are generic or share the same angle. Passes brand check but wouldn't outperform competitor content. Needs significant copy revision.
- 2: Informational, not persuasive. Reads like a brief, not a draft. No tension, no specificity, no pattern interrupt.
- 1: Would actively underperform. Generic to the point of being invisible in-feed. "Introducing the [product] — shop now!"

**Red flags that auto-fail:**
- All hooks are the same angle reworded
- Hook starts with brand name or "Introducing..."
- Swap test fails — copy could be any competitor's with a name change
- No specific numbers, scenarios, or proof anywhere in the content
- CTA is "Shop now" with no product, price, or action specificity

### 6. Adaptability (Did it actually handle the edge case?)

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
| Engagement & Persuasion | /5 | |
| Adaptability | /5 | |

Overall: /30
Pass: Yes/No (all dimensions 4+)
Red flags: [any auto-fails]
Action needed: [None / Revise output / Fix skill instruction]
```

Note: Engagement & Persuasion applies most directly to content-producing skills (draft-content, email-sequence, campaign-plan copy direction). For analytical skills (performance-report, seo-audit, competitive-brief), score this dimension on the persuasiveness and actionability of recommendations — are they specific enough that the team would act on them immediately, or are they generic "consider doing X" suggestions?

### For Regression Test (Test 3)

Each phase gets a scorecard. Plus a cross-cutting eval:

**Cross-cutting regression checks:**
- [ ] Brand voice consistency across all 7+ content pieces (no voice drift between skills)
- [ ] Product facts consistent (same specs, same prices, same claims in every output)
- [ ] Strategic consistency (campaign-plan strategy reflected in draft-content and email-sequence)
- [ ] No contradictions between skills (e.g., campaign-plan says "no sitewide discount" but email-sequence includes one)
- [ ] Seasonal timing consistent (all dates align to the same campaign calendar)
- [ ] Engagement quality consistent — hooks and copy across all skills meet the same pattern-interrupt and specificity bar (no skill producing generic copy while others are sharp)

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

### Hook Variants — Score 5 Example (Tern, Ad Creative)

**Bad (score 2) — same angle reworded:**
> 1. "Keep your water from freezing on the trail"
> 2. "Stop your water bottle from freezing"
> 3. "Don't let your water freeze on winter hikes"
> 4. "Prevent frozen water bottles on the mountain"
> 5. "Your water won't freeze anymore"

Why it fails: All 5 are the same direct-benefit angle. No diversity. No pattern interrupt. Any outdoor gear brand could use these.

**Good (score 5) — genuinely diverse angles:**
> 1. **Scenario**: "You're 3 miles from the trailhead. Your water bottle is a solid block of ice. Now what?"
> 2. **Contrarian**: "Insulated bottles cost $45 and still freeze. This costs $34 and insulates the bottle you already own."
> 3. **Social proof**: "2,847 skiers switched last winter. Here's what they figured out."
> 4. **Identity**: "For the person who's 'fine' at 14,000ft but their water bottle isn't."
> 5. **Curiosity gap**: "The reason ski patrol started buying these isn't what you'd think."

Why it passes: 5 distinct angles (scenario, contrarian, social proof, identity, curiosity). Each earns the next line differently. Swap test passed — the specifics (14,000ft, $34, ski patrol) are ownable. Platform-native (these read like social/ad hooks, not product page copy).

### Brand Review — Engagement Assessment Examples

**Weak engagement flag:**
> "Copy is on-brand and factually accurate. However, hook 'Introducing the Bottle Parka — our newest product' starts with the brand name and uses an announcement frame. A competitor could use this copy with a name swap. Hooks need specific scenarios or proof to create pattern interrupts."

**Strong engagement pass:**
> "Engagement: Strong. Hooks use specific scenarios (frozen water at altitude) and brand-ownable proof (-20F, 14,000ft). Swap test passed — competitor couldn't replicate the specificity. Subject line 'Your water bottle froze on the last run. This fixes that.' creates tension before resolution."

---

## When to Update the Eval

- **Add a quality baseline** every time you find a great output (score 5) or a terrible one (score 2 or below) — these become reference examples
- **Add a red flag** when you discover a new failure mode that should auto-fail
- **Update per-skill checklists** when skills are updated with new sections
- **Add new edge cases** to Test 2 when the eval reveals gaps the unit tests don't cover
