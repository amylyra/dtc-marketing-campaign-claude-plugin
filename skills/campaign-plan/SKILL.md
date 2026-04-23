---
name: campaign-plan
description: Plan a DTC campaign through a stepped, conversational flow — lock strategy first, then site creative assets, then channels and execution. Use when planning a product launch, seasonal campaign, revenue push, or retention play.
argument-hint: "<campaign objective or product>"
---

# Campaign Plan

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../../CONNECTORS.md).

Plan a DTC campaign in 4 steps. Start with 3 theme options (safe, competitive, wild card), iterate until the user locks one, then build site assets, channels, and execution from it. Each step gets user sign-off before moving forward. Goal: most engaging on-brand content with minimum team effort.

## Trigger

User runs `/campaign-plan` or asks to plan, design, or build a marketing campaign.

## Design Principles

1. **On-brand, engaging output.** Every piece of copy direction must be specific to THIS brand with THIS campaign story — not generic templates.
2. **Minimum effort, maximum impact.** Short list of high-impact todos. Don't give the team 15 things when 5 move the needle.
3. **Essential vs. optional, always.** Tier by impact: make-or-break vs. amplifies vs. only-if-needed.
4. **Get materials from users.** Ask what they already have before assuming blank slate. Adapt > create from scratch.
5. **Strategy first.** Campaign theme determines which assets matter and what they say.
6. **Concise output.** Scannable — bullet points, tables, short copy direction. No walls of text.

## Intake

Gather before starting Step 1. Ask for anything missing — batch questions, max 3 per message.

1. **Campaign goal** — the primary objective (e.g., drive revenue, launch a product, increase AOV, reactivate lapsed customers)
2. **Target audience** — who the campaign is aimed at (new customers, VIP/repeat buyers, lapsed, gift-givers, specific segment)
3. **Timeline** — campaign duration and any fixed dates (launch date, seasonal deadline, shipping cutoff)
4. **Product or collection** — what's being promoted (mandatory, not optional)
5. **Brand context** — If a `brand/` directory exists, auto-apply product catalog and customer profiles. Reference products by name and price. If no `brand/` directory is found, prompt the user to set one up or paste key details.

**Deferred to later steps** (don't ask upfront):
- Budget range → Step 3 (Channels + Calendar)
- Competitors → offer to scan inline during Step 1 if mentioned, but don't gate on it
- Previous campaign performance → ask during Step 1 if relevant

### Ask, Don't Assume

For any information needed that isn't available, ask the user — don't skip or assume. Batch questions (max 3 per message, prioritize most blocking first). Proactively ask what existing materials/assets the user has before generating from scratch.

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

## Site Creative Asset Checklist

Reference table for Step 2. Typical tiers shown — adapt based on the specific campaign. A threshold-offer campaign makes Cart Messaging essential; a brand awareness campaign may skip PDP Badges entirely.

| Asset | What It Is | Typical Tier |
|-------|-----------|-------------|
| HP Banner | Homepage hero — highest-traffic placement | Essential |
| Collection Page Banner (Shop All) | Top of main collection — sets campaign context | Essential |
| Collection Page Banner (Category) | Category-specific angle if needed | Essential / Recommended |
| Announcement Bar | Site-wide top bar — one key message, character-limited | Essential |
| Nav Super Menu Merch | Navigation dropdown merchandising zone | Recommended |
| Collection Page Inline Promo Spot | Mid-browse offer reminder within product grid | Recommended |
| PDP Badges / Callouts | "New," "Best Seller," campaign-specific badges per SKU | Recommended |
| Cart / Checkout Messaging | Threshold banners, upsell modules, offer reminders | Only if needed |
| Pop-up / Slide-in | Email/SMS capture, offer announcement | Only if needed |
| Landing Page | Standalone campaign destination (only if existing pages don't fit) | Only if needed |

## Brand Guide & Design System

Check these before producing site creative asset direction in Step 2:

1. **Brand voice** — If `brand/voice.md` exists, auto-apply tone, terminology, and brand energy to all copy direction.
2. **Figma / design tool** — If Figma is connected (`~~design`), pull UI kit components, asset dimensions, typography, and color specs for each site asset. Reference existing component frames.
3. **User's existing materials** — Ask at the start of Step 2: "What do you already have? Past campaign assets, brand guide, Figma/UI kit, previous creative that worked?" Adapt existing assets before creating from scratch.

If no brand guide or design tool is available, ask: "Do you have a brand guide or UI kit I should reference for site asset specs?"

## Audience Psychology Reference

Each audience segment has different psychology that affects channel allocation, offer strategy, and content. Pull buyer psychology from `brand/customers.md`.

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

DTC audience template:
> "[Demographics] who care about [values/lifestyle] and shop for [category] because [motivation]. They discover brands through [channels] and are influenced by [social proof type]."

## Channel Reference

Reference tables for Step 3. Include only channels relevant to the specific campaign.

### Paid Acquisition

| Channel | Best For | Key Metrics |
|---------|----------|-------------|
| Meta (Instagram/Facebook) | Prospecting, retargeting, lookalikes | ROAS, CPA, CPM, CTR, thumbstop rate |
| TikTok Ads | Younger demos, UGC-style creative | CPA, hook rate, CTR, ROAS |
| Google Shopping / PMax | High-intent capture | ROAS, CPC, conversion rate |
| Pinterest Ads | Discovery, aspirational categories | CPA, CTR, save rate, ROAS |

### Email + SMS

- **Always-on flows** (infrastructure — never pause): Welcome, cart abandonment, post-purchase, replenishment, winback, review request
- **Campaign sends**: Announcement, reminder, last chance, VIP early access
- **Segmentation**: New subscribers, engaged buyers, VIP, lapsed, never-purchased

### Organic Social

| Platform | Best For | Cadence |
|----------|----------|---------|
| Instagram | Brand building, product showcase, community | 4-7x/week |
| TikTok | Discovery, virality, younger demos | 3-5x/week |
| Pinterest | Evergreen discovery, aspirational categories | 5-10x/week |

### Influencer / UGC
- Creator partnerships, gifting programs, UGC campaigns, whitelisting (paid ads through creator accounts)

### Budget Framework

| Category | % of Budget |
|----------|------------|
| Paid acquisition | 40-60% |
| Influencer / UGC | 10-20% |
| Content production | 10-15% |
| Email / SMS tooling | 5-10% |
| Organic social | 5-10% |

### Production Timeline Benchmarks

Use when building the campaign timeline in Step 3.

| Asset Type | Lead Time |
|-----------|-----------|
| Product page updates | 2-3 business days |
| Landing/collection page | 3-5 business days |
| Email campaign | 2-3 business days |
| SMS copy | 1 business day |
| Ad creative (static) | 2-3 business days |
| Ad creative (video/UGC) | 5-10 business days |
| Organic social posts | 1-2 business days |
| Influencer brief | 1-2 business days |

## Execution Checklist Reference

Full checklist for reference. Step 4 presents the condensed version; teams can reference this for the complete list.

### Before Launch (10 questions — all must be answered)

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

### During Promo (daily check-ins)

- Is conversion rate above baseline?
- Is AOV holding or compressing?
- Is CAC within acceptable range?
- Are margin dollars growing (not just revenue)?
- Are the right SKUs moving (or is one product cannibalizing)?
- Any checkout, discount code, fulfillment, or CX issues reported?

If any metric crosses the kill threshold, escalate immediately.

### After Promo (post-mortem within 7 days)

- Did we beat baseline? (Baseline = counterfactual, not zero.)
- Did we beat forecast?
- Was the incremental lift profitable after all costs?
- Who bought? (Break down by cohort, channel, segment)
- 14-day hangover check: Did full-price sales dip after the promo ended?
- Verdict: **Repeat** / **Revise** / **Kill**

---

## Stepped Flow

Work through these 4 steps in order. Each step produces output and gets user sign-off before moving to the next. Do not skip ahead.

### Opening: Orient the User

Before starting Step 1, briefly tell the user what to expect. Keep it to 3-4 lines max:

> **Here's how this works:**
> 1. **Strategy** — we'll pick a campaign theme and offer (you choose from 3 options)
> 2. **Site assets** — prioritized list of what to build on-site, with copy direction
> 3. **Channels + calendar** — where to promote, when, and budget
> 4. **Metrics + execution** — KPIs, risks, go/no-go checklist
>
> Each step gets your sign-off before I move on. Let's start with strategy.

Then proceed to intake questions (from the Intake section above) and Step 1.

### Step 1: Campaign Strategy

Step 1 has two parts: first present 3 theme options, then once the user picks a direction, fill in the full strategy.

#### Part A: Three Theme Options

Present 3 campaign theme concepts. Each gets a **one-line theme name** and a **2-3 sentence pitch** — that's it. No walls of text. The user needs to react fast, not read an essay.

**Option 1 — Safe Bet** (brand-led, educational, proven):
The on-brand, well-received angle. Leans into what the brand already does well. Educates, informs, reinforces positioning. Lowest risk.
- *Example for Tern BFCM: "Gear Up Before It Freezes" — Seasonal education play. Position Tern as essential winter prep. Lead with the problem (frozen gear), not the discount.*

**Option 2 — Competitive Edge** (differentiation-led, stand out in promo noise):
Focuses on what makes this product/brand different from everything else in market. Designed to cut through a sea of "20% off everything" promos. Leads with the unique product advantage.
- *Example for Tern BFCM: "Everyone Else Sells Insulated Bottles. We Insulate Yours." — Direct competitive contrast. Position against Hydro Flask, Stanley, etc. The hook is the category difference, not the discount.*

**Option 3 — Wild Card** (on-brand voice, unexpected angle, hook-first):
Same brand voice, polar opposite idea. Designed to stop the scroll. May be provocative, counterintuitive, or emotional. Higher risk, higher ceiling.
- *Example for Tern BFCM: "Your $45 Water Bottle Is Broken." — Confrontational hook. Challenges the reader's current gear. Insulated bottles still freeze — that's a design flaw, not a user problem. Tern is the fix.*

**Format for each option:**
> **[Option name]**: "[Theme line]"
> [2-3 sentence pitch. What the angle is, why it works, what it leads with.]

Do NOT include full messaging hierarchy, offer mechanics, or audience details yet. The user picks a direction first. All 3 options should be readable in under 30 seconds.

**Gate:** "Which direction resonates? You can pick one, mix elements, or tell me what's missing and I'll riff."

#### Part B: Iterate and Lock Strategy

After the user picks a direction (or gives feedback), this becomes a conversation:

- **Picks one** → flesh it out into the full strategy below
- **Wants changes** → revise and re-present the theme
- **Wants to explore** → offer references, research angles, or new variations
- **Wants competitive context** → run a lightweight scan inline
- **Has their own idea** → great, use it — shape it into the strategy format below

Keep iterating until the user explicitly confirms the theme. The theme is the foundation — everything downstream (site assets, ad creative, email copy) flows from it. A weak theme wastes all downstream work.

Once the theme is locked, produce the **full strategy** in this table format — concise and scannable:

| Element | Detail |
|---------|--------|
| **Theme** | [Locked theme line] |
| **Audience** | Primary: [who]. Secondary: [if any]. Excluded: [who + why]. |
| **Messages** | 1. Why care: [one line] 2. What is it: [one line] 3. Why us: [one line] 4. CTA: [one line] |
| **Offer** | [Mechanic] — hierarchy check: [why not cheaper?] |
| **Kill threshold** | [Specific metric + number + when to check] |
| **Promo economics** | [Margin impact, discount penetration estimate] |

Pull audience psychology from `brand/customers.md` and the Audience Psychology Reference. If the user mentions competitors, run a lightweight competitive scan inline. If a `/competitive-brief` exists in conversation, pull from it.

**Gate:** "Strategy locked. Ready for site assets, or want to adjust anything?"

Do not ask about materials yet — let the user focus on strategy alignment.

### Step 2: Site Creative Assets

**Open with:** "Before I build the asset list — what do you already have? Past campaign assets, brand guide, Figma/UI kit, previous creative that worked?"

Then produce a **prioritized asset list** — tiered by impact for this specific campaign, not a flat checklist. Reference the Site Creative Asset Checklist and Brand Guide & Design System sections above.

**Tier the assets based on the specific campaign:**

**Essential** (make or break — highest-traffic, highest-conversion placements):
- Typically: HP Banner, Collection Page Banner, Announcement Bar

**Recommended** (amplify if the team has bandwidth):
- Typically: Nav Super Menu Merch, Collection Page Inline Promo Spot, PDP Badges/Callouts

**Only if needed** (conditional on campaign mechanics):
- Landing Page, Cart/Checkout Messaging, Pop-up/Slide-in

For each asset in the list, provide:
- **Specific copy direction tied to the campaign story** — not generic. Reference brand voice and energy.
- Key message (from Step 1 messaging hierarchy)
- Design notes from brand guide / UI kit / Figma if available

If the user provided existing materials, note which assets can be adapted vs. built from scratch.

**Gate:** "Here's the prioritized asset list with copy direction. Anything to add, remove, or change?"

### Step 3: Channels + Calendar

**Ask now (deferred from intake):** Budget range, channel preferences/constraints.

**Produce a concise channel plan.** Reference the Channel Reference section above. Only include channels relevant to this campaign.

**Tiered channels (essential / recommended / optional):**
- **Email** — Essential: Announcement + Last chance (2 sends). Recommended: VIP early access, segment-specific variants. Optional: educational content, post-campaign nurture.
- **Meta paid** — Essential: 2-3 ad concepts + retargeting creative. Recommended: 5-10 hook variants, UGC-style creative, lookalike audiences. Optional: whitelisted influencer ads, broad awareness.

**Essentials-only channels (no tiering — just the core):**
- **SMS** — Launch + Last chance (2 sends max).
- **Google** — Shopping feed update + branded search.
- **Organic social, Influencer/UGC, SEO** — Brief, relevant recommendations only.

**Campaign timeline** — simple date/milestone/asset table. Site assets from Step 2 are blocking dependencies; outbound builds in parallel.

| Date | Milestone | What Goes Live |
|------|-----------|---------------|
| *Example* | *Campaign launch* | *HP Banner, Collection, Announcement Bar* |
| | *Email #1* | *Announcement email + SMS* |
| | *Urgency push* | *Updated bar copy, retargeting ramp* |
| | *Last chance* | *Last chance email + SMS* |
| | *Campaign ends* | *All campaign assets removed* |

**Budget allocation** — one table using the Budget Framework reference. No narrative.

**Gate:** "Channel plan and calendar look right? I'll finalize with metrics and execution."

### Step 4: Metrics, Risks + Execution

**Produce (concise — one page max):**

**Success metrics** — 3-5 KPIs with target numbers. See Campaign Types below for type-specific guidance. Core DTC metrics:
- Contribution margin (north star)
- Revenue (total + incremental vs. baseline)
- ROAS (paid channels)
- AOV
- Discount penetration

**Risks** — top 2-3 risks with one-line mitigations. Reference the kill threshold from Step 1.

**Execution checklist (condensed)** — top 5 before-launch questions:
1. What is the offer and why not a cheaper incentive?
2. What is the margin impact at projected volume?
3. Are all site assets live and QA'd?
4. Can discounts stack with other active codes?
5. What is the kill threshold?

Full 10-question checklist + daily/post-mortem checklists available in the Execution Checklist Reference section.

**End with:** "What do you want me to draft first?"
- Copy for site assets from Step 2
- Ad creative (hooks + concepts)
- Email/SMS copy
- Competitive scan
- Full annual promo calendar

## Step Transitions

**Skip-ahead:** If the user asks to skip to a later step, confirm they're comfortable with defaults for the skipped step. Summarize what you'll assume, and proceed.

**Go back:** If the user wants to revise a locked step, re-present that step with their edits, get confirmation, then check if changes affect subsequent steps.

**Single-pass mode:** If the user says "just give me the whole thing," produce all 4 steps in sequence with a note on assumed defaults. Still tier assets and channels.

---

## Campaign Types

### Revenue / Promo Campaign

| Metric | What It Measures |
|--------|-----------------|
| Revenue (total + incremental) | Top-line impact vs. baseline |
| ROAS | Efficiency of paid spend |
| AOV | Whether the offer compresses order value |
| Contribution margin | Profitability after COGS, shipping, discount, ad spend |
| Discount penetration | % of revenue sold on discount |
| New vs. returning customer split | Who the promo attracted |

### Seasonal Campaign

| Season | Typical Timeline | Offer Structure | Email/SMS Cadence |
|--------|-----------------|-----------------|-------------------|
| Valentine's Day | Creative by Jan 15, launch Jan 25-28, run through Feb 14 | GWP, bundles, limited edition | 3-4 emails, 1-2 SMS |
| Mother's Day | Creative by Apr 1, launch Apr 20-25, run through May 11 | Bundles, gifting sets, free shipping | 4-5 emails, 2 SMS |
| Father's Day | Creative by May 1, launch May 25-30, run through Jun 15 | Bundles, gifting sets, threshold offers | 3-4 emails, 1-2 SMS |
| Back to School | Creative by Jul 1, launch Jul 15-20, run through Aug 31 | Bundles, % off, threshold offers | 3-4 emails, 1-2 SMS |
| BFCM | Creative by Oct 1, launch mid-Nov (VIP early access), run through Cyber Monday | Deepest annual offer, sitewide OK here | 8-12 emails, 3-4 SMS |
| Holiday / Gifting | Creative by Nov 1, launch post-BFCM, run through Dec 20-22 (shipping cutoff) | Gift sets, GWP, expedited shipping offers | 5-7 emails, 2-3 SMS |

### Product Launch

| Phase | Timing | Activities |
|-------|--------|------------|
| Teaser | 2-4 weeks pre-launch | Coming soon messaging, waitlist, social hints, influencer seeding |
| Reveal | 1 week pre-launch | Full product reveal, email announcement, early access for VIP/subscribers |
| Available Now | Launch day | Sitewide update, paid ads live, email/SMS blast, social push, influencer posts go live |
| Sustain | 2-4 weeks post-launch | Reviews/UGC collection, retargeting, content marketing, restock updates |

### Retention / Winback

| Metric | What It Measures |
|--------|-----------------|
| Repeat purchase rate (30/60/90-day) | Customer stickiness |
| Customer lifetime value (LTV) | Long-term revenue per customer |
| Reactivation rate | Lapsed customers returning to purchase |

### Off-Season / Counter-Seasonal Campaign

| Strategy | When to Use | Key Metrics |
|----------|-------------|-------------|
| Clearance | Prior-season inventory or discontinued colors | Units moved, inventory cleared, margin preserved |
| Pre-season early-bird | Next season's products, early commitment incentive | Pre-orders, email signups, early revenue |
| Brand-building | Content, community, partnerships — no revenue target | Engagement, email list growth, organic traffic, brand search volume |
| Product development | Beta testing with VIP customers, waitlist for new products | Waitlist signups, VIP engagement, product feedback |

Off-season is for building the audience you'll monetize in-season.

### Sport/Activity Season Launch

| Phase | Timing | Activities |
|-------|--------|------------|
| Pre-season | 4-6 weeks before season | Influencer seeding, SEO content, email list growth, product page updates, pre-order/early access |
| Season launch | First week of season | Full campaign launch — storefront, paid, email/SMS, organic, influencer content goes live |
| In-season sustain | Throughout peak months | UGC collection, retargeting, performance optimization, seasonal content |
| End of season | Last 2-3 weeks | Clearance (if applicable), "last chance" messaging, off-season transition |
| Off-season | Between seasons | See Off-Season strategy above |

### Brand Awareness

| Metric | What It Measures |
|--------|-----------------|
| Reach and impressions | How many people saw the campaign |
| Engagement rate | Interaction depth (likes, comments, shares, saves) |
| Branded search volume | People searching for the brand by name |
| Direct traffic | People coming to the site unprompted |
