# Marketing Knowledgebase Plugin

## What This Is

A DTC marketing plugin with 8 skills for campaign planning, content creation, email/SMS flows, competitive intelligence, brand management, SEO, and performance reporting. Every skill is built around DTC economics — contribution margin as the north star, not vanity metrics.

## Getting Started

### First-Time Setup

1. **Run `/brand-review setup`** — fills in the `brand/` directory (voice, products, customers). This is the foundation. Every other skill reads from these files. Takes 15-30 minutes.

2. **Run `/campaign-plan`** — builds your first campaign brief with promo economics, channel strategy, and execution checklist. If you provide competitors, it runs a lightweight competitive scan inline.

3. **Run `/draft-content` and `/email-sequence` in parallel** — these produce the actual content and retention flows for the campaign. Both auto-apply brand context from step 1.

4. **Run `/brand-review`** — QA all content before launch.

5. **Run `/performance-report`** — post-mortem after campaign ends.

You can run any skill standalone, but output quality improves significantly when `brand/` files are populated first.

### Skill Quick Reference

| Command | When to Use |
|---|---|
| `/brand-review setup` | First time, or when updating brand voice/products/customers |
| `/brand-review` | QA content before publishing |
| `/campaign-plan` | Planning any campaign, seasonal promo, or building annual calendar |
| `/draft-content` | Writing product descriptions, ad copy, social posts, gift guides, influencer briefs |
| `/email-sequence` | Building email + SMS flows (welcome, abandoned cart, post-purchase, etc.) |
| `/competitive-brief` | Deep competitive research — ad creative, pricing, influencer, storefront teardown |
| `/performance-report` | Post-campaign analysis, weekly/monthly reporting, promo post-mortems |
| `/seo-audit` | Keyword research, product page SEO, content gap analysis |

## Key Files

```
brand/
  voice.md          — brand personality, voice attributes, tone by channel
  products.md       — product catalog, pricing, claims, hero SKUs
  customers.md      — customer profiles, language bank, social proof themes

skills/
  brand-review/     — brand setup + content QA
  campaign-plan/    — campaign briefs with promo economics
  draft-content/    — DTC content drafting (9 content types)
  email-sequence/   — email + SMS lifecycle flows (12 flow types)
  competitive-brief/— DTC competitive intelligence
  performance-report/— contribution-margin-first reporting
  seo-audit/        — SEO with e-commerce focus
  content-creation/ — background reference skill (not user-invocable)

CONNECTORS.md       — MCP integration reference
```

## Core Principles

- **Storefront first** — every campaign starts with the site. Product pages, collection pages, and conversion flows must be ready before any outbound channel launches.
- **Contribution margin is the north star** — not revenue, not ROAS. Revenue minus discount minus COGS minus shipping minus payment fees minus fulfillment minus promo media, measured against counterfactual baseline.
- **Offer hierarchy** — exhaust cheaper incentives before going deeper: early access → loyalty perks → free shipping → GWP → bundles → % off secondary SKUs → sitewide % off (last resort).
- **Hero SKU protection** — never deep-discount the anchor product. Once the discount price becomes the reference price, pricing power is permanently lowered.
- **Brand context flows through everything** — populate `brand/` once, every skill uses it automatically.

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
