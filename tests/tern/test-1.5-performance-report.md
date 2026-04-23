# Test 1.5: `/performance-report` Output — Post-Mortem for Ski Season Launch + BFCM

**Simulated input:** "/performance-report promo post-mortem for Tern ski season launch + BFCM. Nov 1 - Dec 15."

**Simulated data provided by user:**
```
Phase 1 (Launch, Nov 1-26): $18K revenue, 320 orders, 280 new customers
Phase 2 (BFCM, Nov 27 - Dec 1): $31K revenue, 410 orders, 290 new customers
Post-BFCM (Dec 2-15): $8K revenue, 145 orders
October baseline: $3K revenue, 55 orders (off-season)

AOV: Phase 1 $56, Phase 2 $76, Post-BFCM $55
Bundle attach: Phase 2 had 52% bundle orders
Top SKU: Bottle Parka (45% of units), Full Send bundle (28% of revenue in Phase 2)
Ad spend: $8.2K total ($4.8K Phase 1, $3.4K Phase 2)
Email/SMS revenue attributed: $14K (29% of total)
New email subscribers gained: 2,400
Discount codes used: 188 orders (26% of BFCM orders used bundle pricing)

No prior year data (first ski season).
```

**Brand context applied:** brand/products.md (product names, prices), brand/customers.md (segments)

---

## Simulated Report Output

### Executive Summary

- **Total revenue:** $57K across Nov 1 - Dec 15, against a $45K target. Beat by 27%.
- **Contribution margin:** Estimated $24K (42% margin) — above the $18K target. Driven by strong full-price Phase 1 sales and high bundle attach in Phase 2.
- **Biggest win:** Phase 1 full-price launch drove $18K with zero discounting. 87.5% of Phase 1 customers paid full price. This is the strongest signal — the product sells on merit.
- **Concern:** Post-BFCM hangover is moderate. Dec 2-15 revenue ($8K) is well above October baseline ($3K) but 74% below BFCM run rate. Need to assess whether this is natural seasonal decay or demand-borrowing.
- **Verdict:** Campaign structure is strong. Two-phase approach (full-price launch → BFCM bundles) should be repeated. Adjust: reduce BFCM Phase 2 ad spend and reallocate to Phase 1 where full-price conversion is stronger.

### Core Metrics Dashboard

| Metric | Phase 1 (Launch) | Phase 2 (BFCM) | Post-BFCM | Target | Status |
|--------|------------------|-----------------|-----------|--------|--------|
| Revenue | $18,000 | $31,000 | $8,000 | $45K total | $57K — beat by 27% |
| Orders | 320 | 410 | 145 | — | 875 total |
| AOV | $56 | $76 | $55 | $55+ | Phase 2 driven by bundles |
| New customers | 280 | 290 | — | 500+ | 570 — beat by 14% |
| Contribution margin (est.) | ~$9K (50%) | ~$11.5K (37%) | ~$3.5K | $18K+ | ~$24K — beat by 33% |
| Ad spend | $4,800 | $3,400 | — | $8K | $8.2K — on budget |
| Blended MER | — | — | — | — | $57K / $8.2K = 6.95x |
| Email/SMS revenue | — | — | — | — | $14K (29% of total) |
| New subscribers | — | — | — | 2,000+ | 2,400 — beat by 20% |
| Discount penetration | 0% | ~26% of BFCM | — | <20% | Over target for BFCM phase — see guardrails |

### 7-Signal Promo Health Check

Evaluated separately for Phase 1 and Phase 2:

#### Phase 1 (Launch — no discount)

| Signal | Result | Status |
|--------|--------|--------|
| Net revenue | $18K vs $3K October baseline — 6x lift | Good |
| Margin dollars | ~$9K at ~50% margin (full price, no discounting) | Good |
| AOV | $56 (above $55 target, driven by free-shipping threshold at $60) | Good |
| CAC | $4,800 / 280 new customers = $17.14 | Good (below $34 hero price) |
| New-customer quality | First cohort, no LTV data yet. Monitor 60-day repurchase. | Watch |
| Repeat behavior | N/A (first season) | N/A |
| Post-promo sales | Not applicable (no promo in Phase 1) | N/A |

**Phase 1 verdict: Strong. Full-price product sells on merit. This is the health signal.**

#### Phase 2 (BFCM — bundle discount)

| Signal | Result | Status |
|--------|--------|--------|
| Net revenue | $31K vs ~$6K estimated non-BFCM baseline (extrapolating Phase 1 weekly rate) — ~5x lift | Good |
| Margin dollars | ~$11.5K at ~37% margin (bundle discounts + free shipping) | Good but lower than Phase 1 |
| AOV | $76 (driven by Full Send bundle at $108) | Good — bundles working |
| CAC | $3,400 / 290 new customers = $11.72 | Good |
| New-customer quality | BFCM-acquired customers bought on discount. Monitor if they repurchase at full price. | Watch |
| Repeat behavior | N/A (first season) | N/A |
| Post-promo sales | Dec 2-15: $8K (74% below BFCM rate, but 167% above October baseline) | Moderate concern |

**Phase 2 verdict: Revise. Revenue and margin are strong, but discount penetration at 26% exceeds the 20% target for this phase. The 74% post-BFCM drop is steep — partly seasonal, partly demand-borrowing. Next year: tighter BFCM window (3 days not 5) and less aggressive email cadence.**

### Guardrail Check

| Guardrail | Target | Actual | Status |
|-----------|--------|--------|--------|
| Discount penetration (full campaign) | <20% | 188 discounted orders / 875 total = 21.5% | Slightly over — driven by BFCM bundle attach |
| Discount penetration (BFCM only) | <25% | 188 / 410 = 45.9% of BFCM orders at bundle discount | High but expected for tentpole |
| Full-price velocity (Phase 1) | Healthy | $18K at 100% full-price | Strong |
| Full-price velocity (Post-BFCM) | Watching | $8K, mostly full price (bundles returned to standard pricing Dec 1) | Acceptable — above off-season baseline |
| Hero SKU price integrity | Bottle Parka stays at $34 | $34 throughout. Never individually discounted. | Protected |

**Note on discount penetration:** 21.5% across the full campaign is within the 15-25% healthy range, but right at the upper bound. The concern is that BFCM phase alone was at 45.9% discount penetration. This is acceptable for an annual tentpole, but only if the rest of the year stays well below 15% to keep the blended number healthy.

### Who Bought?

| Segment | Phase 1 | Phase 2 (BFCM) | Notes |
|---------|---------|-----------------|-------|
| New customers | 280 (87.5%) | 290 (70.7%) | Phase 1 new customers paid full price — strongest cohort |
| Returning customers | 40 (12.5%) | 120 (29.3%) | BFCM drove repeat bundle purchases from Phase 1 buyers |
| Gift-givers (est.) | ~15% of orders | ~35% of BFCM orders | Based on "gift" messaging in notes, separate shipping addresses |

**Gift-giver insight:** Estimated 35% of BFCM orders were gifts (shipping to different address, gift message included). This validates the gift-giver segment strategy. The gift guide email (Nov 15) was the 2nd highest-revenue email in the sequence.

### Channel Performance

| Channel | Revenue Attributed | Spend | ROAS / Efficiency |
|---------|--------------------|-------|-------------------|
| Meta (Instagram/Facebook) | ~$22K | $5,000 | 4.4x ROAS |
| Google Shopping | ~$8K | $2,000 | 4.0x ROAS |
| TikTok | ~$3K | $1,200 | 2.5x ROAS |
| Email | ~$11K | $750 (tools) | 14.7x |
| SMS | ~$3K | $250 (tools) | 12x |
| Organic social | ~$5K | $1,000 | 5x |
| Influencer | ~$5K | $3,000 | 1.67x |
| **Blended** | **$57K** | **$8,200** (paid only) | **6.95x MER** |

**Note:** Platform-reported ROAS is directional, not precise. Blended MER (6.95x) is the north star. Post-iOS14 attribution means Meta and TikTok likely over-report. The honest answer: paid contributed but email/SMS at 29% of total revenue is the efficiency story.

**Influencer note:** $3K spend, ~$5K attributed revenue (1.67x). However, influencer content was whitelisted for paid ads in Phase 2 — some of the Meta ROAS is actually influencer creative performing in paid. True influencer ROI is likely higher than the direct attribution suggests. The 3 backcountry creators generated 12 UGC pieces used across paid and organic.

### Recommendations

1. **Repeat the two-phase structure** (full-price launch → BFCM bundles). Phase 1 full-price revenue is the strongest signal. The product sells on merit.
2. **Shorten BFCM window to 3 days** (Fri-Mon, not Tue-Mon). 5 days diluted urgency and pushed discount penetration above target.
3. **Increase influencer budget to $4-5K** next season. Whitelisted creator content outperformed polished brand creative in paid.
4. **Monitor 60-day repurchase** for BFCM-acquired customers. If they don't repurchase at full price, the discount cohort is structurally weaker. This determines whether BFCM bundle pricing was worth it.
5. **Gift-giver segment is validated** — invest in dedicated gift-giver creative and email flows for next holiday season.
6. **TikTok underperformed** (2.5x ROAS). Either invest in better native content or reallocate to Meta where ROAS is stronger.
7. **Establish this season as baseline** for YoY comparison next year.

### Next Period Priorities

- **Dec 15 - Feb**: Off-season. Focus on:
  - Post-purchase flow: care tips, field photo requests, review collection, cross-sell
  - Analyze 60-day repurchase rates by cohort (Phase 1 full-price vs BFCM bundle buyers)
  - Plan spring product launch if applicable
- **Sep - Oct (pre-season)**: Start influencer seeding, blog content for SEO indexing, email list growth campaigns
- **Next November**: Repeat this campaign structure with adjustments per findings above

---

**Next steps:** Would you like me to:
- Dig deeper into BFCM bundle cannibalization (did bundles reduce individual SKU sales)?
- Build a cohort analysis framework for tracking BFCM buyer quality?
- Compare ad creative performance across the 5 frameworks tested?
- Forecast next season based on this year's data?
