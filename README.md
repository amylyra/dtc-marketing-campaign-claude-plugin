# Marketing Knowledgebase Plugin

A DTC marketing plugin for Claude Code and Claude.ai. Campaign planning with promo economics, email/SMS retention flows, ad creative drafting, brand voice management, competitive intelligence, SEO audits, and performance reporting — all built around contribution margin as the north star.

Works across product types (consumable, durable goods, fashion, subscription), audience segments (self-purchase, gift-giver, VIP, lapsed, cold prospect), and category positions (established, challenger, category creator).

## Getting Started

### First-Time Setup (15-30 minutes)

```
1. /brand-review setup     → populate brand voice, product catalog, customer profiles
2. /campaign-plan           → build your first campaign brief
3. /draft-content           → write content assets  ┐
   /email-sequence          → build retention flows  ┤ run in parallel
4. /brand-review            → QA everything before launch
5. /performance-report      → post-mortem after campaign ends
```

Step 1 is the most important — every other skill reads from the `brand/` files it creates. You can run any skill standalone, but output quality improves significantly with brand context.

The `brand/` templates include a worked example (Glow Lab skincare) to show what "done" looks like. Delete the examples and fill in your own brand.

---

## Architecture

### The Foundation: Brand Knowledge

Before any skill produces content, it checks for the `brand/` directory:

```
brand/
  voice.md       — personality, voice attributes, tone by channel, terminology
  products.md    — product profile, hero SKUs, prices, claims, differentiators
  customers.md   — segments, buyer psychology, language bank, objections
```

Run `/brand-review setup` to fill these in. Once populated, every skill auto-applies brand voice, product details, and customer language. No re-entering context each time.

#### Buyer Psychology (the foundation beneath the foundation)

Each customer segment in `customers.md` includes an 8-dimension buyer psychology profile:

| Dimension | What it captures |
|-----------|-----------------|
| Decision mode | Impulse, semi-considered, or deeply researched? |
| Trust hierarchy | What proof sources they trust, in order |
| Risk perception | Performance, social, financial, or safety fear? |
| Purchase trigger | What event pushes browsing to buying? |
| Consideration depth | How many sessions before purchase? |
| Objection pattern | What objections they have + what proof resolves them |
| Post-purchase psychology | What triggers satisfaction vs. regret? |
| Advocacy trigger | What would make them tell a friend? |

This psychology cascades through every skill — it shapes ad creative proof strategy, email flow structure, campaign channel allocation, competitive framing, and content QA.

#### Product Profile

`products.md` includes a Product Profile that captures product type (consumable / durable / fashion / subscription-native), replenishment cycle, seasonal demand, and margin structure. Skills adapt their output based on product type:

- **Consumable**: replenishment flows, subscription offers, routine-building content
- **Durable goods**: cross-sell flows, seasonal re-engagement, no replenishment assumptions
- **Fashion**: collection-based, trend-influenced, identity-driven messaging
- **Subscription-native**: churn prevention, upgrade paths, usage-based triggers

### Skill Map

```
┌─────────────────────────────────────────────────────────────┐
│                       brand/ directory                       │
│   voice.md · products.md (profile) · customers.md (psych)   │
│         (foundation — every skill reads from here)           │
└───────────────────────────┬─────────────────────────────────┘
                            │
┌───────────────────────────┼─────────────────────────────────┐
│                     Claude (Orchestrator)                    │
└──────┬──────────┬─────────┼──────────┬──────────┬───────────┘
       │          │         │          │          │
       ▼          ▼         ▼          ▼          ▼
  /campaign-  /draft-   /email-    /brand-   /competitive-
    plan      content   sequence   review       brief
       │          │         │
       ▼          ▼         ▼
  /performance-         /seo-audit
     report
       │
       ▼
┌─────────────────────────────────────────────────────────────┐
│              content-creation (background skill)             │
│   DTC templates, ad frameworks, SEO rules, CTAs             │
└─────────────────────────────────────────────────────────────┘
       │
       ▼
┌─────────────────────────────────────────────────────────────┐
│                      MCP Integrations                       │
│   Klaviyo · Ahrefs · Similarweb · Amplitude · Supermetrics  │
│   Slack · Canva · Figma · Notion                            │
└─────────────────────────────────────────────────────────────┘
```

### Skills

7 user-invocable skills + 1 background reference skill.

#### `/brand-review` — Brand Setup & Review
Two modes. **Setup**: guides you through creating brand voice, product catalog (with product profile), and customer profiles (with buyer psychology) — saves to `brand/` directory. **Review**: audits content against those files for voice consistency, terminology, messaging alignment, proof-to-psychology match, and DTC compliance (FTC influencer disclosure, subscription language, health/beauty claims).

#### `/campaign-plan` — Campaign Planning with Promo Economics
Generates a campaign brief with DTC channel strategy (storefront-first), promo calendar framework (offer hierarchy adapted by product type, hero SKU protection, no-promo zones), audience psychology and channel implications, execution checklists (before/during/after), and pre-committed kill thresholds. Supports standard promos, seasonal tentpoles, product launches, off-season campaigns, and sport/activity season launches. Includes optional inline competitive context.

#### `/draft-content` — DTC Content Drafting
Writes product descriptions, ad creative (5 frameworks with hook variants and framework prioritization by product type), collection page copy, social posts (Instagram/TikTok/Pinterest first), email/SMS copy, gift guides, influencer briefs, and product launch announcements. Adapts messaging across 5 audience segments (primary buyer, gift-giver, VIP, lapsed, cold prospect) — shifting all 4 messaging layers, not just the hook.

#### `/email-sequence` — Email + SMS Retention Flows
Designs and drafts 12 DTC lifecycle flows: welcome, abandoned cart, post-purchase, browse abandonment, win-back, VIP, back-in-stock, price drop, replenishment, review request, referral, birthday. Every email has an SMS variant. Adapts by product type (flow applicability matrix — skip replenishment for durable goods, skip birthday for non-lifestyle brands) and buyer psychology (research-mode cart recovery vs. impulse reminder). Includes promo psychology rules (buyer's remorse protection, discount escalation trap, VIP paradox).

#### `/competitive-brief` — DTC Competitive Intelligence
Researches competitors through DTC-relevant sources: Meta Ad Library, influencer analysis, storefront teardowns, pricing/promo strategy, social presence, review sentiment. Includes category position analysis — for category creators with no direct competitors, analyzes substitute solutions and workarounds instead of head-to-head brand comparison. Outputs positioning gaps, content opportunities, and promo intelligence.

#### `/performance-report` — Contribution-Margin-First Reporting
North star: incremental contribution margin. Core KPI stack, 7-signal promo health check, discount penetration guardrails. Four report types: promo post-mortem, paid acquisition, retention/lifecycle, and seasonal YoY. Includes seasonal business adjustments (season-over-season baselines), new brand / no-baseline protocol, cohort segmentation by acquisition psychology (full-price vs. discount-acquired vs. gift-received), and DTC attribution guidance.

#### `/seo-audit` — SEO Audit with E-Commerce Focus
Keyword research, on-page analysis, content gaps, technical SEO, and competitor comparison — with DTC-specific additions: product page SEO, collection page taxonomy, Google Shopping structured data, high-intent keyword patterns, and novel product / category-creating keyword strategy (target the problem when the product name has no search volume).

#### `content-creation` — Background Reference Skill
Always-on knowledge layer. DTC content templates, ad creative frameworks, headline/hook formulas, brand energy matching (technical/understated, warm/community, bold/disruptive, luxe/elevated), SEO fundamentals, and CTA guidance. Not called directly — loaded automatically when content is being written.

---

### How Skills Work Together

#### Campaign / Seasonal Promo

```
1. /campaign-plan (with inline competitive context + promo economics)
   → strategy, offer, audience, calendar, kill thresholds, margin targets
2. PARALLEL:
   a. /draft-content → ad copy, product pages, social, gift guides
   b. /email-sequence → retention flows + promo-specific email/SMS
3. /brand-review → QA all content (voice, claims, proof-to-psychology match)
4. LAUNCH → daily check-ins (conversion, AOV, CAC, margin, SKU mix)
5. /performance-report → post-mortem within 7 days
```

#### Ongoing Content Operations

```
1. /seo-audit → keyword and content gaps
2. /draft-content → fill gaps
3. /brand-review → QA
4. /performance-report → monthly reporting
```

#### Competitive Deep-Dive

```
1. /competitive-brief → full DTC competitor teardown (or substitute analysis for category creators)
2. /campaign-plan → apply insights to strategy
```

Key principle: content, ads, and email/SMS flows are built **in parallel**, not sequentially. They all need to be ready for the same launch date.

---

## Commands

| Command | What It Does |
|---|---|
| `/brand-review` | Set up brand voice/products/customers (with buyer psychology), or review content against them |
| `/campaign-plan` | Campaign brief with promo economics, product-type offers, audience psychology, execution checklist |
| `/draft-content` | Product descriptions, ad copy (audience-adaptive), social posts, gift guides, influencer briefs |
| `/email-sequence` | Email + SMS flows — adapted by product type and buyer psychology, with promo safety rules |
| `/competitive-brief` | Competitor research — ads, pricing, influencers, storefront, category position analysis |
| `/performance-report` | Performance reports — contribution margin, promo post-mortem, seasonal adjustments, cohort psychology |
| `/seo-audit` | SEO audit — keywords, on-page, product page SEO, novel product strategy, content gaps |

## Configuration

### Brand Setup

Run `/brand-review setup` to populate the `brand/` directory. This creates your brand voice, product profile, product catalog, buyer psychology profiles, and customer language bank. All skills reference these files automatically.

### MCP Integrations

> See [CONNECTORS.md](CONNECTORS.md) for the full connector reference.

| Integration | Used By |
|---|---|
| **Klaviyo** | `/email-sequence`, `/performance-report` — email/SMS flows, retention metrics |
| **Ahrefs** | `/seo-audit`, `/competitive-brief` — keyword research, backlink analysis |
| **Similarweb** | `/seo-audit`, `/competitive-brief` — traffic analysis, competitor benchmarking |
| **Amplitude** | `/performance-report` — product analytics, user behavior |
| **Supermetrics** | `/performance-report` — cross-platform marketing data |
| **Notion** | All skills — briefs, style guides, campaign docs |
| **Slack** | All skills — share drafts, reports, briefs with team |
| **Canva** | `/draft-content`, `/campaign-plan` — design assets |
| **Figma** | `/draft-content`, `/brand-review` — design files, brand assets |

## Testing

The `tests/` directory contains the evaluation framework used to validate skill quality:

- `TEST-PLAN.md` — 3-layer test plan (new user flow, unit tests, regression)
- `EVAL-RUBRIC.md` — 5-dimension scoring rubric (Brand Fidelity, Strategic Soundness, Specificity, Completeness, Adaptability)
- `tests/tern/` — full test suite using a non-beauty brand (Tern, winter sport accessories) to stress-test templates beyond the default consumable/subscription assumptions

The Tern test suite covers edge cases like single-product brands, off-season campaigns, gift-giver audiences, durable goods post-purchase flows, no-baseline reporting, category creation with no direct competitors, and novel products with no search volume.
