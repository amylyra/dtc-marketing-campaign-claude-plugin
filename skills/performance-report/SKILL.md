---
name: performance-report
description: Build a marketing performance report with contribution margin analysis, promo post-mortems, paid acquisition metrics, and retention cohort tracking. Use when wrapping a promo, preparing weekly or monthly reports, or when you need data translated into an executive summary with next-period priorities.
argument-hint: "<time period or campaign>"
---

# Performance Report

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../../CONNECTORS.md).

Generate a DTC marketing performance report centered on contribution margin, with channel deep-dives, promo post-mortems, and actionable next-period priorities.

## Core Philosophy

The north star metric is **incremental contribution margin** — not revenue, not GMV, not ROAS.

Contribution margin = Revenue minus discount minus COGS minus shipping minus payment fees minus variable fulfillment minus promo-attributable paid media, measured against a counterfactual baseline (trailing 4-week trend-adjusted, or holdout group).

If you only measure one thing, measure this.

## Trigger

User runs `/performance-report` or asks for a marketing report, performance analysis, campaign results, promo post-mortem, or metrics summary.

## Inputs

1. **Report type** — determine which type of report the user needs:
   - **Promo post-mortem** — analysis of a specific promotion's performance
   - **Weekly/monthly summary** — cross-channel performance overview
   - **Paid acquisition deep-dive** — paid media performance and efficiency
   - **Retention/lifecycle report** — email, SMS, cohort retention, and subscription metrics
   - **Seasonal comparison (YoY)** — this period vs same period last year

2. **Time period** — dates or campaign name

3. **Data sources**:
   - If ~~marketing analytics is connected, discover what accounts and platforms are available, then pull performance data automatically
   - If ~~product analytics is connected: pull performance data automatically
   - What else is connected (Klaviyo, Amplitude, Supermetrics, etc.)
   - If not connected: ask the user to provide metrics. Prompt with: "Please paste or share your performance data. I can work with spreadsheets, CSV data, dashboard screenshots described in text, or just the key numbers."

4. **Comparison baseline** — prior period, same period last year, or counterfactual

### Brand Context

If `brand/` directory exists, auto-apply:
- **`brand/products.md`** — reference product names, price points, and margin structure when analyzing revenue, AOV, and contribution margin
- **`brand/customers.md`** — segment performance by customer profiles (primary buyer, gift-giver, VIP, lapsed) rather than generic new/returning splits
- **`brand/voice.md`** — no direct impact on reporting, but reference brand messaging pillars when evaluating content-driven metrics (email subject line performance, ad creative hooks)

## Core KPI Stack

Track only these — more creates noise without insight:

| Metric | What It Measures |
|--------|-----------------|
| Net sales | Top-line revenue after returns |
| Gross margin dollars | Revenue minus COGS |
| **Contribution margin after discount + media** | **The north star** |
| Conversion rate | Visitors to buyers |
| AOV | Average order value |
| CAC / CPA | Cost to acquire a customer |
| New vs returning customer mix | Acquisition vs retention balance |
| Repeat purchase rate (60-day, 180-day by cohort) | Customer stickiness |
| Email/SMS revenue per recipient | Owned channel efficiency |
| Post-promo hangover: sales 7-14 days after | Whether the promo borrowed from future demand |

## Annualized Guardrails

Always check these structural health indicators:

- **Discount penetration** (% of revenue sold at any discount): Healthy = 15-25%. Above 35% = structural problem.
- **Full-price velocity between promos**: If trending down, you are training the customer base to wait for discounts.

## 7-Signal Promo Health Check

All seven must be true for a promo to be "good":

| Signal | What "good" looks like |
|--------|----------------------|
| Net revenue | Up vs counterfactual baseline |
| Margin dollars | Up, not just revenue |
| AOV | Held or increased |
| CAC / CPA | Within acceptable range |
| New-customer LTV | Cohort not degrading vs full-price cohorts |
| Repeat behavior | Not worsening |
| Post-promo sales | No 30%+ trough in the 2-4 weeks after |

If revenue spiked but any of these broke, the promo was mediocre. You bought a spike with margin, LTV, or future demand.

## Report Sub-Types

### Promo Post-Mortem (within 7 days of promo end)

One-page format:

1. **Hypothesis**: What we expected and why
2. **Result vs baseline**: Counterfactual comparison (not vs zero)
3. **Result vs forecast**: Did it beat projections?
4. **Contribution margin**: The actual number
5. **Who bought**: By cohort (new/returning/lapsed), channel, segment
6. **14-day hangover check**: Sales in 2 weeks post-promo vs trailing baseline
7. **Verdict**: Repeat, revise, or kill
8. **What we'd change**: Specific adjustments for next time

This is the compounding asset. Brands that do this for two years have a structural advantage.

### Paid Acquisition Report

- ROAS by platform (Meta, Google, TikTok, Pinterest)
- CAC by platform
- Creative performance: Which ad concepts/hooks are winning, which are fatiguing
- Audience performance: Which targeting/segments are winning
- Spend efficiency curve: At what spend level do returns diminish?
- New customer acquisition rate by platform
- **Blended MER** (Marketing Efficiency Ratio = total revenue / total ad spend) — the real north star for paid, given iOS14+ attribution limitations

### Retention / Lifecycle Report

- Email flow performance by flow type (welcome, abandoned cart, post-purchase, win-back)
- SMS flow performance
- List growth (net new subscribers minus unsubscribes)
- Revenue per recipient (email and SMS)
- Cohort retention curves: 30/60/90/180-day repurchase rates by acquisition source
- Repeat purchase rate trends
- Subscription metrics (if applicable): active subscribers, churn rate, MRR

### Seasonal YoY Comparison

- This period vs same period last year (e.g., BFCM 2025 vs BFCM 2024)
- Revenue, AOV, conversion rate, new customers, discount depth
- What changed in strategy and what impact it had
- Channel mix shift and its effect

## DTC Attribution Guidance

Include this context in every report that touches paid media:

- **Platform-reported ROAS is unreliable post-iOS14/ATT** — Meta and TikTok over-report, Google may under-report
- **Blended MER** (total revenue / total ad spend) is the pragmatic north star
- **Incrementality testing**: holdout tests, geo-lift tests, media mix modeling for brands at scale
- **Last-click attribution** undervalues top-of-funnel; view-through attribution overvalues it
- **The honest answer**: precise attribution is impossible at most DTC scale. Focus on directional trends and contribution margin.

## Channel-Specific Metrics

### Email Marketing

| Metric | What It Measures | Benchmark |
|--------|-----------------|-----------|
| Revenue per recipient | Email program efficiency | $0.05-0.15/recipient/month |
| Flow revenue vs campaign revenue | Automation health | Flows should be 30-50% of email revenue |
| List growth rate | Audience building | 3-5% net growth/month |
| Deliverability | Sender health | >97% delivery rate |
| Unsubscribe rate | Content relevance | <0.3% per send |

### SMS Marketing

| Metric | What It Measures | Benchmark |
|--------|-----------------|-----------|
| Revenue per recipient | SMS program efficiency | $0.02-0.08/recipient/month |
| CTR | Message relevance | 8-15% for triggered, 3-6% for campaigns |
| Opt-out rate | Frequency/relevance | <1% per send |
| Subscriber growth | SMS list building | SMS list typically 30-50% of email list |

### Paid Social (Meta, TikTok)

| Metric | What It Measures | Benchmark |
|--------|-----------------|-----------|
| ROAS | Return on ad spend | 2-4x for prospecting, 5-10x for retargeting |
| CPA / CAC | Cost to acquire | Varies by AOV; target CPA < 30% of first-order AOV |
| CTR | Creative relevance | >1% for feed, >0.5% for stories |
| Frequency | Ad fatigue | <3 for prospecting, <5 for retargeting per 7 days |
| Hook rate (video) | Creative stopping power | >25% 3-second view rate |
| Thumbstop ratio | Scroll-stopping ability | >20% for strong creative |

### Organic Social

| Metric | What It Measures | Benchmark |
|--------|-----------------|-----------|
| Engagement rate | Content resonance | 2-5% for Instagram, 3-8% for TikTok |
| Follower growth | Audience building | 2-5% monthly |
| Save rate | Content value | >2% is strong |
| Share rate | Virality potential | >1% is strong |
| Profile visits from content | Discovery | Trending up = content is working |

### SEO / Organic Search

| Metric | What It Measures | Benchmark |
|--------|-----------------|-----------|
| Organic sessions | SEO health | Trending up month over month |
| Keyword rankings | Search visibility | Track top 20 product and category keywords |
| Organic conversion rate | Traffic quality | 1-3% for product pages |
| Branded vs non-branded traffic | Brand awareness | Growing non-branded = SEO working |

## Output Format

Present as a structured report with:

1. **Executive summary** (3-5 bullet points, biggest wins and misses)
2. **Core metrics dashboard** (table with current, prior period, change %)
3. **Deep-dive by report type** (detailed analysis per section above)
4. **Guardrail check** (discount penetration, full-price velocity)
5. **Recommendations** (prioritized, specific, actionable — not vague)
6. **Next period priorities** (what to test, change, or double down on)

## After the Report

Ask: "Would you like me to:
- Dig deeper into any channel or metric?
- Compare against a different time period?
- Generate a promo post-mortem for a specific campaign?
- Build a forecast for next period based on these trends?"
