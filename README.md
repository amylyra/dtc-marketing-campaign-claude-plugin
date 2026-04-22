# Marketing Knowledgebase Plugin

A DTC marketing plugin for Claude Code and Claude.ai. Campaign planning with promo economics, email/SMS retention flows, ad creative drafting, brand voice management, competitive intelligence, SEO audits, and performance reporting — all built around contribution margin as the north star.

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
  products.md    — hero SKUs, prices, claims, ingredients, differentiators
  customers.md   — segments, purchase motivations, review language, objections
```

Run `/brand-review setup` to fill these in. Once populated, every skill auto-applies brand voice, product details, and customer language. No re-entering context each time.

### Skill Map

```
┌─────────────────────────────────────────────────────────────┐
│                       brand/ directory                       │
│         voice.md · products.md · customers.md                │
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
Two modes. **Setup**: guides you through creating brand voice, product catalog, and customer profiles — saves to `brand/` directory. **Review**: audits content against those files for voice consistency, terminology, messaging alignment, and DTC compliance (FTC influencer disclosure, subscription language, health/beauty claims).

#### `/campaign-plan` — Campaign Planning with Promo Economics
Generates a campaign brief with DTC channel strategy (storefront-first → paid → email/SMS → organic → influencer), promo calendar framework (offer hierarchy, hero SKU protection, no-promo zones), execution checklists (before/during/after), and pre-committed kill thresholds. Includes optional inline competitive context.

#### `/draft-content` — DTC Content Drafting
Writes product descriptions, ad creative (5 frameworks with hook variants), collection page copy, social posts (Instagram/TikTok/Pinterest first), email/SMS copy, gift guides, influencer briefs, and product launch announcements. Pulls from brand/ for voice and product knowledge.

#### `/email-sequence` — Email + SMS Retention Flows
Designs and drafts DTC lifecycle flows: welcome, abandoned cart, post-purchase, browse abandonment, win-back, VIP, back-in-stock, price drop, replenishment, review request, referral, birthday. Every email has an SMS variant. Includes post-purchase framework, Klaviyo-specific guidance, and DTC benchmarks.

#### `/competitive-brief` — DTC Competitive Intelligence
Researches competitors through DTC-relevant sources: Meta Ad Library, influencer analysis, storefront teardowns, pricing/promo strategy, social presence, review sentiment. Outputs positioning gaps, content opportunities, and promo intelligence that feeds directly into `/campaign-plan`.

#### `/performance-report` — Contribution-Margin-First Reporting
North star: incremental contribution margin. Core KPI stack, 7-signal promo health check, discount penetration guardrails. Four report types: promo post-mortem, paid acquisition, retention/lifecycle, and seasonal YoY. Includes DTC attribution guidance for the post-iOS14 landscape.

#### `/seo-audit` — SEO Audit with E-Commerce Focus
Keyword research, on-page analysis, content gaps, technical SEO, and competitor comparison — with DTC-specific additions: product page SEO, collection page taxonomy, Google Shopping structured data, and high-intent keyword patterns ("best X for Y", "X vs Y").

#### `content-creation` — Background Reference Skill
Always-on knowledge layer. DTC content templates, ad creative frameworks, headline/hook formulas, SEO fundamentals, and CTA guidance. Not called directly — loaded automatically when content is being written.

---

### How Skills Work Together

#### Campaign / Seasonal Promo

```
1. /campaign-plan (with inline competitive context + promo economics)
   → strategy, offer, audience, calendar, kill thresholds, margin targets
2. PARALLEL:
   a. /draft-content → ad copy, product pages, social, gift guides
   b. /email-sequence → retention flows + promo-specific email/SMS
3. /brand-review → QA all content
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
1. /competitive-brief → full DTC competitor teardown
2. /campaign-plan → apply insights to strategy
```

Key principle: content, ads, and email/SMS flows are built **in parallel**, not sequentially. They all need to be ready for the same launch date.

---

## Commands

| Command | What It Does |
|---|---|
| `/brand-review` | Set up brand voice/products/customers, or review content against them |
| `/campaign-plan` | Campaign brief with promo economics, channels, calendar, execution checklist |
| `/draft-content` | Product descriptions, ad copy, social posts, gift guides, influencer briefs |
| `/email-sequence` | Email + SMS flows — welcome, abandoned cart, post-purchase, win-back, etc. |
| `/competitive-brief` | Competitor research — ads, pricing, influencers, storefront, social |
| `/performance-report` | Performance reports — contribution margin, promo post-mortem, paid, retention |
| `/seo-audit` | SEO audit — keywords, on-page, product page SEO, content gaps, technical |

## Configuration

### Brand Setup

Run `/brand-review setup` to populate the `brand/` directory. This creates your brand voice, product catalog, and customer profiles. All skills reference these files automatically.

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
