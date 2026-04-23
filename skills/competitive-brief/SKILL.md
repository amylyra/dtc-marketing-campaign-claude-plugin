---
name: competitive-brief
description: Research DTC competitors and generate a comparison of ad creative, pricing, influencer strategy, storefront UX, and social presence — with actionable positioning gaps. Use when building competitive positioning, analyzing a competitor's promo strategy, or scoping the landscape before a campaign.
argument-hint: "<competitor or market segment>"
---

# Competitive Brief

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../../CONNECTORS.md).

Research DTC competitors and generate a structured competitive analysis comparing brand positioning, ad creative, pricing, influencer strategy, storefront UX, and social presence.

## Trigger

User runs `/competitive-brief` or asks for a competitive analysis, competitor research, or market comparison.

## Inputs

Gather the following from the user:

1. **Competitor name(s)** — one or more competitors to analyze (required)

2. **Your brand context** (optional but recommended):
   - What you sell and to whom
   - Your positioning or value proposition
   - Key differentiators you want to highlight

3. **Focus areas** (optional — if not specified, cover all):
   - Brand positioning and messaging
   - Storefront and product page teardown
   - Ad creative analysis
   - Social media presence
   - Influencer and UGC strategy
   - Pricing and promo strategy
   - Content and SEO gaps

### Brand Context

If `brand/` directory exists, auto-apply:
- **`brand/products.md`** — compare competitor products against your own by name, price, and positioning. Include your brand's column in the messaging comparison matrix.
- **`brand/customers.md`** — evaluate whether competitors are targeting the same customer segments or different ones. Note overlapping vs. underserved audiences.
- **`brand/voice.md`** — compare competitor brand voice and tone against your own. Identify where your voice is distinct vs. where it blends in.

If `brand/` doesn't exist, run the competitive brief without your brand's column in comparison matrices. Note: "For a side-by-side comparison, run `/brand-review setup` first to document your brand's positioning."

## Research Process

For each competitor, research using web search:

1. **Website** — homepage messaging, product pages (PDP), collection pages, pricing, about page, reviews page
2. **Social media** — Instagram (grid, Stories, Reels), TikTok (organic content, trends), Pinterest
3. **Email/SMS** — sign up for their list, analyze welcome flow, promo frequency, offer depth
4. **Ad library** — Meta Ad Library, TikTok Creative Center — current and recent ad creative
5. **Product** — order the product, evaluate unboxing, packaging, inserts, post-purchase experience

### Research Sources

Gather intelligence from these categories of sources:

#### Primary Sources (Direct from Competitor)
- **Website**: homepage, product pages (PDP), collection pages, pricing, about page, reviews page
- **Social media**: Instagram (grid, Stories, Reels), TikTok (organic content, trends), Pinterest
- **Email/SMS**: sign up for their list, analyze welcome flow, promo frequency, offer depth
- **Ad library**: Meta Ad Library, TikTok Creative Center — current and recent ad creative
- **Product**: order the product, evaluate unboxing, packaging, inserts, post-purchase experience

#### Secondary Sources (Third-Party)
- **Review sites**: Amazon reviews (if sold there), Trustpilot, brand's own site reviews — customer sentiment themes
- **"Best of" listicles**: Google "[category] best [product type]" — who appears, who's missing
- **Influencer analysis**: Which creators feature their products? What tier (nano/micro/macro)? What platforms?
- **SEO tools**: Keyword rankings, organic traffic estimates, content gaps (Ahrefs/Similarweb if connected)
- **Social listening**: Reddit, TikTok comments, brand mention sentiment
- **Pricing intelligence**: Current prices, promo frequency, offer types, subscription models

### Research Cadence
- **Deep competitive analysis**: quarterly (full research across all sources)
- **Competitive monitoring**: monthly (scan for new ads, promos, content, messaging changes)
- **Real-time alerts**: ongoing (set up alerts for competitor brand mentions, new ads, promo launches)

## Category Position Analysis

Before analyzing competitors, determine the brand's category position. This changes what "competition" means and how the entire brief should be framed.

1. **Established category with direct competitors** → standard competitive analysis (proceed to Competitive Brief Structure below)
2. **Established category, new entrant** → focus on differentiation and positioning gaps against incumbents
3. **Category creator (no direct competitor)** → analyze SUBSTITUTES AND WORKAROUNDS, not head-to-head competitors

### Category Creator Analysis

If the brand is creating a new category (the product name has no search volume, customers don't know the solution exists):

- **Identify substitute solutions**: What does the customer currently do instead? (e.g., insulated bottles, anti-fog sprays, stuffing a phone inside a jacket pocket.) These substitutes ARE the competition — even though they're not the same product.
- **Analyze workaround friction**: How annoying, unreliable, or inadequate is the status quo? High friction = easier sell. Low friction = harder to justify the switch.
- **Map adjacent competitors**: Brands in neighboring categories that could enter yours. If your product succeeds, who has the manufacturing, audience, or distribution to copy it?
- **Category naming**: What should this category be called? The brand that names the category owns it. Analyze whether a clear, searchable category name exists, or whether the brand needs to create one.
- **Education-first positioning**: "We're not a better [existing thing]. We're a new solution to [specific problem]." Frame the competitor section around the problem the buyer faces, not the product they'd compare against.

### Solution Comparison Matrix (for Category Creators)

Replace the standard Messaging Comparison Matrix with a Solution Comparison when the brand has no direct competitors:

| Dimension | Current Workaround A | Current Workaround B | Your Product |
|-----------|---------------------|---------------------|-------------|
| Effectiveness | | | |
| Convenience | | | |
| Cost (total, including replacement/ongoing) | | | |
| Reliability | | | |
| Learning curve | | | |
| Social proof availability | | | |

This comparison educates the buyer: "Here's what you're doing now. Here's why it doesn't work. Here's what does."

## Competitive Brief Structure

### 1. Executive Summary
- 2-3 sentence landscape overview
- Biggest positioning opportunity
- Biggest competitive threat

### 2. Competitor Profiles

For each competitor:

#### Brand & Positioning
- What they sell (one sentence)
- Target customer
- Brand aesthetic and vibe (visual identity, photography style, packaging feel)
- Pricing tier (budget / mid / premium / luxury) and price range
- Core value proposition

#### Storefront Teardown
- Homepage: hero messaging, offer placement, navigation structure
- Product pages: copy quality, social proof placement, photography, cross-sell strategy
- Collection pages: organization, filtering, merchandising logic
- Cart/checkout: friction points, upsell/cross-sell, trust signals
- Mobile experience quality

#### Ad Creative Analysis
- Active ad count and estimated spend level (if visible)
- Primary creative formats (UGC, polished, lifestyle, product-focused)
- Hook themes (what pain points or aspirations they lead with)
- Offer strategy in ads (discount-led vs value-led vs social-proof-led)
- Strongest performing concepts (longest-running ads = likely winners)

#### Social Presence
- Instagram: followers, engagement rate, content themes, posting frequency, Reels usage
- TikTok: followers, engagement, content style (UGC, founder-led, educational, trend-riding)
- Pinterest: presence, pin strategy, search visibility
- Overall content quality and consistency

#### Influencer/UGC Strategy
- Creator tier: nano (<10K), micro (10-100K), macro (100K+), celebrity
- Content style: authentic reviews, tutorials, unboxing, lifestyle integration
- Volume: how many creators are posting about them
- Platforms used
- Whether they use UGC in ads (repurposed creator content)

#### Pricing & Promo Strategy
- Price points across product line
- Promo frequency (how often do they discount?)
- Promo depth (typical discount: 10%? 20%? 30%+?)
- Promo mechanics (% off, GWP, bundles, free shipping, flash sales)
- Subscription offering (% off, skip/pause/cancel flexibility)
- Seasonal promo patterns (when do they go deep?)

#### Strengths
- What they do well
- Where their brand resonates

#### Weaknesses
- Gaps in their offering or experience
- Customer complaints (from reviews)
- Where they are vulnerable

### 3. Messaging Comparison Matrix

| Dimension | Your Brand | Competitor A | Competitor B |
|-----------|-----------|--------------|--------------|
| Tagline / hero message | | | |
| Target customer | | | |
| Price positioning | | | |
| Core differentiator | | | |
| Brand aesthetic | | | |
| Primary acquisition channel | | | |
| Promo intensity | | | |

(Include your brand only if the user provided their positioning context)

### 4. Content & SEO Gap Analysis
- Topics/keywords they rank for that you don't
- Content formats they use that you could adopt
- Social content themes working for them
- Opportunities they've missed (keywords, formats, platforms)

### 5. Promo Intelligence
- Competitive promo calendar: when competitors discount, how deep, what mechanics
- How this should inform your own promo calendar (don't compete head-to-head on discounts against brands that go deeper — differentiate on mechanics or timing)
- Subscription model comparison

### 6. Opportunities
- Positioning gaps you can exploit
- Audience segments they are underserving
- Content or channel opportunities
- Price/value gaps

### 7. Threats
- Where competitors are strong and you are vulnerable
- Trends favoring their positioning
- Recent moves that could shift the market

### 8. Recommended Actions
- 3-5 specific, actionable recommendations based on the analysis
- Quick wins (things you can act on this week)
- Strategic moves (longer-term positioning, channel, or product investments)

## Analysis Frameworks

### Messaging Comparison Frameworks

#### Value Proposition Comparison

For each competitor, document:
- **Promise**: what they promise the customer will achieve
- **Evidence**: how they prove the promise (reviews, UGC, before/after, clinical data)
- **Mechanism**: how their product delivers on the promise (the "how it works")
- **Uniqueness**: what they claim only they can do

#### Narrative Analysis

Identify each competitor's story arc:
- **Villain**: what problem or enemy they position against (mainstream products, harmful ingredients, overpriced alternatives)
- **Hero**: who is the hero in their story (the customer? the founder? the community?)
- **Transformation**: what before/after do they promise?
- **Stakes**: what happens if you do not act?

This reveals positioning strategy and emotional appeals.

#### Messaging Strengths and Vulnerabilities

For each competitor's messaging, assess:
- **Clarity**: can a first-time visitor understand what they sell in 5 seconds?
- **Differentiation**: is their positioning distinct or generic?
- **Proof**: do they back up claims with evidence (reviews, UGC, data)?
- **Consistency**: is messaging consistent across site, ads, social, and email?
- **Resonance**: does their messaging address real customer pain points or desires?

### Content Gap Analysis Methodology

#### Content Audit Comparison

Map content across competitors by:

| Topic/Theme | Your Content | Competitor A | Competitor B | Gap? |
|-------------|-------------|--------------|--------------|------|
| [Topic 1] | Blog post, email series | Blog, TikTok series | Nothing | Opportunity for B |
| [Topic 2] | Nothing | Instagram Reels | Blog post, Pinterest | Gap for you |
| [Topic 3] | UGC gallery | Nothing | UGC gallery | Parity |

#### Content Type Coverage

| Content Format | You | Comp A | Comp B | Comp C |
|----------------|-----|--------|--------|--------|
| Blog posts | Y | Y | Y | Y |
| Email flows | Y | Y | N | Y |
| Instagram Reels | N | Y | Y | N |
| TikTok content | Y | Y | Y | N |
| Pinterest pins | N | N | Y | N |
| Video content (YouTube) | N | Y | Y | Y |
| Quizzes/interactive tools | N | N | N | Y |
| UGC/creator content | Y | N | Y | N |

#### Identifying Content Opportunities
1. **Topics they cover that you do not**: potential gaps in your content strategy
2. **Topics you cover that they do not**: potential differentiators to amplify
3. **Formats they use that you do not**: format gaps that could reach new audiences
4. **Audience segments they address that you do not**: underserved audiences
5. **Search terms they rank for that you do not**: SEO content gaps

#### Content Quality Assessment
- Depth: surface-level or comprehensive?
- Freshness: regularly updated or stale?
- Engagement: do posts get comments, shares, saves?
- Production value: low-fi/authentic or high-production?
- Originality: unique perspective or rehashed content?

### Positioning Strategy

#### Positioning Statement Framework

For your brand and each competitor, define (or reverse-engineer) their positioning statement:

> For [target customer], [brand] is the [category] that [key benefit/differentiator] because [reason to believe].

Example:
> For health-conscious millennials, Acme is the daily supplement that simplifies your routine into one scoop because it combines 30 whole-food ingredients backed by third-party testing.

#### Positioning Map

Plot competitors on a 2x2 matrix using the two most important dimensions for your market:

Common axis pairs for DTC:
- **Price vs. Quality** (affordable / basic vs. premium / high-quality)
- **Mass vs. Niche** (broad appeal / everyone vs. specific audience / curated)
- **Clinical vs. Natural** (science-backed / clinical vs. organic / holistic)
- **Trendy vs. Timeless** (trend-driven / viral vs. classic / enduring)

Identify which quadrant is underserved or where your differentiation is strongest.

#### Category Strategy
- **Create a new category**: if you do something genuinely different, define and own the category (high risk, high reward)
- **Reframe the existing category**: change how buyers evaluate the category to favor your strengths
- **Win the existing category**: compete directly on recognized criteria and out-execute
- **Niche within the category**: own a specific segment, use case, or audience

#### Positioning Pitfalls to Avoid
- Positioning against a competitor rather than for a customer need
- Claiming too many differentiators (pick 1-2 that matter most)
- Using industry jargon the customer does not use
- Positioning on ingredients or features rather than outcomes
- Changing positioning too frequently (confuses the customer)

## Output

Present the full competitive brief with clear formatting. Note the date of the research so the user knows the freshness of the data.

**Save findings** to `research/competitive-[competitor-or-market].md` so other skills can auto-load them. Include: key competitors, positioning gaps, promo intelligence, ad creative patterns, and recommended actions.

Other skills use this file:
- `/campaign-plan` — loads competitive context for theme options (what competitors are doing, where the gaps are)
- `/draft-content` — loads competitive ad patterns for swap test and competitive distinctiveness
- `/brand-review` — checks content against competitive landscape

After the brief, ask:

"Would you like me to:
- Dive deeper into any competitor's ad creative or promo strategy?
- Build a positioning map for your market?
- Feed these insights into a `/campaign-plan`?
- Tear down a specific competitor's storefront in detail?"
