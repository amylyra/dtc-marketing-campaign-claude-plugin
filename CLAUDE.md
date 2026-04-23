# Marketing Knowledgebase Plugin

## What This Is

A DTC marketing plugin with 8 skills for campaign planning, content creation, email/SMS flows, competitive intelligence, brand management, SEO, and performance reporting. Every skill is built around DTC economics — contribution margin as the north star, not vanity metrics.

## Getting Started

### First-Time Setup

1. **Run `/brand-review setup`** — fills in the `brand/` directory (voice, products with product profile, customers with buyer psychology). This is the foundation. Every other skill reads from these files. Takes 15-30 minutes.

2. **Run `/campaign-plan`** — pick from 3 theme directions, lock strategy, plan site assets and channels. Saves a campaign brief to `campaigns/` that downstream skills auto-load.

3. **Run `/draft-content` and `/email-sequence`** — these auto-load your campaign brief (theme, arc, audience, creative direction) and produce channel-specific content. No need to re-explain the campaign.

4. **Run `/brand-review`** — QA all content before launch.

5. **Run `/performance-report`** — post-mortem after campaign ends.

You can run any skill standalone, but output quality improves significantly when `brand/` files are populated first.

### Skill Quick Reference

| Command | When to Use |
|---|---|
| `/brand-review setup` | First time, or when updating brand voice/products/customers |
| `/brand-review` | QA content before publishing — checks voice, claims, proof-to-psychology match, engagement quality (hook strength, competitive distinctiveness, persuasion) |
| `/campaign-plan` | Planning any campaign in 4 steps: strategy lock → site creative assets → channels/calendar → metrics/execution |
| `/draft-content` | Writing product descriptions, ad copy, social posts, gift guides, influencer briefs — with copy quality standards (hook quality, variant diversity, swap test) |
| `/email-sequence` | Building email + SMS flows (welcome, abandoned cart, post-purchase, etc.) |
| `/competitive-brief` | Deep competitive research — ad creative, pricing, influencer, storefront teardown, or substitute analysis for category creators |
| `/performance-report` | Post-campaign analysis, weekly/monthly reporting, promo post-mortems |
| `/seo-audit` | Keyword research, product page SEO, content gap analysis, novel product keyword strategy |

## Key Files

```
brand/
  voice.md          — brand personality, voice attributes, tone by channel
  products.md       — product profile (type, replenishment, seasonal demand), catalog, pricing, claims, hero SKUs
  customers.md      — customer segments, buyer psychology (8 dimensions), language bank, social proof themes

campaigns/          — saved campaign briefs (created by /campaign-plan, auto-loaded by /draft-content, /email-sequence, /brand-review)

skills/
  brand-review/     — brand setup + content QA (incl. proof-to-psychology match, engagement quality, campaign alignment)
  campaign-plan/    — 4-step campaign planning: 3 theme options → site creative assets → channels/calendar → metrics/execution. Saves brief for downstream skills.
  draft-content/    — DTC content drafting (9 content types, audience-adaptive messaging, creative concept brainstorm). Auto-loads campaign briefs.
  email-sequence/   — email + SMS lifecycle flows (12 flow types, product-type matrix, promo psychology). Auto-loads campaign briefs.
  competitive-brief/— DTC competitive intelligence (incl. category position analysis)
  performance-report/— contribution-margin-first reporting (seasonal adjustments, cohort psychology)
  seo-audit/        — SEO with e-commerce focus (incl. novel product keyword strategy)
  content-creation/ — background reference skill (not user-invocable)

tests/              — evaluation framework and test suite (Tern brand)
CONNECTORS.md       — MCP integration reference
```

## Core Principles

- **Storefront first** — every campaign starts with the site. Product pages, collection pages, and conversion flows must be ready before any outbound channel launches.
- **Contribution margin is the north star** — not revenue, not ROAS. Revenue minus discount minus COGS minus shipping minus payment fees minus fulfillment minus promo media, measured against counterfactual baseline.
- **Offer hierarchy** — exhaust cheaper incentives before going deeper: early access → loyalty perks → free shipping → GWP → bundles → % off secondary SKUs → sitewide % off (last resort). Adapts by product type (single-SKU, durable goods, seasonal demand).
- **Hero SKU protection** — never deep-discount the anchor product. Once the discount price becomes the reference price, pricing power is permanently lowered.
- **Brand context flows through everything** — populate `brand/` once, every skill uses it automatically.
- **Campaign briefs are the handoff** — `/campaign-plan` saves a brief to `campaigns/`. Downstream skills (`/draft-content`, `/email-sequence`, `/brand-review`) auto-load it so the user never re-explains the campaign. Theme, arc, audience, offer, and creative direction flow through.
- **Buyer psychology drives adaptation** — each audience segment has different decision-making psychology. Skills adapt proof strategy, flow structure, channel allocation, and messaging based on buyer psychology, not just demographics.
- **Product type shapes everything** — consumable, durable, fashion, and subscription products need different flows, offers, and retention strategies. Skills check `brand/products.md` Product Profile and adapt.

## MCP Integrations

Connected: Klaviyo (email/SMS), Ahrefs (SEO), Similarweb (competitive), Amplitude (analytics), Supermetrics (data), Slack (team), Canva (design), Figma (design), Notion (docs).

See [CONNECTORS.md](CONNECTORS.md) for the full reference including DTC-specific placeholders (storefront, ad platform, attribution, reviews).

## FTC Compliance (Canonical Reference)

All skills that produce influencer content, UGC, or promotional claims must follow these rules:

**Influencer Disclosure:**
- Must include `#ad` or `#partner` (or "Paid partnership" label on platform)
- Disclosure must be visible in the first 3 seconds of video or above the fold in captions
- Cannot be buried in hashtag blocks or at the end of long captions
- Applies to paid partnerships, gifted products, and affiliate relationships

**Health/Beauty Claims:**
- No claims without substantiation (clinical studies, dermatologist verification)
- "Results may vary" disclaimer required alongside before/after imagery
- Cannot use "cure," "treat," or medical language unless FDA-approved

**Subscription Language:**
- Auto-renewal terms must be clearly disclosed before purchase
- Cancellation process must be described (not just "cancel anytime" without explanation)
- Price-after-trial must be prominent

**UGC Usage Rights:**
- Written permission required before repurposing customer content in ads
- Attribution required unless permission explicitly waives it
- Rights scope (organic only, paid amplification, duration) must be defined

Skills reference this section rather than maintaining separate compliance definitions.
