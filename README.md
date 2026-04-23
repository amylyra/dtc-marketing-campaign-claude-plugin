# Marketing Knowledgebase Plugin

A DTC marketing plugin for Claude Code and Claude.ai. Campaign planning with promo economics, email/SMS retention flows, ad creative drafting, brand voice management, competitive intelligence, SEO audits, and performance reporting — all built around contribution margin as the north star.

Works across product types (consumable, durable goods, fashion, subscription), audience segments (self-purchase, gift-giver, VIP, lapsed, cold prospect), and category positions (established, challenger, category creator).

## Getting Started

### First-Time Setup

```
1. /brand-review setup       → brand voice, products, customer profiles (foundation)
2. /competitive-brief        → competitor research (optional, saves to research/)
   /seo-audit                → keyword & content gaps (optional, saves to research/)
3. /campaign-plan            → 3 theme options → lock strategy → site assets → channels
                               (saves brief to campaigns/ — downstream skills auto-load it)
4. /draft-content            → brainstorm creative concepts, write channel copy
   /email-sequence           → build promo/lifecycle flows (arc-aware)
5. /brand-review             → QA against brand + campaign brief + engagement standards
6. /performance-report       → post-mortem (auto-loads brief for actuals vs targets)
```

Step 1 is the foundation — every skill reads from `brand/`. Steps 2-6 are connected: research feeds strategy, strategy feeds creative, creative gets QA'd, results close the loop.

The `brand/` templates include a worked example (Glow Lab skincare) to show what "done" looks like. Delete the examples and fill in your own brand.

---

## Architecture

### Shared Context: Three Directories

Skills share context through three directories. Each is optional but compounds quality:

```
brand/                           ← Foundation (created by /brand-review setup)
  voice.md                         personality, voice attributes, tone by channel, terminology
  products.md                      product profile, hero SKUs, prices, claims, differentiators
  customers.md                     segments, buyer psychology, language bank, objections

research/                        ← Research (created by /competitive-brief, /seo-audit)
  competitive-[name].md            competitor gaps, ad patterns, positioning opportunities
  seo-[topic].md                   keyword targets, content gaps, on-page priorities

campaigns/                       ← Campaign briefs (created by /campaign-plan)
  [campaign-slug].md               locked theme, arc, audience, offer, creative direction, KPIs
```

`brand/` is the foundation — every skill reads from it. `research/` and `campaigns/` are the connective tissue — they pass context between skills so the user never re-explains.

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

### Skill Map & Data Flow

```
┌─────────────────────────────────────────────────────────────┐
│                       brand/ directory                       │
│   voice.md · products.md (profile) · customers.md (psych)   │
│            (foundation — every skill reads)                  │
└───────────────────────────┬─────────────────────────────────┘
                            │
  [Research]                │              [Plan]
  /competitive-brief ──saves──→ research/     │
  /seo-audit ─────────saves──→ research/     │
                            │                │
                            ▼                ▼
                     /campaign-plan ←── loads research/
                            │
                       saves brief
                            │
                            ▼
                       campaigns/
                            │
              ┌─────────────┼─────────────┐
              ▼             ▼             ▼
  [Execute]              [Execute]     [QA]
  /draft-content         /email-       /brand-review
  (loads brief +          sequence     (loads brief +
   research,             (loads brief,  brand, checks
   brainstorms            arc-aware     engagement)
   concepts)              sends)
                                          │
                            ┌─────────────┘
                            ▼
                     [Measure]
                     /performance-report
                     (loads brief for
                      actuals vs targets)

  ┌───────────────────────────────────────────────────────────┐
  │  content-creation (background) · MCP integrations         │
  │  Klaviyo · Ahrefs · Similarweb · Amplitude · Figma · etc  │
  └───────────────────────────────────────────────────────────┘
```

### Skills

7 user-invocable skills + 1 background reference skill.

#### `/brand-review` — Brand Setup & Content QA
Two modes. **Setup**: guides you through creating brand voice, product catalog (with product profile), and customer profiles (with buyer psychology) — saves to `brand/` directory. **Review**: audits content against brand files + campaign brief (if exists) for voice consistency, terminology, messaging alignment, proof-to-psychology match, engagement quality (hook strength, competitive distinctiveness, persuasion structure), and DTC compliance (FTC influencer disclosure, subscription language, health/beauty claims).

#### `/campaign-plan` — Stepped Campaign Planning
Plans a campaign in 4 conversational steps. Auto-loads research from `research/` if available. (1) **Strategy** — presents 3 theme options (Brand Story, Sharp Edge, Pattern Interrupt) with sample hooks, "why this works," narrative arc, and competitive context. User picks/iterates until locked. (2) **Site creative assets** — tiered checklist with brand-specific copy direction. (3) **Channels + calendar** — tiered channels with creative direction per concept (angle + arc phase) + milestone timeline. (4) **Metrics + execution** — KPIs, risks, checklist, then saves campaign brief to `campaigns/` with a specific handoff menu of concepts to draft next.

#### `/draft-content` — DTC Content Drafting
Auto-loads campaign brief from `campaigns/` and research from `research/`. For ad creative: brainstorms 3-5 creative concepts before writing (seeded from campaign brief's creative direction), user picks which to develop. Writes with copy quality standards: hook pattern interrupt test, variant diversity (4+ angles per 5+ set), swap test, persuasion signals. Adapts messaging across 5 audience segments, all 4 messaging layers. 9 content types including product descriptions, ad creative (5 frameworks), social posts, email/SMS, gift guides, influencer briefs.

#### `/email-sequence` — Email + SMS Retention Flows
Auto-loads campaign brief — matches each send to the campaign's narrative arc phase (educate/prove/convert). 12 DTC lifecycle flows with product-type adaptation (skip replenishment for durable goods, skip birthday for non-lifestyle brands). Promo psychology rules (buyer's remorse protection, discount escalation trap, VIP paradox). Every email has an SMS variant.

#### `/competitive-brief` — DTC Competitive Intelligence
Researches competitors through DTC-relevant sources: Meta Ad Library, influencer analysis, storefront teardowns, pricing/promo strategy, social presence, review sentiment. **Saves findings to `research/`** — auto-loaded by `/campaign-plan` for richer theme options and by `/draft-content` for competitive distinctiveness. Includes category position analysis for brands with no direct competitors.

#### `/performance-report` — Contribution-Margin-First Reporting
Auto-loads campaign brief to compare actuals against planned KPIs, kill thresholds, and budget allocation. North star: incremental contribution margin. 7-signal promo health check, seasonal adjustments, new-brand/no-baseline protocol, cohort psychology segmentation.

#### `/seo-audit` — SEO Audit with E-Commerce Focus
Keyword research, on-page analysis, content gaps, technical SEO, competitor comparison. **Saves findings to `research/`** — auto-loaded by `/draft-content` for keyword targeting in web content. DTC-specific: product page SEO, novel product keyword strategy (target the problem when the product name has no search volume).

#### `content-creation` — Background Reference Skill
Always-on knowledge layer. DTC content templates, ad creative frameworks, brand energy matching, SEO fundamentals, CTA guidance. Not called directly — loaded automatically when content is being written.

---

### How Skills Work Together

#### Full Campaign Pipeline (connected)

```
1. /competitive-brief → saves to research/ (optional but enriches everything)
   /seo-audit         → saves to research/ (optional)
2. /campaign-plan     → loads research/, 3 theme options, lock strategy
                        → saves brief to campaigns/
3. PARALLEL:
   a. /draft-content   → loads campaigns/ + research/, brainstorms concepts, writes copy
   b. /email-sequence  → loads campaigns/, arc-aware promo sends
4. /brand-review      → QA against brand/ + campaigns/ + engagement standards
5. LAUNCH → daily check-ins
6. /performance-report → loads campaigns/ brief, actuals vs planned KPIs
```

#### Ongoing Content Operations

```
1. /seo-audit     → keyword and content gaps (saves to research/)
2. /draft-content → fill gaps (loads research/ for keyword targeting)
3. /brand-review  → QA
4. /performance-report → monthly reporting
```

Key principle: **saved context compounds quality.** Each skill produces better output when research, campaign briefs, and brand context are available. No skill requires another to run, but the pipeline is strongest when connected.

---

## Commands

| Command | What It Does | Saves To |
|---|---|---|
| `/brand-review setup` | Brand voice, products, customers with buyer psychology | `brand/` |
| `/brand-review` | QA content — voice, claims, engagement quality, campaign alignment | — |
| `/competitive-brief` | Competitor research — ads, pricing, positioning gaps | `research/` |
| `/seo-audit` | SEO audit — keywords, content gaps, on-page priorities | `research/` |
| `/campaign-plan` | 3 theme options → strategy → site assets → channels → metrics | `campaigns/` |
| `/draft-content` | Creative concept brainstorm → channel copy (loads brief + research) | — |
| `/email-sequence` | Email + SMS flows — arc-aware, product-type adapted (loads brief) | — |
| `/performance-report` | Post-mortem — actuals vs planned KPIs (loads brief) | — |

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
- `EVAL-RUBRIC.md` — 6-dimension scoring rubric (Brand Fidelity, Strategic Soundness, Specificity, Completeness, Engagement & Persuasion, Adaptability)
- `tests/tern/` — full test suite using a non-beauty brand (Tern, winter sport accessories) to stress-test templates beyond the default consumable/subscription assumptions

The Tern test suite covers edge cases like single-product brands, off-season campaigns, gift-giver audiences, durable goods post-purchase flows, no-baseline reporting, category creation with no direct competitors, and novel products with no search volume.
