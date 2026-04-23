---
name: campaign-plan
description: Generate a campaign brief with promo economics, channel strategy, content calendar, and execution checklist. Use when planning a product launch, seasonal campaign, revenue push, or retention play — or when building your annual promo calendar.
argument-hint: "<campaign objective or product>"
---

# Campaign Plan

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../../CONNECTORS.md).

Generate a DTC campaign brief with promo economics, audience strategy, channel plan, content calendar, and execution checklist.

## Trigger

User runs `/campaign-plan` or asks to plan, design, or build a marketing campaign.

## Inputs

Gather the following from the user. If not provided, ask before proceeding:

1. **Campaign goal** — the primary objective (e.g., drive revenue, launch a product, increase AOV, reactivate lapsed customers, build brand awareness, grow subscriber base)

2. **Target audience** — who the campaign is aimed at (new customers, VIP/repeat buyers, lapsed customers, specific demographic or psychographic segment)

3. **Timeline** — campaign duration and any fixed dates (launch date, seasonal deadline, inventory availability window)

4. **Budget range** — approximate budget or budget tier (optional; if not provided, generate a channel-agnostic plan and note where budget allocation would matter)

5. **Competitors** (optional) — If provided, run a lightweight competitive scan inline (ad creative angles, pricing/offers, social presence, positioning) before building the brief. If a `/competitive-brief` already exists in conversation, pull from it. No hard gate — just an optional enrichment input.

6. **Brand context** — If a `brand/` directory exists, auto-apply product catalog and customer profiles. Reference products by name and price. If no `brand/` directory is found, prompt the user to set one up or paste key details (hero SKUs, price points, margin structure, brand voice).

7. **Additional context** (optional):
   - Product or collection being promoted
   - Key differentiators or value propositions
   - Previous campaign performance or learnings
   - Brand guidelines or constraints
   - Geographic focus

## Promo Calendar Framework

This is the operating system for DTC campaigns. Every campaign exists within a broader annual rhythm. Before building any individual brief, understand where it fits.

### Calendar Structure

- **Tentpoles (4-6/yr)**: Deep, strategic, pre-planned campaigns with the biggest offers and highest investment. Examples: BFCM, brand anniversary, one summer moment, one category-specific moment. These get full-funnel execution across every channel.
- **Mid-tier (6-10/yr)**: Moderate campaigns with varied mechanics. Examples: Friends & Family, VIP early access, gift-with-purchase events, threshold offers ("spend $X, get Y"). These test new offer types and keep momentum between tentpoles.
- **Always-on lifecycle**: Welcome series, replenishment reminders, winback flows, post-purchase sequences, review requests. This is infrastructure, not promo. It runs continuously in Klaviyo (or equivalent) and should never be turned off for a campaign.
- **No-promo zones (6-10 weeks/yr)**: Full-price selling periods. Non-negotiable. This is where you learn if the brand works without a crutch. Protect these windows ruthlessly — they are the health indicator.

### Offer Hierarchy

Always exhaust cheaper incentives before moving to deeper discounts. Work down this list:

1. Early access (time-based exclusivity, zero margin cost)
2. Loyalty/VIP perks (points multipliers, exclusive products)
3. Free shipping thresholds (increases AOV, partially self-funding)
4. Gift with purchase (moves secondary inventory, protects hero pricing)
5. Bundles (increases AOV, obscures per-unit discount)
6. % off secondary SKUs (protects hero product pricing power)
7. Sitewide % off (last resort — use only for tentpole moments)

The skill must ask: **"Why this offer instead of a cheaper incentive higher on the hierarchy?"** If the user cannot articulate why, recommend stepping up.

### Key Principles

- **Hero SKU protection**: Discount bundles and secondary SKUs, not the anchor product. Once the hero's discount price becomes the reference price in the customer's mind, pricing power is permanently lowered. This is irreversible.
- **Audience per promo**: New customers, VIP/repeat buyers, lapsed customers, and active subscribers each get different offers. Reserve the deepest discounts for existing customers (loyalty reward), not prospecting. Promo-acquired new customers have structurally worse LTV — they were trained to buy on discount from day one.
- **Pre-committed kill thresholds**: Define before launch — the conversion rate or margin level that triggers pulling the promo early. Write it down. Agree on it. Do not renegotiate mid-campaign.
- **Build backwards**: Annual margin target -> acceptable discount penetration -> tentpole discount depth -> mid-tier mechanics -> no-promo zones. The calendar serves the P&L, not the other way around.
- **Discount penetration guardrails**: 15-25% of revenue sold on discount is healthy. Above 35% is a structural problem — the brand is training customers to wait. Track full-price velocity between promos as a leading health indicator.

## Offer Hierarchy by Product Type

The main offer hierarchy above assumes multiple SKUs and a standard DTC product line. Adapt based on `brand/products.md` product profile:

**Single-SKU brand:** The hero product IS the only product. Hierarchy compresses to: early access → free shipping → multi-unit discount (buy 2+, gift-giving play) → modest % off (last resort, tentpole only). Bundles and "% off secondary SKUs" don't apply.

**Durable goods (non-consumable):** No replenishment lever for retention. Retention strategy = new product launches + seasonal re-engagement + cross-sell within product line + community + referral. Never assume subscription. Win-back is "new product" or "new season," not "time to restock."

**Seasonal demand:** Include off-season strategy. Don't force standard promos in off-season — demand is structurally low. Options: clearance of prior-season inventory, pre-season early-bird pricing, brand-building content with no revenue target, product development with VIP beta testers.

**Budget note:** For niche categories with strong creator communities (outdoor, fitness, specialty food), consider shifting 10-15% from broad paid to influencer/UGC. Creator credibility outperforms polished brand creative in trust-driven categories.

## Campaign Brief Structure

Generate a campaign brief with the following sections:

### 1. Campaign Overview
- Campaign name suggestion
- One-sentence campaign summary
- Primary objective with a specific, measurable goal
- Secondary objectives (if applicable)
- **Promo economics**: Offer mechanic, expected margin impact at projected volume, discount penetration contribution, kill threshold

### 2. Target Audience
- Primary audience segment (DTC customer profile)
- Secondary audience segment (if applicable)
- Audience explicitly excluded from this campaign (and why)
- Where they discover brands and what influences purchase decisions

### Audience Psychology and Channel Implications

Each audience segment has different psychology that affects channel allocation, offer strategy, and content approach. Pull buyer psychology from `brand/customers.md`:

**Research-driven buyer** (common in durable goods, technical, high-ticket):
- Channels: SEO/content (buying guides, comparisons), YouTube reviews, Reddit, long-form blog
- Offer strategy: Free shipping and bundles over discounts. They buy on merit. Discounts can raise suspicion.
- Content: Specs, test data, peer reviews, comparison to alternatives
- Retargeting: Serve review content and comparison data, not urgency-based ads

**Social/aspirational buyer** (common in beauty, fashion, wellness):
- Channels: Instagram, TikTok, creator partnerships. Discovery-driven.
- Offer strategy: GWP, limited editions, seasonal bundles. Exclusivity and aspiration, not just savings.
- Content: Before/after, UGC, lifestyle imagery, creator endorsements
- Retargeting: Social proof — "10,000 people bought this month"

**Gift-giver** (cross-category, seasonal):
- Channels: Google Shopping ("gifts for [person]"), Pinterest (gift guides), Instagram (product-in-use showing gift appeal). NOT Reddit or deep content — they want curation, not research.
- Offer strategy: Gift-wrapping, bundles at price tiers, free shipping, arrival guarantee. The offer is the SERVICE (easy gifting), not the discount.
- Content: Gift guides by price tier, "for the person who [trait]" framing, reviews from other gift-givers
- Timing: Nov 15 - Dec 20 (holiday), late Jan (Valentine's), late Apr (Mother's Day), late May (Father's Day)
- Dedicate a separate content track for gift-givers when gifting is a significant use case

Use this DTC audience template:
> "[Demographics] who care about [values/lifestyle] and shop for [category] because [motivation]. They discover brands through [channels] and are influenced by [social proof type]."

Example:
> "Women 28-42 who care about clean ingredients and sustainability, shopping for skincare because they want effective products without compromise. They discover brands through Instagram and TikTok, and are influenced by creator reviews and before/after content."

### 3. Key Messages
Messaging hierarchy — work through these four layers in order:

1. **Why should I care?** (addresses the pain point, desire, or moment)
2. **What is it?** (positions the product or offer clearly)
3. **Why this brand?** (differentiates from alternatives)
4. **What should I do?** (clear call to action)

Include:
- Core campaign message (one sentence)
- 3-4 supporting messages tailored to audience motivations
- Message variations by channel (email vs. ad vs. organic social vs. SMS)
- Proof points: reviews, UGC, clinical results, press mentions, ingredient callouts

### 4. Channel Strategy

**Always start with the storefront.** Before recommending any outbound channel, assess and address the destination. Every campaign sends traffic somewhere — if the site, product page, or collection page is not ready to convert, all other channel activity is wasted spend. Site readiness is a prerequisite, not an afterthought.

Recommend channels in this order:

#### 1. Storefront (always first)

| Asset | Best For | Key Metrics | Effort |
|-------|----------|-------------|--------|
| Product pages | Conversion, SEO, paid traffic landing | Conversion rate, add-to-cart rate, bounce rate | Medium |
| Collection pages | Category campaigns, seasonal edits | Conversion rate, products per session | Medium |
| Homepage | Brand-level campaigns, hero launches | Bounce rate, CTR to product/collection | Medium |
| Cart/checkout | AOV optimization, upsell, threshold offers | Cart completion rate, AOV, upsell take rate | Medium-High |
| On-site CTAs and banners | Capturing existing traffic for campaign | CTR, email/SMS capture rate | Low |
| Landing pages | Focused campaigns, influencer traffic | Conversion rate, bounce rate | Medium |

If any storefront asset is not ready, flag it as a **blocking dependency** — no outbound channel should launch until it is live.

#### 2. Paid Acquisition

| Channel | Best For | Key Metrics | Effort |
|---------|----------|-------------|--------|
| Meta (Instagram/Facebook) | Prospecting, retargeting, lookalikes, broad awareness | ROAS, CPA, CPM, CTR, thumbstop rate | Medium |
| TikTok Ads | Younger demos, trend-driven products, UGC-style creative | CPA, CPM, hook rate, CTR, ROAS | Medium |
| Google Shopping / PMax | High-intent capture, product-level targeting | ROAS, CPC, conversion rate, impression share | Medium |
| Pinterest Ads | Discovery, aspirational categories (home, fashion, beauty) | CPA, CTR, save rate, ROAS | Low-Medium |
| YouTube / Connected TV | Brand awareness, consideration, retargeting | CPV, VCR, brand lift, assisted conversions | High |

#### 3. Email + SMS (Klaviyo Retention Flows)

- **Always-on flows** (infrastructure — never pause for a campaign): Welcome series, browse/cart abandonment, post-purchase, replenishment, winback, review request, sunset
- **Campaign-specific sends**: Announcement, reminder, last chance, early access (VIP), extended offer
- **Segmentation**: New subscribers, engaged buyers, VIP/high-LTV, lapsed, never-purchased
- **Cadence**: 3-5 emails + 1-2 SMS per promo campaign. Space appropriately to avoid fatigue.

#### 4. Organic Social

| Platform | Best For | Content Types | Cadence |
|----------|----------|---------------|---------|
| Instagram | Brand building, product showcase, community | Reels, Stories, carousels, UGC reposts | 4-7x/week |
| TikTok | Discovery, virality, younger demos | Short-form video, trends, behind-the-scenes | 3-5x/week |
| Pinterest | Evergreen discovery, aspirational categories | Pins, idea pins, product pins | 5-10x/week |

#### 5. Influencer / UGC

- **Creator partnerships**: Paid posts, affiliate programs, long-term ambassadors
- **Gifting programs**: Seeding product to micro-influencers and customers for organic content
- **UGC campaigns**: Customer photo/video collection for ad creative and social proof
- **Whitelisting**: Running paid ads through creator accounts for authenticity and reach

#### 6. SEO / Content

- Blog posts targeting purchase-intent and informational keywords
- Buying guides and comparison content
- Product page optimization (copy, schema, reviews)
- Category page content for collection-level SEO

### 5. Content Calendar

Create a week-by-week (or day-by-day for short campaigns) content calendar.

**Planning principles:**
1. **Lock storefront assets first** — product pages, collection pages, landing pages, and cart/checkout updates must be production-ready before any outbound activity. These are blocking dependencies.
2. **Build in parallel**: Site assets, ad creative, and email/SMS flows should be developed simultaneously, not sequentially. The storefront locks first, but creative production for all channels starts at the same time.
3. Start with milestones: launch date, early access window, public launch, last chance, campaign close
4. Work backward from launch to set production deadlines
5. Map content to campaign phases: teaser/hype, launch, sustain, close/urgency
6. Leave 10-15% of calendar slots open for reactive content or real-time optimization

Format as a table:

| Week | Content Piece | Channel | Owner/Notes | Status |
|------|--------------|---------|-------------|--------|

### 6. Content Pieces Needed

List every content asset required for the campaign. **Always lead with storefront assets** — these must be production-ready before any outbound content goes live.

Storefront assets to consider first:
- Updated product pages (copy, imagery, badges/callouts)
- Collection or landing page for the campaign
- Homepage hero and secondary placements
- Cart/checkout messaging (threshold banners, upsell modules)
- Pop-up or banner for email/SMS capture

Then outbound assets:
- Ad creative (static, video, UGC-style) with variations per platform
- Email designs (announcement, reminder, last chance, post-purchase)
- SMS copy
- Organic social content (feed posts, Stories, Reels, TikToks)
- Influencer briefs and talking points
- Blog or SEO content (if applicable)

For each asset, include:
- Asset name and type
- Brief description of what it should contain
- Priority (must-have vs. nice-to-have)
- Suggested timeline for creation

#### Production Timeline Benchmarks
- Product page updates: 2-3 business days (copy, imagery, QA)
- Landing/collection page: 3-5 business days (copy, design, development, QA)
- Email campaign: 2-3 business days (copy, design, test, schedule)
- SMS copy: 1 business day (draft, review, schedule)
- Ad creative (static): 2-3 business days (brief, design, variations)
- Ad creative (video/UGC): 5-10 business days (brief, production, editing, variations)
- Organic social posts: 1-2 business days (draft, design, schedule)
- Blog post: 3-5 business days (research, draft, review, publish)
- Influencer brief: 1-2 business days (draft, review)

### 7. Success Metrics

Define KPIs aligned to the campaign type. See Campaign Types below for type-specific metrics.

Core DTC metrics to always track:
- **Revenue** (total and incremental vs. baseline)
- **ROAS** (for paid channels)
- **CAC** (cost to acquire a new customer through this campaign)
- **AOV** (average order value — is the offer compressing it?)
- **Contribution margin** (revenue minus COGS, shipping, discount, and ad spend)
- **Repeat rate** (for retention campaigns: 30/60/90-day repurchase)
- **Discount penetration** (% of revenue sold on discount during campaign window)

Include:
- Primary KPI with target number
- Secondary KPIs (3-5)
- How each metric will be tracked
- Reporting cadence recommendation

### 8. Budget Allocation

DTC campaign budget framework:

| Category | Percentage of Budget | Examples |
|----------|---------------------|----------|
| Paid acquisition | 40-60% | Meta ads, TikTok ads, Google Shopping, Pinterest ads |
| Influencer / UGC | 10-20% | Creator fees, gifting, whitelisting, UGC production |
| Content production | 10-15% | Photography, video, design, copywriting |
| Email / SMS tooling | 5-10% | Klaviyo, Postscript, Attentive (platform costs + creative) |
| Organic social | 5-10% | Content creation, community management, tools |

**Budget optimization principles:**
- Start with your highest-confidence channel and allocate 60-70% of paid budget there
- Reserve 15-20% of paid budget for testing new channels or creative approaches
- Shift budget weekly based on performance data — do not set and forget
- Account for production costs separately from media spend
- Include a 10-15% contingency for scaling winners or covering overruns

### 9. Risks and Mitigations
- 2-3 potential risks (inventory, margin compression, audience fatigue, channel underperformance, discount stacking errors)
- Mitigation strategy for each
- Reference the pre-committed kill threshold from Section 1

### 10. Execution Checklist

#### Before Launch (10 questions — all must be answered)

1. What is the single objective?
2. Who is the target audience? (And who is explicitly excluded?)
3. What specific customer behavior are we trying to create?
4. What is the offer?
5. Why this offer instead of a cheaper incentive higher on the offer hierarchy?
6. What is the margin impact at projected volume?
7. What products are included / excluded?
8. Can discounts stack with subscription, loyalty, or other active codes?
9. Is inventory ready for upside scenario and prepared for softness?
10. What is the success metric and the kill threshold?

If any answer is missing or unclear, do not proceed. Surface the gap.

#### During Promo (daily check-ins)

Run through these daily while the campaign is live:
- Is conversion rate above baseline?
- Is AOV holding or compressing?
- Is CAC within acceptable range?
- Are margin dollars growing (not just revenue)?
- Are the right SKUs moving (or is one product cannibalizing)?
- Any checkout, discount code, fulfillment, or CX issues reported?

If any metric crosses the kill threshold, escalate immediately.

#### After Promo (post-mortem within 7 days)

- Did we beat baseline? (Baseline is the counterfactual — what would have happened without the promo — not zero.)
- Did we beat forecast?
- Was the incremental lift profitable after all costs?
- Who bought? (Break down by cohort, channel, and segment)
- 14-day hangover check: Did full-price sales dip after the promo ended?
- Verdict: **Repeat** (worked, do it again), **Revise** (promising but needs changes), or **Kill** (did not work, do not repeat)

## Campaign Types

### Revenue / Promo Campaign

Primary goal: drive revenue through a specific offer mechanic.

| Metric | What It Measures |
|--------|-----------------|
| Revenue (total + incremental) | Top-line impact vs. baseline |
| ROAS | Efficiency of paid spend |
| AOV | Whether the offer compresses order value |
| Contribution margin | Profitability after COGS, shipping, discount, ad spend |
| Discount penetration | % of revenue sold on discount |
| New vs. returning customer split | Who the promo attracted |

### Seasonal Campaign

Pre-built frameworks for major DTC moments:

| Season | Typical Timeline | Offer Structure | Email/SMS Cadence |
|--------|-----------------|-----------------|-------------------|
| Valentine's Day | Creative by Jan 15, launch Jan 25-28, run through Feb 14 | GWP, bundles, limited edition | 3-4 emails, 1-2 SMS |
| Mother's Day | Creative by Apr 1, launch Apr 20-25, run through May 11 | Bundles, gifting sets, free shipping | 4-5 emails, 2 SMS |
| Father's Day | Creative by May 1, launch May 25-30, run through Jun 15 | Bundles, gifting sets, threshold offers | 3-4 emails, 1-2 SMS |
| Back to School | Creative by Jul 1, launch Jul 15-20, run through Aug 31 | Bundles, % off, threshold offers | 3-4 emails, 1-2 SMS |
| BFCM | Creative by Oct 1, launch mid-Nov (VIP early access), run through Cyber Monday | Deepest annual offer, sitewide OK here | 8-12 emails, 3-4 SMS |
| Holiday / Gifting | Creative by Nov 1, launch post-BFCM, run through Dec 20-22 (shipping cutoff) | Gift sets, GWP, expedited shipping offers | 5-7 emails, 2-3 SMS |

Seasonal campaigns should reference the promo calendar framework to ensure they fit within annual discount penetration guardrails.

### Product Launch

Consumer-facing launch sequence:

| Phase | Timing | Activities |
|-------|--------|------------|
| Teaser | 2-4 weeks pre-launch | Coming soon messaging, waitlist, social hints, influencer seeding |
| Reveal | 1 week pre-launch | Full product reveal, email announcement, early access for VIP/subscribers |
| Available Now | Launch day | Sitewide update, paid ads live, email/SMS blast, social push, influencer posts go live |
| Sustain | 2-4 weeks post-launch | Reviews/UGC collection, retargeting, content marketing, restock updates |

| Metric | What It Measures |
|--------|-----------------|
| Units sold (first 7/14/30 days) | Initial demand validation |
| Waitlist conversion rate | Pre-launch interest to purchase |
| Revenue vs. forecast | Accuracy of demand planning |
| New customer % | Whether the product expanded the audience |
| Review volume and rating | Early product-market signal |

### Retention / Winback

| Metric | What It Measures |
|--------|-----------------|
| Repeat purchase rate (30/60/90-day) | Customer stickiness |
| Customer lifetime value (LTV) | Long-term revenue per customer |
| Reactivation rate | Lapsed customers returning to purchase |
| Time between purchases | Purchase frequency trend |
| Subscription conversion rate | Shift from one-time to recurring revenue |

### Off-Season / Counter-Seasonal Campaign

For brands with concentrated seasonal demand. Don't try to force standard promos in off-season — demand is structurally low.

| Strategy | When to Use | Key Metrics |
|----------|-------------|-------------|
| Clearance | Prior-season inventory or discontinued colors | Units moved, inventory cleared, margin preserved |
| Pre-season early-bird | Next season's products, early commitment incentive | Pre-orders, email signups, early revenue |
| Brand-building | Content, community, partnerships — no revenue target | Engagement, email list growth, organic traffic, brand search volume |
| Product development | Beta testing with VIP customers, waitlist for new products | Waitlist signups, VIP engagement, product feedback |

Off-season is for building the audience you'll monetize in-season. Content published in off-season indexes for SEO by the time peak season arrives.

### Sport/Activity Season Launch

For brands tied to activity seasons (ski season, surf season, hiking season, cycling season):

| Phase | Timing | Activities |
|-------|--------|------------|
| Pre-season | 4-6 weeks before season | Influencer seeding, blog content for SEO, email list growth, product page updates, pre-order/early access |
| Season launch | First week of season | Full campaign launch — storefront, paid, email/SMS, organic, influencer content goes live |
| In-season sustain | Throughout peak months | UGC collection, retargeting, performance optimization, seasonal content |
| End of season | Last 2-3 weeks | Clearance (if applicable), "last chance" messaging, off-season transition |
| Off-season | Between seasons | See Off-Season strategy above |

### Brand Awareness

| Metric | What It Measures |
|--------|-----------------|
| Reach and impressions | How many people saw the campaign |
| Engagement rate | Interaction depth (likes, comments, shares, saves) |
| New followers / subscribers | Audience growth |
| Branded search volume | People searching for the brand by name |
| Direct traffic | People coming to the site unprompted |
| Share of voice | Brand mentions vs. competitors |

## Output

Present the full campaign brief with clear headings and formatting. After the brief, ask:

"Would you like me to:
- Dive deeper into any section?
- Draft specific content pieces from the calendar (email copy, ad creative briefs, SMS)?
- Run a competitive scan to sharpen the positioning?
- Build out the full promo calendar for the year?
- Stress-test the promo economics (margin sensitivity, discount penetration impact)?"
