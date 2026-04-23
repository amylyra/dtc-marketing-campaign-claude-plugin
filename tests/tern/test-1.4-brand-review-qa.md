# Test 1.4: `/brand-review` Output — QA Content from Phase 3

**Simulated input:** User pastes the BFCM public launch email (Email 7 from test-1.3b) and two ad hooks, then says "/brand-review"

**Content submitted for review:**

**Email:**
> Subject: "The Full Send. $108. All 4 products."
> Body: "We don't do sitewide sales. We don't discount The Bottle Parka. Here's what we do once a year: The Full Send — $108 (all 4 products, saves $24). The Summit Kit — $89 (3 essentials, saves $13). Free shipping on everything. Through Cyber Monday. That's it. Bundles at the best price of the year. Individual products stay full price. Ends midnight Monday."

**Ad hook 1:**
> "Your water bottle freezes at 10,000ft. Now what? The Bottle Parka. Military-grade Thinsulate keeps water liquid to -20F for 4+ hours. Field-tested at 14,000ft. $34. Shop now."

**Ad hook 2:**
> "This cozy little sleeve keeps your water warm all day! Perfect for any outdoor adventure. A total game-changer for hikers. Get yours today!"

*(Ad hook 2 is intentionally bad — testing whether the review catches violations)*

**Brand context applied:** brand/voice.md, brand/products.md, brand/customers.md

---

## Simulated Review Output

### Summary

Overall, 2 of 3 content pieces are strong and on-brand. Ad hook 2 has multiple high-severity issues — it contradicts Tern's brand voice, uses avoided terms, and makes vague claims. Do not publish without a full rewrite.

**Strengths:** The email and ad hook 1 nail Tern's technical, understated voice. Product claims match approved specs. The email's "We don't do sitewide sales. We don't discount The Bottle Parka." is strong brand positioning.

**Top priority:** Ad hook 2 needs a complete rewrite. It reads like generic DTC copy and violates multiple brand guidelines.

### Detailed Findings

| Issue | Location | Severity | Suggestion |
|-------|----------|----------|------------|
| Uses "cozy" — avoided term | Ad hook 2: "cozy little sleeve" | High | Remove. Tern is performance gear, not lifestyle. Use "insulated" or "expedition-grade." |
| Uses "game-changer" — avoided term | Ad hook 2: "total game-changer" | High | Remove. Tern avoids hype language. Let the specs speak: "-20F for 4+ hours." |
| Uses "perfect for" — avoided term | Ad hook 2: "perfect for any outdoor adventure" | High | Remove. Vague and off-brand. Specify the use case: "Purpose-built for winter summits, backcountry ski days, and ice climbs." |
| Vague claim: "keeps your water warm all day" | Ad hook 2 | High | Unapproved and inaccurate. Approved claim: "keeps water liquid to -20F for 4+ hours." "All day" is unsubstantiated. "Warm" is incorrect — the product prevents freezing, not heating. |
| "little sleeve" undermines product positioning | Ad hook 2 | Medium | Tern positions these as an "insulation system" and "gear protection," not a "sleeve." Use product-specific language from brand/voice.md. |
| Missing product name | Ad hook 2 | Medium | Refers to "this sleeve" — should be "The Bottle Parka" (always capitalize, always include "The"). |
| "hikers" is too broad | Ad hook 2 | Low | Tern targets serious winter athletes, not generic hikers. Specify: "backcountry skiers," "mountaineers," "winter hikers." |
| Email: no issues found | Email (Email 7) | — | On-brand. Voice is direct and confident. Claims match approved specs. Pricing accurate. |
| Ad hook 1: no issues found | Ad hook 1 | — | On-brand. Specs correct (-20F, 4+ hours, 14,000ft, $34). Voice is technical and understated. |

### Product Claim Check

| Claim in Content | Approved in brand/products.md? | Status |
|-----------------|-------------------------------|--------|
| "keeps water liquid to -20F for 4+ hours" (Ad hook 1) | Yes — matches exactly | Approved |
| "$108, saves $24" (Email) | Yes — Full Send $118 normally, $108 BFCM | Approved |
| "$89, saves $13" (Email) | Yes — Summit Kit normally $102, $89 bundle | Approved |
| "keeps your water warm all day" (Ad hook 2) | No — unapproved claim | **Rejected** — approved claim is "liquid to -20F for 4+ hours" |
| "Military-grade Thinsulate" (Ad hook 1) | Yes | Approved |
| "Field-tested at 14,000ft" (Ad hook 1) | Yes | Approved |

### Revised Sections

**Ad hook 2 — Before:**
> "This cozy little sleeve keeps your water warm all day! Perfect for any outdoor adventure. A total game-changer for hikers. Get yours today!"

**Ad hook 2 — After:**
> "Your water freezes. Your phone dies. Your goggles fog. Every piece of gear that fails in the cold — Tern keeps it working. The Bottle Parka: military-grade Thinsulate, -20F for 4+ hours. Field-tested at 14,000ft. $34."

### Legal/Compliance Flags

| Flag | Details | Recommended Action |
|------|---------|-------------------|
| Unsubstantiated claim | "keeps your water warm all day" — duration is vague ("all day"), mechanism is incorrect ("warm" vs "prevents freezing"), and exceeds approved 4+ hour claim | Replace with approved claim. If longer duration is desired, conduct and document additional field testing first. |

### After Review

Would you like me to:
- Revise ad hook 2 with the corrections applied?
- Review additional content against the same guidelines?
- Focus on fixing just the high-severity issues?
- Update your brand voice, products, or customer profiles?
