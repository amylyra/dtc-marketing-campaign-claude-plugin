# Marketing Knowledgebase Plugin

A marketing plugin for Claude Code and Claude.ai. Content creation, campaign planning, brand voice management, competitive analysis, SEO, and performance reporting — all from the command line or chat.

## Architecture

### Overview

This plugin is built around **8 skills** that Claude loads as domain knowledge. There are no separate background agents — Claude itself orchestrates the work, with each skill acting as a specialized instruction set that shapes how Claude reasons and responds for a given task.

```
┌─────────────────────────────────────────────────────────────┐
│                        User Request                         │
└───────────────────────────┬─────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                     Claude (Orchestrator)                    │
│   Routes to the right skill(s) based on the command or      │
│   intent. Skills can be chained across a single workflow.   │
└──────┬──────────┬──────────┬──────────┬──────────┬──────────┘
       │          │          │          │          │
       ▼          ▼          ▼          ▼          ▼
  /draft-    /campaign-  /brand-   /seo-audit  /email-
  content      plan      review               sequence
       │          │          │
       ▼          ▼          ▼
  /competitive-          /performance-
     brief                 report
       │
       ▼
┌─────────────────────────────────────────────────────────────┐
│               content-creation (background skill)           │
│   Always-on reference layer: templates, SEO rules,          │
│   headline formulas, CTA frameworks, channel formatting.    │
│   Used automatically by draft-content and other skills.     │
└─────────────────────────────────────────────────────────────┘
       │
       ▼
┌─────────────────────────────────────────────────────────────┐
│                      MCP Integrations                       │
│  HubSpot · Klaviyo · Ahrefs · Amplitude · Supermetrics      │
│  Notion · Slack · Canva · Figma · Similarweb                │
└─────────────────────────────────────────────────────────────┘
```

### Skills

There are 7 user-invocable skills (triggered by slash commands) and 1 background reference skill.

#### `/draft-content` — Content Drafting
Writes marketing content tailored to channel, audience, and brand voice. Supports blog posts, social media, email newsletters, landing pages, press releases, and case studies. Generates multiple headline options, applies SEO guidance, and formats output for the target platform. Automatically pulls from the `content-creation` reference skill for templates and channel-specific rules.

#### `/campaign-plan` — Campaign Planning
Takes a marketing goal and turns it into a full campaign brief: objectives, audience segmentation, key messages, channel strategy, a week-by-week content calendar with dependencies, budget allocation guidance, and KPIs. Designed for product launches, lead-gen pushes, and awareness campaigns.

#### `/brand-review` — Brand Voice Review
Audits content against your brand voice, style guide, and messaging pillars. Flags deviations by severity (high / medium / low) and provides before/after rewrites for the top issues. Also runs legal and compliance checks regardless of whether brand guidelines are configured — flagging unsubstantiated claims, missing disclaimers, comparative claims, and testimonial issues.

#### `/competitive-brief` — Competitive Analysis
Researches competitors and produces a structured comparison of positioning, messaging, content strategy, and market presence. Identifies content gaps, unclaimed positioning angles, and threats. Can generate sales battlecards and summarize competitor moves.

#### `/seo-audit` — SEO Audit
Runs a comprehensive SEO audit covering keyword research, on-page analysis, content gaps, technical checks, and competitor comparison. Connects to Ahrefs and Similarweb when available. Outputs a prioritized action plan split into quick wins and strategic investments.

#### `/email-sequence` — Email Sequence Design
Designs and drafts complete multi-email sequences with full copy, send timing, branching logic, exit conditions, and performance benchmarks. Covers onboarding, lead nurture, re-engagement, win-back, and product launch flows. Generates a flow diagram and A/B test recommendations. Connects to Klaviyo when available.

#### `/performance-report` — Performance Reporting
Builds marketing performance reports for campaigns, channels, or time periods. Pulls data from Amplitude, Supermetrics, and HubSpot when connected. Outputs a structured report with metrics, trend analysis, wins and misses, and prioritized recommendations. Can generate executive summaries for stakeholders.

#### `content-creation` — Background Reference Skill (not user-invocable)
An always-on knowledge layer that other skills draw on automatically. Contains content type templates, writing best practices by channel, SEO fundamentals, headline formulas, CTA frameworks, and channel-specific formatting rules. Never called directly — loaded by Claude whenever content is being written.

---

### How Skills Work Together

Skills are designed to chain across a marketing workflow. A typical product launch might flow like this:

```
1. /competitive-brief   → understand the market landscape before planning
2. /campaign-plan       → build the campaign brief with positioning informed by research
3. /draft-content       → write the content assets defined in the campaign calendar
4. /brand-review        → QA each draft against voice and compliance standards
5. /email-sequence      → build the nurture flow that runs alongside the campaign
6. /performance-report  → wrap the campaign with a metrics summary and next steps
```

Or for ongoing content operations:

```
1. /seo-audit           → find keyword and content gaps to prioritize
2. /draft-content       → fill those gaps with optimized content
3. /brand-review        → QA before publishing
4. /performance-report  → track what's working each month
```

Claude maintains context across the conversation, so outputs from one skill (e.g. the audience and messaging from `/campaign-plan`) automatically inform the next (e.g. `/draft-content` or `/email-sequence`) without re-entering information.

---

## Commands

| Command | Description |
|---|---|
| `/draft-content` | Draft blog posts, social media, email newsletters, landing pages, press releases, and case studies |
| `/campaign-plan` | Generate a full campaign brief with objectives, channels, content calendar, and success metrics |
| `/brand-review` | Review content against your brand voice, style guide, and messaging pillars |
| `/competitive-brief` | Research competitors and generate a positioning and messaging comparison |
| `/performance-report` | Build a marketing performance report with key metrics, trends, and optimization recommendations |
| `/seo-audit` | Run a comprehensive SEO audit — keyword research, on-page analysis, content gaps, technical checks, and competitor comparison |
| `/email-sequence` | Design and draft multi-email sequences for nurture flows, onboarding, drip campaigns, and more |

## Example Workflows

### Drafting a Blog Post

```
> /draft-content
Type: blog post
Topic: How AI is transforming B2B marketing
Audience: Marketing directors at mid-market SaaS companies
Key messages: AI saves time on repetitive tasks, improves personalization, requires human oversight
Tone: Authoritative but approachable
Length: 1200 words
```

Claude generates a structured blog post with an engaging headline, introduction with a hook, organized sections, SEO-optimized subheadings, and a clear call to action.

### Planning a Campaign

```
> /campaign-plan
Goal: Drive 500 signups for our new product launch
Audience: Technical decision-makers at enterprise companies
Timeline: 6 weeks
Budget range: $20,000-$30,000
```

Claude produces a campaign brief covering objectives, audience segmentation, key messages, channel strategy, a week-by-week content calendar, and KPIs.

### Reviewing Content Against Brand Guidelines

```
> /brand-review
[paste your draft content]
```

If your brand style guide is configured in local settings, Claude checks content against voice, tone, terminology, and messaging pillars. If not configured, Claude asks about your guidelines or provides a generic review for clarity, consistency, and professionalism.

## Configuration

Configure your brand voice, style guide, and target personas in a local settings file for personalized output. This allows commands like `/draft-content` and `/brand-review` to automatically apply your brand standards without prompting each time.

## MCP Integrations

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](CONNECTORS.md).

| Integration | Used By |
|---|---|
| **HubSpot** | `/campaign-plan`, `/performance-report` — campaign data, contacts, marketing automation |
| **Klaviyo** | `/email-sequence` — draft and send email sequences and campaigns |
| **Ahrefs** | `/seo-audit` — keyword research, backlink analysis, site audits |
| **Similarweb** | `/seo-audit`, `/competitive-brief` — traffic analysis, market benchmarking |
| **Amplitude** | `/performance-report` — product analytics and user behavior data |
| **Supermetrics** | `/performance-report` — cross-platform marketing data aggregation |
| **Notion** | All skills — access briefs, style guides, and campaign documents |
| **Slack** | All skills — share drafts, reports, and briefs with your team |
| **Canva** | `/draft-content`, `/campaign-plan` — create and edit design assets |
| **Figma** | `/draft-content`, `/brand-review` — access design files and brand assets |
