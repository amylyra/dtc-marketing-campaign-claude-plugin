# Fix Plan v2

22 findings from Tern testing. The original plan grouped them into 4 themes. But on review, the themes are interconnected through **buyer psychology** — the product type shapes the buyer's mindset, the buyer's mindset determines what works in every skill, and the category position determines where the buyer sits on the awareness spectrum.

The optimized plan has one foundational fix and three cascading layers.

---

## Foundation: Buyer Psychology in `brand/customers.md`

**The root insight:** The current customers.md template captures WHO buys (demographics, language) but not HOW they decide. Every skill downstream needs to know the buyer's decision-making psychology — not just their demographics — to produce output that actually converts.

A Tern athlete and a Glow Lab skincare buyer are both "millennials who care about quality." But their psychology is completely different:

| Dimension | Tern Athlete | Glow Lab Buyer |
|-----------|-------------|---------------|
| Decision mode | Researched, comparative, spec-driven | Semi-considered, peer-influenced, aspiration-driven |
| Trust hierarchy | Peer review > field data > brand claims | Creator endorsement > reviews > before/after |
| Risk perception | "Will it actually work at -20F?" (performance fear) | "Will it irritate my skin?" (safety fear) |
| Consideration depth | Multi-session. Reads Reddit, watches YouTube reviews. | 1-2 sessions. Sees a TikTok, checks reviews, buys. |
| Purchase trigger | Upcoming trip/season. Functional need. | Aspiration, self-care moment, FOMO from social proof. |
| Objection pattern | "Prove it works" (needs data) | "Prove it's worth the price" (needs validation) |
| Post-purchase | Evaluates against real-world performance. Hard to impress, hard to disappoint. | Evaluates against expectation set by marketing. Easy to delight, easy to disappoint. |
| Advocacy trigger | Product survives a real test (summit, storm). Shares because it earned respect. | Visible result (glow, compliment from friend). Shares because it makes them feel good. |
| Channel trust | Reddit, gear review blogs, YouTube deep-dives > Instagram | Instagram, TikTok, friend referral > blogs |
| Loyalty driver | Product quality + new products in the line | Routine integration + community + subscription convenience |

This psychology changes EVERYTHING downstream. Not just the hooks — the flow structure, the channel weight, the email timing, the proof strategy, the win-back angle, the post-purchase sequence, the competitive framing.

### Fix: Expand `brand/customers.md` template

Add a **Buyer Psychology** section to each customer segment. This sits between "Who they are" and the language bank:

```markdown
## Primary Customer

### Who they are
- **Demographics**: 
- **Psychographics**: 

### Buyer Psychology
- **Decision mode**: How they evaluate a purchase — impulse, semi-considered, or deeply researched? Do they compare options or buy on instinct?
- **Trust hierarchy**: What sources do they trust, in order? (peer reviews, creator content, clinical data, press, brand claims, social proof volume)
- **Risk perception**: What are they afraid of when buying? Performance risk ("will it work?"), social risk ("will they like it?"), financial risk ("is it worth it?"), safety risk ("will it hurt me?")
- **Purchase trigger**: What event or moment pushes them from browsing to buying? (Upcoming trip, seasonal need, seeing a result on social, running out of product, friend recommendation)
- **Consideration depth**: How many sessions before purchase? What do they do between sessions? (Compare on Reddit, ask friends, watch reviews, sleep on it, wait for a sale)
- **Objection pattern**: What objections does this buyer have, and what TYPE of proof resolves them? (Data resolves performance doubt. Social proof resolves value doubt. Guarantee resolves risk doubt.)
- **Post-purchase psychology**: What makes them feel good about the purchase? What triggers regret? What would make them advocate?
- **Advocacy trigger**: What would make this person tell a friend or post about it? (Product exceeds expectations in a specific way, visible result, compliment from someone, survives a real test)

### Language Bank
<!-- Their actual words — from reviews, DMs, social comments -->
```

Add the same psychology section for gift-giver and other segments:

```markdown
## Gift-Giver

### Buyer Psychology
- **Decision mode**: Proxy decision — buying for someone else's needs. Lower product knowledge, higher reliance on curation ("best for", "most popular", gift guides).
- **Trust hierarchy**: "Best-seller" status > reviews from other gift-givers > price-as-quality signal > brand reputation
- **Risk perception**: Social risk — "Will they like it? Will this make me look thoughtful or clueless?" Return policy and gift receipt matter more than product specs.
- **Purchase trigger**: Calendar-driven (holiday, birthday, Mother's Day). Often last-minute. Gift guides and "arrives by" guarantees are conversion drivers.
- **Consideration depth**: Low. 1 session if guided well (gift guide with price tiers). Likely comparing across BRANDS, not within your catalog.
- **Objection pattern**: "Is this a good gift?" (needs social proof from other gift-givers). "Will it arrive in time?" (needs shipping clarity). "What if they don't like it?" (needs return policy).
- **Post-purchase psychology**: Relief ("done, good gift, moving on"). They don't become a repeat customer unless they also discover the product is for THEM.
- **Advocacy trigger**: Recipient tells them they love it. "My mom won't stop talking about it" → now the gift-giver becomes a buyer.
```

And for VIP / repeat:

```markdown
## VIP / Repeat Buyer

### Buyer Psychology
- **Decision mode**: Low consideration for repurchase (they've decided). High consideration for new products (they have standards).
- **Trust hierarchy**: Their own experience > brand communications > everything else. They trust YOU because you've earned it — don't squander it with hype.
- **Risk perception**: LOW for known products. For new products: "Is this as good as the thing I already love?" Don't oversell — let them try.
- **Purchase trigger**: Running out (consumable), new product launch (durable), seasonal need, loyalty reward.
- **Objection pattern**: Price is not an objection. Discounts can actually OFFEND if they just bought at full price. Biggest objection: "Is the new product as good as what I already have?"
- **Post-purchase psychology**: Expects consistency. Delighted by surprises (handwritten note, free sample, early access). Betrayed by quality drops or aggressive upselling.
- **Advocacy trigger**: Feeling like an insider. "I've been buying this since before anyone knew about it." Give them status and they'll recruit.
```

### Why this is foundational (not just a template improvement)

Every skill reads `brand/customers.md`. When buyer psychology is IN the file, every skill can adapt:

| Skill | How it uses buyer psychology |
|-------|------------------------------|
| **draft-content** | Matches proof type to the buyer's trust hierarchy. Research buyer gets specs and test data. Social buyer gets reviews and UGC. Gift-giver gets "best-seller" validation. |
| **email-sequence** | Adapts flow structure — not just copy. Abandoned cart for a researcher = comparison data + reviews (they're deciding, not distracted). Abandoned cart for impulse buyer = simple reminder + urgency. |
| **campaign-plan** | Allocates channel budget by where the buyer trusts recommendations. Reddit-trusting audience = content + SEO. TikTok-trusting audience = creator partnerships + paid social. |
| **brand-review** | Checks whether the content's proof strategy matches the buyer's trust hierarchy. If the buyer needs data and the copy provides vibes, flag it. |
| **competitive-brief** | Frames competitor analysis through the lens of what the buyer actually evaluates. Feature-comparing buyer = spec comparison. Aspiration buyer = brand positioning comparison. |
| **performance-report** | Segments cohorts by acquisition psychology, not just channel. "Discount-acquired" vs "full-price-acquired" vs "gift-received" behave differently. |

---

## Layer 1: Product-Type Awareness

*Connected to buyer psychology: product type shapes the buyer's default mindset.*

Consumable = habitual purchase, routine-driven loyalty, convenience matters.
Durable = considered purchase, research-heavy, loyalty through quality and new products.
Fashion = emotional purchase, trend-influenced, loyalty through identity.
Seasonal = calendar-driven, urgency-based, loyalty through annual ritual.

### Fix: Add Product Type to `brand/products.md`

At the top, add:

```markdown
## Product Profile

- **Product type**: Consumable / Durable goods / Fashion & apparel / Subscription-native
- **Replenishment cycle**: [e.g., "30 days", "N/A — lasts years"]
- **Seasonal demand**: [e.g., "Year-round", "Nov-Feb peak"]
- **Subscription available**: Yes / No
- **SKU count**: [e.g., "4 products + 2 bundles"]
- **Price range**: [e.g., "$18-$42"]
- **Margin structure** (optional): Approximate gross margin % or COGS per unit
```

Rename "Ingredients / Materials / What's included" to "Materials / What's included" (removes beauty bias).

### Cascade to skills:

**`campaign-plan/SKILL.md`:**

Add "Offer Hierarchy by Product Type" after the main offer hierarchy:

**Single-SKU:** Hierarchy compresses — early access → free shipping → multi-unit discount (gift play) → modest % off (tentpole only). No bundles or secondary SKU discounts.

**Durable (non-consumable):** No replenishment lever. Retention strategy = new product launches + seasonal re-engagement + cross-sell + community + referral. Never assume subscription.

**Seasonal demand:** Off-season strategy required. Don't force standard promos in off-season. Options: clearance, pre-season early-bird, brand-building content, product development with VIP beta testers.

Add "Off-Season / Counter-Seasonal Campaign" and "Sport/Activity Season Launch" to Campaign Types.

Add to budget section: "For niche categories with strong creator communities, consider shifting 10-15% from broad paid to influencer/UGC."

**`email-sequence/SKILL.md`:**

Add "Flow Applicability by Product Type" matrix:

| Flow | Consumable | Durable | Fashion | Subscription |
|------|-----------|---------|---------|-------------|
| Welcome | Yes | Yes | Yes | Yes |
| Abandoned cart | Yes | Yes (adapt: research-mode recovery) | Yes | Yes |
| Post-purchase | Yes | Yes (adapt: no replenishment) | Yes | Yes |
| Browse abandonment | Yes | Yes | Yes | Yes |
| Win-back | Yes | Yes (trigger: new product/season) | Yes (trigger: new collection) | Yes |
| VIP/Loyalty | Yes | Yes | Yes | Yes |
| Back-in-stock | Yes | Yes | Yes (high priority) | Rare |
| Price drop | Yes | Yes | Yes (high priority) | No |
| Replenishment | Yes | **Skip** | Rare | Built-in |
| Review request | Yes | Yes | Yes | Yes |
| Referral | Yes | Yes | Yes | Yes |
| Birthday | Yes | **Skip unless lifestyle brand** | Yes | Yes |

Add durable goods post-purchase adaptation:
- Replace replenishment (step 5) with: new product notification or seasonal re-engagement
- Replace second-purchase incentive (step 6) with: cross-sell within product line ("you bought Bottle Parka, meet Phone Parka")
- Add: referral prompt after positive review or 60 days

Add abandoned cart adaptation by buyer psychology:
- **Researched buyer** (durable, technical, high-consideration): Cart recovery should provide comparison data, peer reviews, and objection answers. They aren't distracted — they're deciding. Don't lead with urgency or discounts. Lead with proof.
- **Impulse/emotional buyer** (beauty, fashion, low-consideration): Cart recovery should use reminder + social proof + urgency. They were distracted. Get them back fast.
- **Gift-giver**: Cart recovery should reassure: "This is their most-gifted product," return/exchange policy, arrival date guarantee.

**`performance-report/SKILL.md`:**

Add "Seasonal Business Adjustments" — same-season YoY baseline, per-season discount penetration, season-aligned repeat purchase windows.

Add "New Brand / No Baseline Protocol" — industry benchmarks as reference, establish baseline, focus on leading indicators.

Add cohort segmentation by acquisition psychology: "When segmenting cohorts, distinguish between full-price-acquired, discount-acquired, and gift-received customers. Their repeat purchase behavior and LTV will differ structurally."

---

## Layer 2: Audience-Adaptive Messaging

*Connected to buyer psychology: each audience segment needs different messaging, proof, objection handling, and flow logic.*

### Fix: Add to `draft-content/SKILL.md`

After the Messaging Hierarchy section, add "Audience-Adaptive Messaging":

```
The messaging hierarchy (why care → what → why this brand → CTA) stays the same. 
The CONTENT of each layer changes based on who you're talking to — and the shift 
goes deeper than swapping the hook.

For each audience segment, adapt ALL FOUR LAYERS:

### Primary Buyer (self-purchase)
- **Why care**: Their pain point or aspiration, in their language. They have the problem.
- **What is it**: Product details at THEIR depth. Technical buyer → specs. 
  Aspirational buyer → outcomes and sensory language.
- **Why this brand**: Proof that matches their TRUST HIERARCHY. If they trust peer 
  reviews → lead with reviews. If they trust data → lead with test results. 
  If they trust creators → lead with UGC.
- **CTA**: Direct. "Shop now." They know what they want.

### Gift-Giver
- **Why care**: THEIR frustration — "impossible to shop for." They don't have the 
  recipient's problem. They have a gifting problem.
- **What is it**: PLAIN LANGUAGE. Not specs. "Keeps their water from freezing on the 
  mountain." The gift-giver doesn't know what Thinsulate is and doesn't need to.
- **Why this brand**: Social proof from OTHER GIFT-GIVERS. "Got one for every skier 
  in my family." Best-seller status. "The gift they didn't know they needed." 
  Price as a signal of thoughtfulness, not value.
- **CTA**: Guide them. "Shop the gift guide" or "Gifts under $50" — don't assume 
  they know which product to buy.
- **Risk reduction**: Return policy, gift receipt, arrival guarantee prominently placed. 
  Gift-givers fear social embarrassment more than wasting money.

### VIP / Repeat Buyer
- **Why care**: What's NEW. They don't need re-selling on the brand.
- **What is it**: The new product, feature, or access they don't have yet.
- **Why this brand**: Loyalty recognition. Insider status. "You were one of our first."
- **CTA**: Exclusive. "Shop early access." "Get yours first."
- **Warning**: Do NOT send VIPs discount-led messaging. They bought at full price. 
  Discounts devalue their decision. Reward with ACCESS, not price cuts.

### Lapsed / Win-Back
- **Why care**: What's CHANGED since they left. New products, improvements, recognition.
- **What is it**: The specific new thing that gives them a reason to return.
  For durable goods: "You bought X. Now meet Y." (new product cross-sell)
  For consumable: "It's been [X] days. Time to restock?" (replenishment)
  For seasonal: "Season is back. Here's what's new." (seasonal trigger)
- **Why this brand**: Don't grovel. Don't say "we miss you" for a performance gear brand — 
  it sounds needy and off-brand. Instead, lead with the product and let it speak.
- **CTA**: Low-pressure. "See what's new." Not "COME BACK — here's 20% off."

### New-to-Brand / Cold Prospect
- **Why care**: The PROBLEM, not the product. They don't know you exist. 
  Start with what they already feel.
- **What is it**: Simple, clear, fast. One product, one benefit. Don't overwhelm.
- **Why this brand**: For researched buyers → data and reviews. For social buyers → 
  creator endorsement and volume ("50,000 customers"). For skeptics → guarantee/trial.
- **CTA**: Low commitment first. "Learn more" or "See how it works" before "Buy now."
  For category-creating products: education before transaction.
```

This replaces the original Theme B "Audience-Specific Messaging" section — it's deeper because it grounds each adaptation in WHY the psychology differs, not just WHAT to change.

### Fix: Add to `campaign-plan/SKILL.md`

Under Target Audience, add:

```
### Audience Psychology and Channel Implications

Each audience segment has different psychology that affects channel allocation, 
offer strategy, and content approach:

**Research-driven buyer** (common in durable goods, technical, high-ticket):
- Channels: SEO/content (buying guides, comparisons), YouTube reviews, Reddit, 
  long-form blog. These buyers are actively researching before purchase.
- Offer strategy: Free shipping and bundles over discounts. They buy on merit. 
  Discounts actually raise suspicion ("why is it cheap?").
- Content: Specs, test data, peer reviews, comparison to alternatives.
- Retargeting: Serve review content and comparison data, not urgency-based ads.

**Social/aspirational buyer** (common in beauty, fashion, wellness):
- Channels: Instagram, TikTok, creator partnerships. Discovery-driven.
- Offer strategy: GWP, limited editions, seasonal bundles. They respond to 
  exclusivity and aspiration, not just savings.
- Content: Before/after, UGC, lifestyle imagery, creator endorsements.
- Retargeting: Social proof ads — "10,000 people bought this month."

**Gift-giver** (cross-category, seasonal):
- Channels: Google Shopping ("gifts for [person]"), Pinterest (gift guides), 
  Instagram (product-in-use showing gift appeal). 
  NOT Reddit, NOT deep content. They want curation, not research.
- Offer strategy: Gift-wrapping, bundles at price tiers, free shipping, 
  arrival guarantee. The offer is the SERVICE (easy gifting), not the discount.
- Content: Gift guides by price tier, "for the person who [trait]" framing, 
  reviews from other gift-givers.
- Timing: Nov 15 - Dec 20 (holiday), late Jan (Valentine's), late Apr (Mother's Day), 
  late May (Father's Day). Front-load content before peak.
```

### Fix: Add to `email-sequence/SKILL.md`

Under the flow diagram section, add guidance on adapting flows by buyer psychology:

```
### Adapting Flow Logic by Buyer Psychology

The same trigger (e.g., cart abandonment) requires different recovery strategy 
depending on buyer psychology. Check `brand/customers.md` for buyer psychology 
before designing the flow.

**Abandoned Cart — by buyer type:**

| Buyer Psychology | Recovery Strategy | Message Focus | Incentive |
|-----------------|-------------------|---------------|-----------|
| Researched (durable, technical) | Provide proof — they're deciding, not distracted | Comparison data, peer reviews, FAQ, "here's why others chose this" | Last resort. Free shipping before %. |
| Impulse (beauty, fashion) | Quick reminder — they were distracted | "Still thinking about it?" + social proof + urgency | Earlier in sequence. GWP or free shipping. |
| Gift-giver | Reassure — they're uncertain about the gift | "Best-seller," return policy, arrival date, reviews from other gift-givers | Gift-wrapping or free shipping. |
| High-ticket ($200+) | Consultative — address specific objections | Warranty, customer service availability, detailed reviews, payment plan | Financing or bundle value, not %. |

**Win-Back — by product type:**

| Product Type | Win-Back Trigger | Win-Back Message |
|-------------|-----------------|-----------------|
| Consumable | X days past expected replenishment | "Running low? Time to restock." Rational, convenience-focused. |
| Durable | New product launch or new season | "You bought X. Meet Y." Product-focused, not relationship-focused. |
| Fashion | New collection or seasonal shift | "New arrivals — your style, updated." Identity-focused. |
| Seasonal | Approaching peak season | "Season is back. Here's what's new." Contextual. |

**Post-Purchase — by psychology:**

| Buyer Psychology | Post-Purchase Focus | Avoid |
|-----------------|--------------------| ------|
| Researched / skeptical | Prove they made the right call. Usage tips, care instructions, field data. "Here's how to get the most out of it." | Over-communicating. Respect their intelligence. |
| Social / enthusiast | Celebrate with them. Community, UGC request, "show us your [product]." | Being transactional too fast. Build relationship before cross-sell. |
| Gift-giver | Confirmation that the gift will be loved. Tracking, unboxing preview. Then: pivot to making THEM a customer. | Sending product-usage emails to someone who gifted it — they don't have the product. |
```

### Fix: Add to `brand-review/SKILL.md`

Under "Messaging and Positioning" review criteria, add:

```
#### Proof-to-Psychology Match
- Does the content use the right TYPE of proof for the stated audience?
  - Research-driven buyer → data, specs, test results, peer reviews
  - Social buyer → UGC, creator endorsements, before/after, volume ("10K customers")
  - Gift-giver → best-seller status, reviews from other gift-givers, price-as-thoughtfulness
- If the buyer needs data and the copy provides vibes, flag it as Medium severity: 
  "Proof type doesn't match buyer psychology."
- If the buyer needs social proof and the copy provides only specs, flag it similarly.
```

### Fix: Add to `content-creation/SKILL.md`

Under Writing Best Practices, add:

```
### Matching Brand Energy
Not every DTC brand is warm and enthusiastic. Match the brand's energy level 
from brand/voice.md:
- **Technical / understated**: Specs are the story. Confidence, not excitement. 
  Periods, not exclamation marks. Let performance data carry the message.
- **Warm / community**: Personal, encouraging, celebratory. Emoji OK. 
  Exclamation marks sparingly.
- **Bold / disruptive**: Punchy, opinionated, high-energy. Short sentences. 
  Strong POV.
- **Luxe / elevated**: Refined, aspirational, measured. White space in copy. 
  Fewer words, more weight per word.

If brand/voice.md specifies "understated" or "technical," dial down enthusiasm. 
If it specifies "warm" or "bold," the default DTC tone is closer to correct.
```

Also add TikTok refinement: "For technical/performance brands, prioritize original audio or field ambience over trending sounds when trending audio would undermine credibility."

---

## Layer 3: Category Position & Market Context

*Connected to buyer psychology: a category-creating product means the buyer is problem-aware but solution-unaware. This changes everything about how you sell.*

### The buyer psychology connection

| Category Position | Buyer Awareness | Marketing Implication |
|------------------|----------------|----------------------|
| Established leader | Knows the product, knows you | Defend. Loyalty, retention, brand premium. |
| Challenger in established category | Knows the product, doesn't know you | Differentiate. Why us, not them. |
| Category creator | Knows the PROBLEM, doesn't know the SOLUTION exists | Educate. Pain recognition → solution introduction → product. |
| New entrant, no awareness | Doesn't know the problem or the solution | Build awareness. This is brand advertising, not DTC performance. |

Tern is a category creator. Nobody searches for "bottle parka." They search for "water bottle freezing while hiking." The ENTIRE funnel starts with problem education.

### Fix: Add to `competitive-brief/SKILL.md`

After Research Process:

```
### Category Position Analysis

Before analyzing competitors, determine the brand's category position:

1. **Established category with direct competitors** → standard competitive analysis
2. **Established category, new entrant** → focus on differentiation and positioning gaps
3. **Category creator (no direct competitor)** → analyze SUBSTITUTES AND WORKAROUNDS

If category creator:
- **Identify substitute solutions**: What does the customer currently do? 
  (Anti-fog sprays, insulated bottles, putting phone inside jacket.) These ARE the competition.
- **Analyze workaround friction**: How annoying is the status quo? High friction = easier sell.
- **Map adjacent competitors**: Brands in neighboring categories that could enter yours.
- **Category naming**: What should this category be called? The brand that names it, owns it.
- **Education-first positioning**: "We're not a better [existing thing]. We're a new solution 
  to [specific problem]."

Replace the standard Messaging Comparison Matrix with a **Solution Comparison**:

| Dimension | Current Workaround | Your Product |
|-----------|--------------------|-------------|
| Effectiveness | | |
| Convenience | | |
| Cost (total, including replacement) | | |
| Reliability | | |
```

### Fix: Add to `seo-audit/SKILL.md`

After DTC-Specific Keyword Patterns:

```
### Novel Product / Category-Creating Keyword Strategy

If the product name has no search volume:

1. **Target the problem**: "Water bottle freezing while skiing" has volume. "Bottle parka" doesn't.
2. **Target the current workaround**: "Best insulated water bottle sleeve" captures people 
   searching for the closest existing solution.
3. **Target [activity] + [problem]**: "Winter hiking hydration", "phone dying in cold weather."
4. **Build category content**: "Why your water bottle freezes at altitude" — educate about the 
   problem, position your product as the solution.
5. **Own your terms**: Even with no volume now, create definitive content for your product 
   name so you rank for it as the category grows.

The buyer is problem-aware but solution-unaware. SEO strategy must start at the 
problem, not the product.
```

### Fix: Add to `draft-content/SKILL.md`

After the 5 ad frameworks:

```
### Framework Prioritization

Not all 5 frameworks perform equally. Prioritize based on product type and buyer psychology:

| Context | Test First | Test Second | Lower Priority |
|---------|-----------|-------------|----------------|
| Performance / technical product | Before/After, Problem-Agitate-Solve | UGC Testimonial | Founder Story |
| Beauty / skincare | UGC Testimonial, Before/After | Problem-Agitate-Solve | "3 Reasons Why" |
| Food / beverage | UGC Testimonial, Founder Story | "3 Reasons Why" | Before/After |
| Fashion / apparel | UGC Testimonial, Before/After (styling) | Founder Story | Problem-Agitate-Solve |
| Category-creating / novel | Problem-Agitate-Solve, Founder Story | Before/After | UGC (limited early reviews) |
| Gift-giver audience | UGC from other gift-givers, "3 Reasons Why" | Before/After (recipient reaction) | Problem-Agitate-Solve (gift-giver doesn't have the problem) |

Category-creating products: Problem-Agitate-Solve is king because the buyer needs 
to recognize the PROBLEM before they can want the solution. "Your water bottle 
freezes at 10,000ft" educates and sells simultaneously.
```

---

## Layer 4: Promo Psychology & Safety

*Connected to buyer psychology: promo responses are psychological, not just economic.*

### Fix: Add to `email-sequence/SKILL.md`

Under suppression rules:

```
### Promo Psychology Rules

These aren't just operational — they're about buyer psychology:

**Buyer's remorse protection:** If a promo follows a full-price period, suppress 
discount offers from customers who purchased at full price within the last 14 days. 
Why: A customer who paid $34 for The Bottle Parka anchored to that price as "fair." 
Seeing it for $28 ten days later reframes their purchase as a mistake. They don't 
feel smart — they feel cheated. Next time, they'll wait for the sale. You've 
permanently downgraded a full-price buyer into a discount-seeker.

**Discount escalation trap:** If a customer received a discount offer in the last 
7 days from ANY flow, do not send a deeper discount from this flow. 
Why: Escalating discounts teaches the buyer a pattern — "if I wait, the deal gets 
better." This is Pavlovian. Once trained, it's nearly impossible to untrain. The 
customer will ALWAYS wait for the deeper discount.

**VIP discount paradox:** VIPs should receive ACCESS (early access, exclusive products) 
not DISCOUNTS. Why: VIPs already buy at full price. A discount says "we think you 
need convincing" — it undermines the relationship. Give them status instead.

**Post-promo quiet period:** After a tentpole promo (BFCM, anniversary sale), 
insert a 7-14 day quiet period with no promotional emails. 
Why: Immediately following a promo with another promo trains the "there's always 
a deal" mentality. The quiet period re-establishes full-price as the norm.
```

---

## Implementation Order

1. **`brand/customers.md`** — add Buyer Psychology section to template + update Glow Lab example
2. **`brand/products.md`** — add Product Profile section, rename materials field, add margin field
3. **`skills/email-sequence/SKILL.md`** — flow applicability matrix, buyer-psychology-adapted flows, promo psychology rules (Layers 1 + 2 + 4)
4. **`skills/draft-content/SKILL.md`** — audience-adaptive messaging, framework prioritization (Layer 2 + 3)
5. **`skills/campaign-plan/SKILL.md`** — product-type offer hierarchy, audience psychology + channels, off-season campaigns, seasonal templates (Layers 1 + 2)
6. **`skills/content-creation/SKILL.md`** — brand energy matching, TikTok refinement (Layer 2)
7. **`skills/competitive-brief/SKILL.md`** — category position analysis (Layer 3)
8. **`skills/seo-audit/SKILL.md`** — novel product keyword strategy (Layer 3)
9. **`skills/performance-report/SKILL.md`** — seasonal adjustments, no-baseline protocol, cohort segmentation by psychology (Layers 1 + 2)
10. **`skills/brand-review/SKILL.md`** — proof-to-psychology match check (Layer 2)

**Total: 10 files** (was 8, added brand-review and customers.md updates)

---

## Findings Coverage

| Finding | Theme | Resolved By |
|---------|-------|-------------|
| F1 (product template beauty bias) | Layer 1 | products.md rename |
| F2 (no margin field) | Layer 1 | products.md addition |
| F3 (no sport-season template) | Layer 1 | campaign-plan seasonal addition |
| F4 (budget by niche) | Layer 1 | campaign-plan note |
| F5 (framework prioritization) | Layer 3 | draft-content prioritization table |
| F6 (gift-giver ad adaptation) | Layer 2 | draft-content audience-adaptive messaging |
| F7 (trending audio for tech brands) | Layer 2 | content-creation TikTok refinement |
| F8 (replenishment for non-consumable) | Layer 1 | email-sequence flow applicability |
| F9 (buyer's remorse suppression) | Layer 4 | email-sequence promo psychology |
| F10 (post-purchase assumes consumable) | Layer 1 | email-sequence post-purchase adaptation |
| F11 (non-subscription DTC guidance) | Layer 1 | products.md + all skills |
| F12 (gift-giver framework) | Layer 2 | campaign-plan + draft-content |
| F13 (seasonal business patterns) | Layer 1 | campaign-plan + performance-report |
| F14 (energy-level matching) | Layer 2 | content-creation brand energy |
| F15 (single-SKU offer hierarchy) | Layer 1 | campaign-plan product-type hierarchy |
| F16 (off-season campaigns) | Layer 1 | campaign-plan off-season type |
| F17 (audience messaging adaptation) | Layer 2 | draft-content audience-adaptive section |
| F18 (post-purchase consumable assumption) | Layer 1 + 2 | email-sequence with psychology-adapted post-purchase |
| F19 (flow skip/applicability) | Layer 1 | email-sequence flow applicability matrix |
| F20 (no-baseline reporting) | Layer 1 | performance-report new brand protocol |
| F21 (no category creation analysis) | Layer 3 | competitive-brief category position |
| F22 (novel product SEO) | Layer 3 | seo-audit problem-based keywords |

**All 22 findings resolved.**

---

## Verification

Re-run failing unit tests after implementation:

| Test | Skill | Target Score | Key Check |
|------|-------|-------------|-----------|
| 2.2 Single-product brand | campaign-plan | 22+ | Compressed offer hierarchy used |
| 2.3 Off-season campaign | campaign-plan | 20+ | Off-season strategy recommended, not standard promo |
| 2.4 Gift-giver audience | draft-content | 22+ | All 4 messaging layers adapted for gift-giver psychology |
| 2.5 Non-consumable post-purchase | email-sequence | 22+ | Replenishment replaced with cross-sell/seasonal |
| 2.6 Full retention system | email-sequence | 20+ | Replenishment and birthday skipped, reasons stated |
| 2.7 No baseline data | performance-report | 20+ | Industry benchmarks used, baseline established |
| 2.8 No direct competitor | competitive-brief | 20+ | Substitute analysis used, category creation framed |
| 2.9 Novel product SEO | seo-audit | 22+ | Problem-based keywords prioritized |

Plus new regression check:
- [ ] Abandoned cart flow adapts by buyer psychology (researcher vs impulse vs gift-giver)
- [ ] Post-purchase flow adapts by product type (consumable vs durable)
- [ ] Ad framework prioritization matches product type
- [ ] Brand energy level matched (technical brand doesn't get enthusiastic copy)
- [ ] Gift-giver gets DIFFERENT proof strategy than primary buyer, not just different hooks
