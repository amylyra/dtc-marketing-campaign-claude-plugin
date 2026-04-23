# Plugin Test Plan

Test brand: **Tern** — a DTC brand selling sport accessories built for extreme conditions. Think insulated gear for the gear you already own: water bottle parkas, phone parkas, goggle warmers, hand warmer pouches. Chosen because it's a niche outdoor/adventure category with physical goods (not beauty, not consumable), which forces the templates to handle hard goods, seasonal use cases, and performance-driven product claims.

**Tern brand profile:**
- Hero SKU: The Bottle Parka ($34) — insulated neoprene sleeve that keeps water from freezing to -20F for 4+ hours
- Secondary SKUs: Phone Parka ($28) — touchscreen-compatible insulated phone case, Goggle Warmer ($22) — anti-fog heated goggle cover, Hand Warmer Pouch ($18) — rechargeable hand warmer with zippered pouch
- Bundles: The Summit Kit ($89, saves $13) — Bottle Parka + Phone Parka + Hand Warmer Pouch; The Full Send ($118, saves $24) — all 4 products
- Price range: $18-$42
- Free shipping at $60
- No subscription model (not a replenishment product)
- Differentiator: Only brand designing insulation specifically for gear, not people. Military-grade Thinsulate + waterproof YKK zippers. Tested at altitude (14,000ft+). "Your gear freezes before you do — we fix that."
- Target customer: Serious outdoor athletes (skiers, mountaineers, winter hikers, ice climbers) 25-45 who already spend on premium gear (Arc'teryx, Patagonia, Black Diamond) but lose function to cold — frozen water bottles, dead phone batteries, fogged goggles
- Secondary customer: Gift-givers buying for the outdoor enthusiast who "has everything"
- Brand voice: Technical and credible but not dry. Confident, field-tested energy. Like a ski patrol buddy who's done 200 days on the mountain. Never precious, never hypey. Understated toughness.
- Avoided terms: "cute", "cozy" (we're performance gear, not lifestyle), "game-changer" (overused), "hack" (we're engineered solutions, not hacks)
- Preferred terms: "field-tested", "expedition-grade", "purpose-built"
- Competitors: Hydro Flask (bottle insulation), Phoozy (phone thermal cases), generic Amazon neoprene sleeves

---

## Test 1: New User Flow (Setup Walkthrough)

Simulate a new user who just installed the plugin and has never used it. Walk through the full recommended flow from README.

### 1.1 `/brand-review setup` — First-Time Brand Onboarding

**Simulate:** User says `/brand-review setup`

**Expected behavior:**
- [ ] Skill detects `brand/` files are empty (template-only)
- [ ] Enters Mode 1: Brand Setup
- [ ] Asks personality question first ("Describe your brand as if it were a person")
- [ ] Does NOT dump all questions at once
- [ ] Works through 6 sections in order: personality, voice attributes, tone by channel, products, customers, terminology
- [ ] Synthesizes answers and confirms before saving
- [ ] Saves to correct files: `brand/voice.md`, `brand/products.md`, `brand/customers.md`
- [ ] After setup, tells user what to do next

**Test inputs (simulate user responses):**
1. Personality: "Tern is the ski patrol veteran who's been on the mountain for 15 years. They don't need to brag — their gear speaks for itself. They'll tell you exactly what works at -20F and why, no fluff. Approachable but no-nonsense. They'd never use the word 'cozy.'"
2. Voice attributes: Technical/credible (we are: specific about materials and performance specs; we are not: academic or jargon-heavy for its own sake), Confident (we are: direct, experienced, field-proven; we are not: aggressive, bro-culture, or arrogant), Understated (we are: let-the-product-speak energy; we are not: hype-driven or exclamation-mark-heavy)
3. Tone: Instagram=field photography + performance proof, TikTok=real conditions testing + "will it survive?" content, Email=direct/informative/seasonal, SMS=short/action/restock alerts, Product pages=specs-forward/test data/use cases, Ads=problem-first/proof-driven
4. Hero product: The Bottle Parka, $34, Thinsulate + waterproof YKK zippers, keeps water liquid to -20F for 4+ hours, tested at 14,000ft+
5. Customer: Serious outdoor athletes 25-45, already own premium gear, lose function to cold conditions. Secondary: gift-givers for "the person who has everything"
6. Terminology: "field-tested" not "lab-tested", "expedition-grade" not "premium", "purpose-built" not "designed". Never: "cozy", "cute", "game-changer", "hack"

**Check for issues:**
- [ ] Does the skill handle hard goods product attributes? (Materials, temperature ratings, test conditions vs. ingredients, skin type)
- [ ] Does the product template work for non-consumable, non-beauty products? (Thinsulate, YKK zippers, neoprene — not serums and ceramides)
- [ ] Does the customer profile template work for outdoor/adventure demographics? (Activity-based segments, not skin concerns)
- [ ] Does terminology capture gear-specific language? (Field-tested, expedition-grade)
- [ ] Does the brand voice capture the "understated technical confidence" without defaulting to beauty/wellness warmth?
- [ ] Are the saved files usable by other skills?

### 1.2 `/campaign-plan` — First Campaign

**Simulate:** User says `/campaign-plan winter launch campaign for Tern — ski season kickoff, November launch`

**Expected behavior:**
- [ ] Reads from `brand/` directory (now populated)
- [ ] References Tern products by name and price (Bottle Parka $34, Phone Parka $28, etc.)
- [ ] Asks for missing inputs (budget, specific audience)
- [ ] Generates full brief with all 10 sections
- [ ] Promo economics section appropriate for a seasonal hard-goods brand (not beauty replenishment)
- [ ] Channel strategy starts with storefront
- [ ] Offer hierarchy suggests cheaper incentives first (bundle savings, free shipping at $60, GWP before % off)
- [ ] Seasonal template: ties to ski season, not generic "holiday"
- [ ] Execution checklist has all 10 pre-launch questions
- [ ] Content calendar accounts for outdoor media lead times

**Check for issues:**
- [ ] Does the seasonal framework handle a product launch timed to a sport season (not Valentine's/Mother's Day)?
- [ ] Does the brief reference actual Tern products and bundles (Summit Kit $89, Full Send $118)?
- [ ] Is the audience section using outdoor athlete profiles from `brand/customers.md`?
- [ ] Does budget allocation make sense for a niche outdoor brand? (Heavier influencer/UGC with outdoor creators, less broad Meta prospecting)
- [ ] Does the plan handle the no-subscription reality? (No replenishment angle, so retention = new product launches + gift-giving seasons)
- [ ] Is hero SKU protection applied correctly? (Don't discount The Bottle Parka — it's the anchor)

### 1.3 `/draft-content` + `/email-sequence` — Parallel Content Production

#### 1.3a `/draft-content` — Ad Creative for Ski Season Launch

**Simulate:** User says `/draft-content ad creative for Tern Bottle Parka ski season launch`

**Expected behavior:**
- [ ] Auto-applies brand voice from `brand/voice.md` (technical, understated, no hype)
- [ ] Pulls product details from `brand/products.md` (Thinsulate, -20F, 4+ hours, YKK zippers)
- [ ] Uses customer language from `brand/customers.md` (gear-obsessed, performance-driven)
- [ ] Produces 5 ad frameworks with hooks
- [ ] Platform specs correct (9:16, 1:1, 4:5)
- [ ] Messaging hierarchy: why care → what is it → why this brand → CTA
- [ ] Performance-proof angle (not lifestyle/aspirational fluff)
- [ ] TikTok creative: "will it survive?" testing content, not polished brand video

**Check for issues:**
- [ ] Do ad hooks work for insulated gear accessories? (Before/after = frozen vs liquid water bottle — actually works here)
- [ ] Is UGC testimonial framework adapted for outdoor gear? (Backcountry context, not bathroom mirror selfie)
- [ ] Does the founder story framework prompt for outdoor/engineering narrative?
- [ ] Are hook variants performance-focused, not beauty-focused? ("Your water bottle freezes at 10,000ft. Ours doesn't." not "Feel the difference")
- [ ] Does the copy avoid "cozy", "cute", "game-changer", "hack"?

#### 1.3b `/email-sequence` — Ski Season Launch Sequence

**Simulate:** User says `/email-sequence product launch for Tern ski season collection`

**Expected behavior:**
- [ ] Identifies this as promo-specific (product launch, time-bound)
- [ ] Auto-applies brand context
- [ ] Generates full flow diagram with email + SMS
- [ ] Copy reflects Tern brand voice (technical, direct, no fluff)
- [ ] Products referenced by name and specs
- [ ] Launch sequence: teaser → reveal → available now (per product launch template)
- [ ] SMS compliance included
- [ ] Timing makes sense for November ski season launch
- [ ] Mentions suppression rules

**Check for issues:**
- [ ] Does the flow handle a seasonal product launch (not a beauty replenishment or subscription)?
- [ ] Is there appropriate urgency? (Ski season timing, not artificial scarcity)
- [ ] Does SMS copy stay under 160 chars with brand name and STOP language?
- [ ] Does the welcome series recommendation account for no subscription? (Can't pitch "subscribe and save" — need alternative retention angle)
- [ ] Is the post-purchase flow adapted for a non-consumable? (No replenishment, but: care instructions, field tips, UGC request, cross-sell other Tern products)

### 1.4 `/brand-review` — QA Content

**Simulate:** User pastes ad creative and email copy from step 1.3 and says `/brand-review`

**Expected behavior:**
- [ ] Enters Mode 2: Brand Review (brand files populated)
- [ ] Checks voice consistency against `brand/voice.md` (technical, understated — flags any hype language)
- [ ] Checks product claims against `brand/products.md` (-20F rating, 4+ hours, 14,000ft testing)
- [ ] Checks terminology: flags "cozy", "cute", "game-changer", "hack" as avoided terms
- [ ] Checks "expedition-grade" and "field-tested" are used correctly
- [ ] FTC compliance: product performance claims need substantiation (temperature ratings, test conditions)
- [ ] Outputs structured review with severity levels
- [ ] Provides before/after revisions for top issues

### 1.5 `/performance-report` — Post-Campaign Analysis

**Simulate:** User says `/performance-report promo post-mortem for ski season launch` and provides data

**Expected behavior:**
- [ ] Identifies report type as promo post-mortem
- [ ] Uses brand context for product segmentation (Bottle Parka vs Phone Parka vs bundles)
- [ ] 7-signal promo health check applied
- [ ] Contribution margin calculated correctly
- [ ] Handles seasonal product (no "replenishment" metric — uses new customer acquisition, bundle attach rate, gift-giver conversion instead)
- [ ] 14-day hangover check included
- [ ] Verdict: repeat, revise, or kill
- [ ] Discount penetration guardrails checked

---

## Test 2: Unit Tests (Edge Cases per Skill)

### 2.1 `brand-review` Edge Cases

| Test Case | Input | Expected Behavior |
|-----------|-------|-------------------|
| No brand/ files at all | `/brand-review` with no content | Detects empty files, enters setup mode |
| Partial brand setup | Only `voice.md` filled in | Asks "continue setup or review with partial?" |
| Review without brand context | Paste content, no brand/ files | Falls back to generic review (clarity, consistency, effectiveness) |
| Non-English content | Paste German product copy (outdoor gear market) | Reviews for clarity, consistency; notes language |
| Content with compliance violations | Paste ad claiming "waterproof" without IP rating | Flags unsubstantiated performance claim |
| Subscription copy without terms | "Subscribe and save!" with no details | Flags missing auto-renewal, cancellation, and pricing info |
| Content for wrong channel | Formal product page copy labeled as TikTok | Flags tone mismatch |
| UGC without rights | Customer summit photo used in ad | Flags UGC usage rights |
| Performance claim without test data | "Keeps water liquid in ANY conditions" | Flags superlative claim without qualification — needs temperature range and duration |
| Competitor comparison without evidence | "Better than Hydro Flask" | Flags comparative claim that could be challenged |

### 2.2 `campaign-plan` Edge Cases

| Test Case | Input | Expected Behavior |
|-----------|-------|-------------------|
| No brand context | `/campaign-plan BFCM` with no brand/ | Prompts to set up brand or paste details |
| Single-product brand | Only The Bottle Parka, no other SKUs | Adapts — no bundle offers, focus on volume and gift sets |
| Very low budget | "$500 total budget" | Reallocates: heavy email/SMS, UGC from existing customers, minimal paid |
| No competitors provided | `/campaign-plan product launch` | Runs without competitive scan, notes it's available |
| High-ticket DTC ($500+ AOV) | Heated jacket at $450 | Adjusts: longer consideration, consultative content, warranty emphasis |
| Sitewide sale request | "25% off everything for BFCM" | Challenges: "Why not bundle savings or free shipping threshold first?" |
| Off-season campaign | "Summer sale for winter gear" | Flags seasonality mismatch, suggests: clearance positioning or early-bird for next season |
| No subscription model | "How do we retain customers?" | Adapts: new product launches, seasonal restocking, cross-sell, referral, community — not replenishment |
| Gift-giving campaign | "Holiday gift guide push" | Shifts to gift-giver persona, "for the person who has everything" angle |

### 2.3 `draft-content` Edge Cases

| Test Case | Input | Expected Behavior |
|-----------|-------|-------------------|
| No brand context | `/draft-content product description` | Prompts for brand setup or guidelines |
| Content type not in list | "Write a press release" | Explains this is DTC-focused, suggests product launch announcement instead |
| Performance claims | "Write ad claiming -40F protection" | Cross-checks against brand/products.md (-20F approved), flags unapproved claim |
| Multiple products in one piece | "Gift guide with all 4 Tern products + bundles" | Uses gift guide template, organizes by price tier and use case |
| TikTok for technical gear | "TikTok ad for Bottle Parka" | "Will it survive?" format, field-test content, not polished brand video |
| SMS over character limit | Asks for SMS with product specs | Stays under 160 chars, leads with benefit not specs |
| Ad without a product URL | "Write Meta ad" but landing page doesn't exist yet | Flags: storefront asset is blocking dependency |
| Influencer brief for outdoor creators | "Brief for backcountry skiing creator, 50K followers" | Adjusts: field-testing angle, authentic usage, safety considerations, FTC disclosure |
| Collection page for "Winter Essentials" | `/draft-content collection page` | SEO-optimized, descriptive, groups products by use case (hydration, electronics, warmth) |

### 2.4 `email-sequence` Edge Cases

| Test Case | Input | Expected Behavior |
|-----------|-------|-------------------|
| No brand context | `/email-sequence welcome series` | Prompts for brand or uses generic DTC tone |
| All 12 flows at once | "Build my entire retention system" | Prioritizes: welcome → abandoned cart → post-purchase first. Notes: skip replenishment (non-consumable) |
| Non-consumable product | Tern gear (lasts years) | Adjusts: no replenishment flow, post-purchase focuses on care tips, cross-sell, UGC, referral |
| No SMS opt-in | "We don't have SMS yet" | Builds email-only flows, recommends SMS adoption |
| Promo + lifecycle conflict | "BFCM sale while welcome series running" | Recommends suppression rules |
| Seasonal business | "Most sales Nov-Feb" | Adjusts: off-season flows focus on engagement/content, ramp up pre-season |
| Brand with no reviews | "We just launched, no reviews yet" | Adjusts: founder story, field-test data, press/media mentions as social proof |
| International audience | "We sell to Canada, EU, and US" | Notes: quiet hours differ, GDPR for EU, different SMS compliance, currency |

### 2.5 `competitive-brief` Edge Cases

| Test Case | Input | Expected Behavior |
|-----------|-------|-------------------|
| No brand context | `/competitive-brief Hydro Flask` | Runs without "Your Brand" column in matrices |
| Competitor in adjacent category | "Analyze Hydro Flask" (bottles, not insulation accessories) | Frames as adjacent competitor, focuses on overlap: "keeping drinks cold/hot" |
| Same-category giant | "Analyze Patagonia" | Frames around niche positioning — Tern is accessories, not apparel. Find the wedge. |
| Multiple competitors (5+) | "Compare against Hydro Flask, Phoozy, Yeti, Stanley, Nalgene, CamelBak" | Suggests focusing on 2-3 most relevant (Hydro Flask insulation, Phoozy phone cases) |
| No direct competitor | "Nobody else makes goggle warmers" | Notes category creation opportunity, analyzes closest substitutes and adjacent solutions |

### 2.6 `performance-report` Edge Cases

| Test Case | Input | Expected Behavior |
|-----------|-------|-------------------|
| No data provided | `/performance-report weekly` | Prompts for data sources, suggests format to paste data |
| Only revenue data | "We did $80K in November" | Works with available data, notes what's missing for full analysis |
| Discount penetration at 40% | Heavy BFCM discounting | Flags as structural problem (>35%), recommends protecting no-promo zones |
| Post-promo hangover detected | December sales dropped 40% after BFCM | Flags in 7-signal check, notes BFCM likely borrowed from holiday demand |
| Seasonal brand with no YoY data | First ski season of sales | Adjusts: no YoY, uses category benchmarks, establishes baseline for next year |
| Bundle performance question | "Are bundles cannibalizing individual SKU sales?" | Analyzes: bundle attach rate, individual SKU velocity pre/post bundle launch, AOV impact |
| Attribution confusion | "Meta says 5x ROAS but revenue didn't change" | Explains post-iOS14 issues, recommends blended MER |

### 2.7 `seo-audit` Edge Cases

| Test Case | Input | Expected Behavior |
|-----------|-------|-------------------|
| No brand context | `/seo-audit tern.com` | Runs standard audit without product-to-keyword matching |
| Niche product with low search volume | "insulated water bottle sleeve" — tiny search volume | Identifies adjacent keywords: "keep water from freezing hiking", "winter hydration gear" |
| Pre-launch site | "We haven't launched yet" | Keyword research mode, pre-launch SEO recommendations |
| Seasonal search patterns | Winter gear keywords spike Oct-Feb | Notes seasonality, recommends publishing content 2-3 months before peak |
| No blog or content pages | Product pages only | Identifies content gap: buying guides ("best winter hiking accessories"), how-tos ("how to keep your water bottle from freezing") |
| Category creation SEO | "Nobody searches for 'bottle parka'" | Recommends targeting problem-based queries ("water bottle freezing while skiing") not product-name queries |

---

## Test 3: Regression Test (Full Ski Season Launch — End to End)

**Test brand:** Tern (from Test 1 setup)
**Campaign:** Ski Season 2026 Launch + BFCM Bundle Push
**Timeline:** November 1 - December 15, 2026 (two-phase: launch Nov 1, BFCM Nov 27)

### Phase 0: Brand Foundation
- [ ] `/brand-review setup` completes with all 6 sections for Tern
- [ ] All 3 brand files saved and readable by other skills
- [ ] Product attributes are gear-specific (materials, temp ratings, test conditions) not beauty-specific

### Phase 1: Strategy
- [ ] `/campaign-plan ski season launch + BFCM for Tern, competitors: Hydro Flask, Phoozy` generates full brief
- [ ] Brief includes: promo economics with margin impact, two-phase approach (launch Nov 1 → BFCM Nov 27)
- [ ] Offer hierarchy applied: launch phase = early access + bundles, BFCM = free shipping + bundle discount (no sitewide % off on hero)
- [ ] Hero SKU protection: Bottle Parka never discounted below $34 individually
- [ ] Content calendar works backward from Nov 1 launch and Nov 27 BFCM
- [ ] Kill threshold defined for each phase
- [ ] 10 pre-launch questions answered in brief
- [ ] Channel strategy recognizes outdoor media/influencer weight

### Phase 2: Competitive Context
- [ ] `/competitive-brief Hydro Flask, Phoozy` generates comparison
- [ ] Hydro Flask analyzed as adjacent competitor (bottle insulation built-in vs. accessory)
- [ ] Phoozy analyzed as direct competitor (phone thermal protection)
- [ ] Positioning gaps identified (Tern = only brand with full gear insulation system)
- [ ] Promo intelligence: when do competitors discount? (Hydro Flask BFCM patterns)
- [ ] Insights actionable for campaign-plan

### Phase 3: Content Production (parallel)
- [ ] `/draft-content product description for The Bottle Parka` — specs-forward product copy
- [ ] `/draft-content ad creative for Tern ski season launch` — 5 frameworks, field-test hooks
- [ ] `/draft-content gift guide for holiday — Tern products` — "for the outdoor enthusiast who has everything"
- [ ] `/draft-content social media post TikTok for Bottle Parka field test` — "will it survive?" format
- [ ] `/draft-content influencer brief for backcountry skiing creator` — FTC-compliant, authentic field-testing
- [ ] `/email-sequence product launch for Tern ski season` — launch promo flow
- [ ] `/email-sequence welcome series` — always-on foundation

All 7 should run independently. Check:
- [ ] Every piece references "The Bottle Parka" by name, $34 price, -20F / 4+ hours
- [ ] Every piece uses Tern voice (technical, understated, field-tested — NOT warm/bubbly/lifestyle)
- [ ] Performance claims match approved specs in `brand/products.md`
- [ ] No beauty/skincare assumptions bleeding through (no "ingredients", no "skin", no "routine")
- [ ] No avoided terms: "cozy", "cute", "game-changer", "hack"
- [ ] Preferred terms present where appropriate: "field-tested", "expedition-grade", "purpose-built"
- [ ] FTC compliance where required (influencer brief, performance claims substantiated)
- [ ] SMS under 160 chars with STOP language
- [ ] Ad hooks are performance-proof focused (frozen bottle test, altitude test, duration test)
- [ ] Gift guide uses "for the outdoor enthusiast who has everything" angle
- [ ] TikTok content feels like field-test content, not polished brand video

### Phase 4: QA
- [ ] `/brand-review` on all content from Phase 3
- [ ] Voice consistency confirmed (technical, understated — catches any warmth/hype creep)
- [ ] Product claims verified against `brand/products.md` (no unapproved temp ratings or durations)
- [ ] Avoided terms caught: "cozy", "cute", "game-changer", "hack"
- [ ] Performance claims substantiated (temperature ratings reference test conditions)
- [ ] No subscription language (Tern has no subscription model)

### Phase 5: Launch + Monitoring
- [ ] Campaign-plan execution checklist: all 10 pre-launch questions answered
- [ ] Daily check-in template: conversion, AOV, CAC, margin, SKU mix, bundle attach rate
- [ ] BFCM-specific monitoring: discount penetration, hero SKU pricing integrity

### Phase 6: Post-Mortem
- [ ] `/performance-report promo post-mortem for ski season launch + BFCM`
- [ ] 7-signal promo health check applied separately for launch phase and BFCM phase
- [ ] Contribution margin calculated for each phase
- [ ] Counterfactual baseline: trailing October sales (off-season) vs. same-season if available
- [ ] 14-day hangover check: did December sales dip after BFCM?
- [ ] Bundle performance: did Summit Kit and Full Send bundles increase AOV without cannibalizing individual SKUs?
- [ ] Gift-giver segment: what % of BFCM/holiday buyers were gifting vs. self-purchase?
- [ ] Verdict per phase: repeat, revise, or kill
- [ ] Discount penetration impact on annual guardrails

### Cross-Cutting Checks (apply to all phases)
- [ ] No B2B artifacts (MQLs, SQLs, pipeline, webinars, demo requests)
- [ ] No beauty/skincare language in output (no "ingredients", "routine", "skin type", "glow")
- [ ] No subscription assumptions (Tern doesn't have a subscription)
- [ ] Brand context flows through every skill without re-entering
- [ ] Storefront-first principle enforced in campaign-plan and draft-content
- [ ] Contribution margin referenced as north star in campaign-plan and performance-report
- [ ] Offer hierarchy challenged when deep discounting proposed
- [ ] Hero SKU protection enforced (Bottle Parka not individually discounted)
- [ ] Kill thresholds defined before launch, not after
- [ ] Seasonal business reality acknowledged (most revenue Nov-Feb, not year-round)

---

## Findings Log

Track issues discovered during testing here:

| # | Test | Skill | Issue | Severity | Status |
|---|------|-------|-------|----------|--------|
| | | | | | |

Severity: Critical (broken), High (produces wrong output), Medium (suboptimal), Low (cosmetic/minor)
Status: Found, Fixed, Won't Fix
