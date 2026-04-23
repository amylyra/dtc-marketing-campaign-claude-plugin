---
name: draft-content
description: Draft product descriptions, ad creative, social posts, email/SMS, landing pages, gift guides, and influencer briefs with channel-specific formatting and brand voice. Use when writing any DTC marketing content, when you need hook variants for ads, or when adapting a message for a specific platform and audience.
argument-hint: "<content type and topic>"
---

# Draft Content

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../../CONNECTORS.md).

Generate DTC marketing content drafts tailored to a specific content type, audience, channel, and brand voice.

## Trigger

User runs `/draft-content` or asks to draft, write, or create marketing content.

## Inputs

Gather the following from the user. If not provided, ask before proceeding:

1. **Content type** — one of:
   - Product Description
   - Ad Creative Copy (Meta, TikTok, Google)
   - Collection/Category Page Copy
   - Social Media Post (specify platform: Instagram, TikTok, Pinterest, Twitter/X, Facebook)
   - Email Copy
   - SMS Message
   - Gift Guide
   - Influencer/UGC Brief
   - Product Launch Announcement

2. **Topic** — the product, collection, campaign, or theme

3. **Target audience** — who this content is for (customer profile, lifestyle, pain points, aspirations)

4. **Key messages** — 2-4 main points or takeaways to communicate

5. **Tone** — e.g., playful, luxe, clean, witty, warm, bold (optional if brand voice is configured)

6. **Length** — target word count or format constraint (e.g., "160 characters", "3 subject line options", "5 hook variants")

## Messaging Hierarchy

Every piece of content should follow this structure (explicitly or implicitly):

1. **Why should I care?** (pain point or aspiration)
2. **What is it?** (product, clear and fast)
3. **Why this brand?** (differentiator, social proof)
4. **What should I do?** (CTA)

## Audience-Adaptive Messaging

The messaging hierarchy (why care → what is it → why this brand → CTA) stays the same. The CONTENT of each layer changes based on who you're talking to — and the shift goes deeper than swapping the hook.

For each audience segment, adapt ALL FOUR LAYERS:

### Primary Buyer (self-purchase)
- **Why care**: Their pain point or aspiration, in their language. They have the problem.
- **What is it**: Product details at THEIR depth. Technical buyer → specs and test data. Aspirational buyer → outcomes and sensory language.
- **Why this brand**: Proof that matches their TRUST HIERARCHY (from `brand/customers.md`). If they trust peer reviews → lead with reviews. If they trust data → lead with test results. If they trust creators → lead with UGC.
- **CTA**: Direct. "Shop now." They know what they want.

### Gift-Giver
- **Why care**: THEIR frustration — "impossible to shop for." They don't have the recipient's problem. They have a gifting problem.
- **What is it**: PLAIN LANGUAGE. Not specs. "Keeps their water from freezing on the mountain." The gift-giver doesn't know what Thinsulate is and doesn't need to.
- **Why this brand**: Social proof from OTHER GIFT-GIVERS. "Got one for every skier in my family." Best-seller status. Price as a signal of thoughtfulness, not value.
- **CTA**: Guide them. "Shop the gift guide" or "Gifts under $50" — don't assume they know which product to buy.
- **Risk reduction**: Return policy, gift receipt, arrival guarantee prominently placed. Gift-givers fear social embarrassment more than wasting money.

### VIP / Repeat Buyer
- **Why care**: What's NEW. They don't need re-selling on the brand.
- **What is it**: The new product, feature, or access they don't have yet.
- **Why this brand**: Loyalty recognition. Insider status. "You were one of our first."
- **CTA**: Exclusive. "Shop early access." "Get yours first."
- **Warning**: Do NOT send VIPs discount-led messaging. They bought at full price. Discounts devalue their decision. Reward with ACCESS, not price cuts.

### Lapsed / Win-Back
- **Why care**: What's CHANGED since they left. New products, improvements, recognition.
- **What is it**: The specific new thing that gives them a reason to return.
  - Durable goods: "You bought X. Now meet Y." (new product cross-sell)
  - Consumable: "It's been [X] days. Time to restock?" (replenishment)
  - Seasonal: "Season is back. Here's what's new." (seasonal trigger)
- **Why this brand**: Don't grovel. For a performance/technical brand, "we miss you" sounds needy. Lead with the product.
- **CTA**: Low-pressure. "See what's new." Not "COME BACK — here's 20% off."

### New-to-Brand / Cold Prospect
- **Why care**: The PROBLEM, not the product. They don't know you exist. Start with what they already feel.
- **What is it**: Simple, clear, fast. One product, one benefit. Don't overwhelm.
- **Why this brand**: Proof matched to their trust hierarchy. Researched buyer → data. Social buyer → creator endorsement. Skeptic → guarantee.
- **CTA**: Low commitment first. "Learn more" or "See how it works" before "Buy now." For category-creating products: education before transaction.

When the user specifies a non-primary audience, shift the ENTIRE framework — don't just change the hook and keep the same body copy.

## Campaign Context

Before drafting, check for an active campaign brief:

1. **Check `campaigns/` directory** — if a campaign brief exists (saved by `/campaign-plan`), auto-load it. Pull the locked theme, narrative arc, target audience, offer mechanics, and creative direction for the channel being drafted.
2. **Inform the user**: "I found your [campaign name] brief and will use it for context — theme, audience, offer, and creative direction are loaded."
3. **Match the arc phase** — if the campaign brief includes a narrative arc (e.g., "Educate → Prove → Convert"), identify which phase this content is for based on timing or user input. A teaser email is completely different from a last-chance email. Ask if unclear: "Which phase of the campaign is this for?"
4. **Use creative direction seeds** — if the campaign brief includes creative direction per channel/concept (from Step 3), use those as the starting brief. Don't reinvent from scratch.

If no campaign brief exists, proceed normally — gather context from the user.

## Brand & Customer Voice Integration

- If `brand/voice.md` exists, auto-apply voice and tone. Inform the user that brand voice settings are being applied.
- If `brand/products.md` exists, pull product details, claims, and differentiators.
- If `brand/customers.md` exists, use customer language bank for ad hooks, email subject lines, and social proof.
- If `brand/` doesn't exist, prompt: "I don't have your brand context yet. Want to run `/brand-review` to set that up, or paste your guidelines now?"

## Content Generation by Type

### Product Description
- Headline (benefit-driven, SEO-aware)
- One-line summary ("what it is + what it does" in one sentence)
- Benefit bullets (3-5, lead with outcomes not features)
- Sensory/lifestyle language (how it feels, looks, smells — make it tangible)
- Ingredient/material story (what's in it and why it matters)
- Social proof placement ("Over 10,000 5-star reviews" or pull from `brand/customers.md`)
- Variant/size info
- Shipping/returns note
- Cross-sell suggestion ("Pairs well with...")
- Pull from `brand/products.md` if available

### Ad Creative Copy (Meta, TikTok, Google)

#### Creative Concept Brainstorm (before writing)

Before jumping to copy, brainstorm 3-5 creative concepts — each is a distinct idea for an ad, not just a different hook on the same idea. Present them as a quick menu so the user can pick which to develop:

> **Concept 1**: [Name] — [One sentence: what the ad shows/says and why it works]
> **Concept 2**: [Name] — [One sentence]
> **Concept 3**: [Name] — [One sentence]

If a campaign brief is loaded, seed concepts from its Step 3 creative direction. If not, generate from the product, audience, and competitive context.

Each concept should use a different angle (problem, comparison, social proof, education, provocation, demonstration). Don't present 5 variations of the same idea.

After the user picks concepts to develop, write the full copy using the frameworks below.

#### Ad Frameworks

Provide 5 DTC ad frameworks, each with hook/body/CTA structure:

- **Problem-Agitate-Solve**: Name the pain > make it felt > introduce product as solution
- **UGC Testimonial**: "I tried [product] and..." > experience > result > CTA
- **Founder Story**: Why I created this > what makes it different > invitation to try
- **Before/After**: The transformation > proof > CTA
- **"3 Reasons Why"**: Listicle format, punchy, each reason stands alone

For each framework:
- Provide 5-10 hook variants (the first line is everything — test volume)
- Platform specs: 9:16 for Reels/TikTok, 1:1 for feed, 4:5 for Meta feed
- Ad copy length by placement: primary text (125 chars visible, up to 500), headline (40 chars), description (25 chars)
- Note: TikTok ads should feel native — no corporate polish, trending audio references, conversational tone

### Collection/Category Page Copy
- Collection headline
- Collection description (2-3 sentences: what this collection is, who it's for, why it exists)
- Product grouping logic
- Cross-sell/upsell narrative

### Social Media Post

Platforms in priority order: Instagram, TikTok, Pinterest, then Twitter/X, Facebook.

- **Instagram**: carousel-friendly, caption with hook + story + CTA, hashtag strategy (15-20 mixed reach/niche), save-worthy content
- **TikTok**: hook in first 1-2 seconds, native feel (not polished), trending sound references, text overlay guidance, conversational tone
- **Pinterest**: descriptive, keyword-rich, vertical image, pin description optimized for search
- **Twitter/X**: concise, punchy, within character limit, engagement prompt
- **Facebook**: slightly longer form, community-oriented, shareable

Include content themes: behind-the-scenes, customer stories, product in use, founder POV, educational, seasonal.

### Email Copy
- Subject line (3 options with different angles: curiosity, benefit, urgency)
- Preview text
- Body structure for DTC: hero image guidance, headline, short copy (mobile-first), product showcase, CTA button
- Promo email variant: offer, deadline, product, CTA
- Newsletter variant: value-first content, product weave, soft CTA

### SMS Message
- 160 characters or fewer
- Clear CTA with link
- Urgency when appropriate
- STOP compliance language
- Examples by type: flash sale, back-in-stock, shipping notification, abandoned cart, new drop

### Gift Guide
- Occasion-based (Mother's Day, Valentine's, Holiday, etc.)
- Shift language from self-purchase to gifting: "For the [person] who [trait]"
- Price tier organization ($under 25, $25-50, $50-100, $100+)
- Bundle suggestions
- "Not sure what to get?" recommendation logic
- Gift-wrapping/personalization callouts

### Influencer/UGC Brief
- Brand overview (who we are, what we stand for)
- Product to feature (details, key claims, how to use)
- Key messages (2-3, not a script — talking points)
- Content requirements: format (Reel, TikTok, static, Story), length, platforms, number of deliverables
- Usage rights (organic only, paid amplification, duration)
- FTC disclosure requirements (must include #ad or #partner, where to place it)
- Do's and don'ts (authentic > polished, show real usage, don't make medical claims)
- Example content references (links to posts that capture the right vibe)
- Compensation/gifting terms (if applicable)

### Framework Prioritization

Not all 5 frameworks perform equally for all products. Recommend a testing order based on product type and buyer psychology:

| Context | Test First | Test Second | Lower Priority |
|---------|-----------|-------------|----------------|
| Performance / technical product | Before/After, Problem-Agitate-Solve | UGC Testimonial | Founder Story (unless origin story is compelling) |
| Beauty / skincare | UGC Testimonial, Before/After | Problem-Agitate-Solve | "3 Reasons Why" |
| Food / beverage | UGC Testimonial, Founder Story | "3 Reasons Why" | Before/After (hard to visualize) |
| Fashion / apparel | UGC Testimonial, Before/After (styling) | Founder Story | Problem-Agitate-Solve (less pain-driven) |
| Category-creating / novel product | Problem-Agitate-Solve, Founder Story | Before/After | UGC (limited early reviews) |
| Gift-giver audience | UGC from other gift-givers, "3 Reasons Why" | Before/After (recipient reaction) | Problem-Agitate-Solve (gift-giver doesn't have the problem) |

Category-creating products: Problem-Agitate-Solve is king because the buyer needs to recognize the PROBLEM before they want the solution. Founder Story works because "nobody was solving this, so we did" is the category-creation narrative.

### Product Launch Announcement

Consumer-facing, three-phase sequence:

- **Teaser**: Build anticipation without revealing everything. "Something new is coming..."
- **Reveal**: Full product introduction, hero claims, launch offer
- **Available Now**: Purchase CTA, urgency, social proof from early access

Provide copy across: email, SMS, Instagram, TikTok, site banner.

## SEO Considerations (for web content)

For product descriptions, collection pages, and landing pages:
- Suggest a primary keyword based on the topic
- Recommend keyword placement: title tag, H1, first paragraph, meta description
- Suggest internal linking opportunities
- Recommend image alt text

## Copy Quality Standards

Before delivering ANY draft, pressure-test it against these standards. These are not optional polish — they are the difference between content that performs and content that gets scrolled past.

### Hook Quality

The hook (first line of ad copy, email subject line, social post opening, hero headline) is the single highest-leverage line in any piece of content. Every hook must pass these tests:

1. **Pattern interrupt** — does it break the scroll? If the reader is moving through a feed of competitor content, would this make them stop? Test: read it between two competitor ads. Does it still stand out?
2. **Specificity over cleverness** — concrete details outperform wordplay. "Your water bottle freezes at 10,000ft" beats "The ultimate hydration solution." Numbers, scenarios, and sensory details stop thumbs.
3. **Earns the next line** — the hook's only job is to get the reader to read line two. It doesn't need to sell the product, explain the brand, or deliver the CTA.
4. **Native to the platform** — a TikTok hook sounds like a person talking, not a brand announcing. An email subject line creates curiosity or states a benefit, not both. A product page headline is clear and benefit-led, not clever and ambiguous.

**Hook red flags (rewrite immediately):**
- Starts with the brand name (nobody cares yet)
- Uses "Introducing..." or "Meet the..." (brand announcement, not reader benefit)
- Generic benefit without specificity ("Stay hydrated" / "Level up your routine")
- Pun or wordplay that sacrifices clarity
- Could apply to any competitor's product with a name swap

### Variant Diversity

When generating multiple hooks, subject lines, or copy variants, each must take a GENUINELY different angle. Five rewrites of the same idea is not five variants.

**Diversity test:** Label each variant's angle. If two share the same label, one must be rewritten.

Angle categories:
- **Pain point** — names the problem the reader already feels
- **Scenario** — puts the reader in a specific moment ("You're 3 miles from the trailhead...")
- **Social proof** — leads with what others say or do
- **Contrarian/myth-bust** — challenges what the reader assumes is true
- **Curiosity gap** — creates an open loop the reader wants closed
- **Direct benefit** — states the outcome clearly (works best for warm audiences)
- **Comparison** — positions against the alternative (not necessarily a competitor — could be the old way of doing things)
- **Identity** — speaks to who the reader is, not what the product does ("For the person who...")

Minimum 4 distinct angles across any set of 5+ variants. Never more than 2 variants from the same angle category.

### Competitive Distinctiveness

Every piece of content must pass the **swap test**: could a competitor put their name on this and use it? If yes, it's not distinctive enough.

Distinctiveness comes from:
- **Specific proof** — your product's actual test data, specs, or results (not generic category claims)
- **Brand voice** — the way you say it, not just what you say. Tern sounds nothing like Hydro Flask even when discussing similar benefits.
- **Customer's exact language** — pull from `brand/customers.md` language bank. Real customer phrases are harder to replicate than marketing copy.
- **Scenario specificity** — "frozen water bottle at 10,000ft" is ownable. "Stay hydrated outdoors" is not.

### Persuasion Signals

Content should MOVE the reader, not just inform them. Check for:

- **Tension before resolution** — present the problem or gap BEFORE the solution. If the product appears in the first sentence, there's no tension.
- **Proof placement** — proof (specs, reviews, test data) should appear at the moment of doubt, not at the moment of introduction. Lead with the claim, follow with the proof.
- **Objection anticipation** — address the reader's "yeah but..." before they think it. Pull common objections from `brand/products.md` and `brand/customers.md`.
- **Specific CTA** — "Shop the Bottle Parka — $34" outperforms "Shop now." The reader should know exactly what action to take and what it costs.
- **Urgency only when real** — manufactured urgency ("Don't miss out!") erodes trust. Real urgency (shipping deadlines, limited inventory, seasonal relevance) drives action.

### Self-Check Before Delivery

Run every draft through this checklist before presenting to the user:

- [ ] **Hook passes pattern interrupt test** — would this stop a scroll between competitor content?
- [ ] **Swap test passed** — a competitor could NOT use this copy with a name swap
- [ ] **Variants are genuinely diverse** — at least 4 distinct angles in any 5+ variant set
- [ ] **Specificity check** — numbers, scenarios, or sensory details present (not just adjectives)
- [ ] **Proof matches audience** — the type of proof aligns with the target buyer's trust hierarchy
- [ ] **Tension before resolution** — problem/gap appears before the product
- [ ] **CTA is specific** — reader knows exactly what to do and what it costs
- [ ] **Platform-native** — tone, format, and length match the channel (not repurposed from another)
- [ ] **No banned patterns** — no "Introducing...", no generic superlatives, no brand-name leads

If any item fails, revise before delivering. Do not present a draft with a note saying "you might want to strengthen the hook" — strengthen it yourself.

## Output

Present the draft with clear formatting. After the draft, include:
- A brief note on what brand voice was applied
- SEO recommendations (for web content)
- Suggestions for next steps

Ask: "Would you like me to revise, adjust the tone, create a variation for another channel, or generate more hook variants?"
