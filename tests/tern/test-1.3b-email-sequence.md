# Test 1.3b: `/email-sequence` Output — Ski Season Launch Promo Sequence

**Simulated input:** "/email-sequence product launch for Tern ski season — November 1 launch, BFCM push Nov 27"

**Brand context applied:** brand/voice.md, brand/products.md, brand/customers.md
**Flow category:** Promo-specific (time-bound, two-phase)

---

## Flow Overview

This is a **promo-specific sequence** — not an always-on lifecycle flow. It has a start date (Oct 28 teaser) and an end date (Dec 1 BFCM close). Always-on flows (welcome, cart abandonment, post-purchase) should continue running alongside this sequence with suppression rules.

### Narrative Arc
Teaser → Early access reward → Public launch → Social proof sustain → Gift-giver pivot → BFCM bundle push → Urgency close.

### Success Definition
Purchase (any Tern product). On purchase, exit this promo flow and enter post-purchase flow.

---

## Flow Diagram

```
[Oct 28] Email 1: Teaser — "Something's coming"
            |
            v
[Nov 1] Email 2 + SMS 1: Early access (subscribers only)
            |
        Purchased? --Yes--> [EXIT → post-purchase flow]
            |
            No
            v
[Nov 3] Email 3: Public launch + social proof
            |
        Purchased? --Yes--> [EXIT → post-purchase flow]
            |
            No
            v
[Nov 10] Email 4: Field-test proof (UGC + reviews)
            |
        Purchased? --Yes--> [EXIT → post-purchase flow]
            |
            No
            v
[Nov 15] Email 5: Gift guide — "For the skier who has everything"
            |
        Purchased? --Yes--> [EXIT → post-purchase flow]
            |
            No
            v
[Nov 25] Email 6 + SMS 2: BFCM early access (VIP + engaged)
            |
        Purchased? --Yes--> [EXIT → post-purchase flow]
            |
            No
            v
[Nov 27] Email 7 + SMS 3: BFCM public launch — The Full Send bundle
            |
        Purchased? --Yes--> [EXIT → post-purchase flow]
            |
            No
            v
[Nov 29] Email 8 + SMS 4: BFCM last chance — ends midnight
            |
            v
[Dec 1] [EXIT — promo sequence ends]
```

---

## Individual Messages

### Email 1: Teaser (Oct 28)

**Channel:** Email
**Timing:** Oct 28 (4 days before launch)
**Purpose:** Build anticipation. Prime the list for the Nov 1 early access.

**Subject line options:**
1. "Something's coming. Ski season is about to change."
2. "Nov 1. Be ready."
3. "Your gear has a freezing problem. We built the fix."

**Preview text:** "Early access for subscribers. 48 hours before everyone else."

**Body:**

> Ski season is almost here. And this year, your gear won't be the weak link.
>
> On November 1, Tern subscribers get 48-hour early access to our full collection — including The Bottle Parka, The Phone Parka, and two new products you haven't seen yet.
>
> No discount. No code. Just first access to gear that's field-tested at 14,000ft and built to keep your equipment working to -20F.
>
> Mark your calendar. November 1.
>
> — Tern

**CTA:** None (anticipation only). Optional: "Add to calendar" link.

---

### Email 2: Early Access Launch (Nov 1) + SMS 1

**Channel:** Email + SMS
**Timing:** Nov 1, 8am (subscriber early access)
**Purpose:** Drive first full-price purchases from most engaged audience.

**Subject line options:**
1. "You're in. Early access is live."
2. "The Bottle Parka. Field-tested at 14,000ft. Yours first."
3. "-20F. 4+ hours. Still liquid. Shop before everyone else."

**Preview text:** "48-hour subscriber exclusive. Full collection is live."

**Body:**

> Early access is live. You're seeing this before everyone else.
>
> **The Bottle Parka — $34**
> Military-grade Thinsulate. Waterproof YKK zippers. Keeps water liquid to -20F for 4+ hours. Fits your Nalgene, Hydro Flask, or CamelBak.
>
> **The Phone Parka — $28**
> Touchscreen-compatible insulated case. Your phone survives the cold. Your GPS, camera, and emergency comms stay live.
>
> **The Goggle Warmer — $22**
> Heated goggle cover. Eliminates fog on transitions. USB-C rechargeable, 6+ hours per charge.
>
> **The Hand Warmer Pouch — $18**
> Rechargeable, 8+ hours, doubles as a power bank.
>
> **Or get the full system:**
> The Summit Kit (3 essentials) — $89 (saves $13)
> The Full Send (everything) — $118 (saves $24)
>
> Free shipping at $60.
>
> This is subscriber-only until Nov 3. After that, everyone gets in.

**CTA:** "Shop Early Access"

**SMS 1 (Nov 1, 8am):**
> Tern: Early access is live. The Bottle Parka + full collection — subscribers only for 48hrs. Shop now: [link] Reply STOP to opt out

*(155 chars with link placeholder)*

---

### Email 3: Public Launch + Social Proof (Nov 3)

**Channel:** Email
**Timing:** Nov 3 (public launch)
**Purpose:** Drive purchases from full list. Lead with social proof.

**Subject line options:**
1. "Now live for everyone. 4.9 stars. 2,800+ reviews."
2. "Your water bottle freezes. Theirs doesn't. Here's why."
3. "The gear fix 2,800 mountaineers already trust."

**Preview text:** "'I've never had liquid water at a summit bivvy.' — verified buyer"

**Body:**

> The collection is live for everyone.
>
> But don't take our word for it:
>
> *"I've been mountaineering for 12 years and this is the first time I've had liquid water at a summit bivvy."* — Jake R., verified buyer
>
> *"Bought one for a Denali trip. Came back and ordered three more."* — Sarah M., verified buyer
>
> *"Built like real gear, not Amazon junk."* — Chris T., verified buyer
>
> **The Bottle Parka — $34**
> Military-grade Thinsulate. Waterproof YKK zippers. Tested at 14,000ft.
>
> Free shipping at $60.

**CTA:** "Shop The Collection"

---

### Email 4: Field-Test Proof (Nov 10)

**Channel:** Email
**Timing:** Nov 10 (1 week post-launch)
**Purpose:** Convert holdouts with field-test data and UGC. Address objections.

**Subject line options:**
1. "We left it on Mt. Hood overnight. Here's what happened."
2. "Lab tests are easy. We test at 14,000ft."
3. "-20F for 4 hours. Here's the data."

**Preview text:** "Field-tested in the conditions you actually ski and climb in."

**Body:**

> We don't test in labs. We test on mountains.
>
> **The test:** The Bottle Parka, Mt. Hood, -18F, 14,200ft. Left overnight on a summit bivvy.
>
> **The result:** Water still liquid after 4+ hours. Ice formation began around hour 5.
>
> **The materials:** Military-grade Thinsulate — the same insulation used in extreme cold weather gear. Waterproof YKK zippers because condensation and snow will find a way in. Reinforced neoprene shell for durability on granite and pack straps.
>
> **The objection we hear most:** "Why not just buy an insulated bottle?"
> Because your Nalgene is bombproof. It's been on every trip. You trust it. We keep it working — we don't replace it.
>
> $34. Fits bottles 18-32oz.

**CTA:** "Shop The Bottle Parka"

---

### Email 5: Gift Guide (Nov 15)

**Channel:** Email
**Timing:** Nov 15 (gift-giver pivot, 6 weeks before Christmas)
**Purpose:** Capture gift-givers. Shift from self-purchase to gifting language.

**Subject line options:**
1. "For the skier who has everything."
2. "The gift they didn't know they needed."
3. "Impossible to shop for? Not anymore."

**Preview text:** "Functional gifts that actually get used. Starting at $18."

**Body:**

> We know the person. They already have the jacket, the skis, the boots. They don't need another pair of socks.
>
> They need the gear their gear doesn't have.
>
> **Under $25:**
> The Hand Warmer Pouch — $18. Rechargeable warmth, 8+ hours. Doubles as a power bank.
>
> **Under $35:**
> The Goggle Warmer — $22. No more fog on every chairlift ride.
> The Phone Parka — $28. Their phone survives the cold.
> The Bottle Parka — $34. Liquid water at any summit.
>
> **The "I got you the good stuff" gift:**
> The Summit Kit — $89. Three essentials, one box, saves $13.
> The Full Send — $118. The complete system. Saves $24.
>
> Free shipping on orders $60+.
>
> All products ship in gift-ready packaging.

**CTA:** "Shop the Gift Guide"

---

### Email 6: BFCM Early Access (Nov 25) + SMS 2

**Channel:** Email + SMS
**Timing:** Nov 25 (24 hours before public BFCM)
**Segment:** VIP (2+ orders) and engaged subscribers (opened 3+ emails in last 30 days)
**Purpose:** Reward best customers with first access to BFCM offer.

**Subject line options:**
1. "BFCM early access. The Full Send, $108."
2. "You get in first. The complete Tern system, $108."
3. "24 hours before everyone else. Full Send bundle."

**Preview text:** "The Full Send: all 4 products, saves $24. VIP access now."

**Body:**

> You're getting this 24 hours before everyone else.
>
> **The Full Send — $108** (normally $142, saves $24)
> The Bottle Parka + The Phone Parka + The Goggle Warmer + The Hand Warmer Pouch. Every piece of gear that fails in the cold — protected.
>
> **The Summit Kit — $89** (saves $13)
> Bottle Parka + Phone Parka + Hand Warmer Pouch. The three essentials.
>
> Free shipping on all orders. Through Cyber Monday.
>
> Individual products are full price — this is about the bundles.

**CTA:** "Shop BFCM Early Access"

**SMS 2 (Nov 25):**
> Tern: BFCM early access — you're in first. The Full Send bundle: $108 (saves $24). Free shipping. Shop: [link]

*(132 chars with link placeholder)*

---

### Email 7: BFCM Public Launch (Nov 27) + SMS 3

**Channel:** Email + SMS
**Timing:** Nov 27 (Black Friday, 6am)
**Purpose:** Drive BFCM bundle purchases from full list.

**Subject line options:**
1. "The Full Send. $108. All 4 products."
2. "Black Friday at Tern: bundles only, no sitewide sales."
3. "One deal. The complete system. $108."

**Preview text:** "No sitewide discounts. Just the bundles, at the best price of the year."

**Body:**

> We don't do sitewide sales. We don't discount The Bottle Parka.
>
> Here's what we do once a year:
>
> **The Full Send — $108** (all 4 products, saves $24)
> **The Summit Kit — $89** (3 essentials, saves $13)
>
> Free shipping on everything. Through Cyber Monday.
>
> That's it. Bundles at the best price of the year. Individual products stay full price.
>
> Ends midnight Monday.

**CTA:** "Shop Black Friday"

**SMS 3 (Nov 27, 8am):**
> Tern: Black Friday is live. The Full Send: $108 (saves $24). Free shipping. Ends Mon midnight. Shop: [link]

*(126 chars with link placeholder)*

---

### Email 8: BFCM Last Chance (Nov 29) + SMS 4

**Channel:** Email + SMS
**Timing:** Nov 29 (Saturday before Cyber Monday ends)
**Purpose:** Urgency close. Convert remaining BFCM interest.

**Subject line options:**
1. "Ends Monday midnight. The Full Send, $108."
2. "Last chance. This price won't come back."
3. "48 hours left. The complete Tern system, $108."

**Preview text:** "BFCM bundle pricing ends midnight Monday."

**Body:**

> This is the last time you'll see this price.
>
> **The Full Send — $108.** All 4 products. Saves $24. Ships free.
>
> After Monday midnight, bundles return to standard pricing. We won't extend. We won't run another sale this year.
>
> If you've been thinking about it, this is the moment.

**CTA:** "Shop Before It Ends"

**SMS 4 (Nov 30, 10am — Sunday):**
> Tern: Final call. The Full Send: $108 ends tomorrow midnight. Free shipping. Don't wait: [link]

*(111 chars with link placeholder)*

---

## Suppression Rules

- Do not send this promo sequence to anyone who has purchased since Nov 1 (they should be in post-purchase flow)
- Do not send BFCM emails (6, 7, 8) to anyone who purchased during Phase 1 at full price within the last 14 days (avoid buyer's remorse)
- If a subscriber is in the welcome series, suppress promo emails until welcome flow completes (or Day 7, whichever is first), then add to promo sequence at the current message
- Do not send SMS during quiet hours (9pm-9am recipient local time)
- Do not send SMS to non-opted-in profiles

## SMS Compliance

- **TCPA**: All SMS recipients have opted in via checkout, popup, or keyword
- **First SMS in flow (SMS 1)**: Includes "Reply STOP to opt out"
- **Brand identification**: Every SMS starts with "Tern:"
- **Quiet hours**: No SMS between 9pm-9am in recipient's local timezone
- **Frequency**: 4 SMS total across ~5 weeks. This is within typical DTC frequency.

## Performance Benchmarks

| Metric | Target | Benchmark |
|--------|--------|-----------|
| Email open rate (launch) | 45-55% | Product launch emails outperform campaign averages |
| Email CTR (launch) | 6-10% | Strong for engaged list receiving first access |
| SMS CTR | 10-18% | Launch/BFCM urgency drives higher SMS engagement |
| BFCM email open rate | 35-45% | Inbox competition is high during BFCM |
| BFCM conversion rate | 3-5% | Bundle offer should drive higher conversion than typical promo |
| Revenue per recipient | $2-4 for launch, $3-6 for BFCM | Higher AOV from bundles |

## A/B Test Suggestions

1. **BFCM subject lines: urgency vs. specificity**
   - A: "Last chance. The Full Send, $108."
   - B: "48 hours left. All 4 products, saves $24."
   - Measure: open rate, CTR, revenue per recipient

2. **Launch email: product-first vs. proof-first**
   - A: Lead with product details and specs (Email 2 style)
   - B: Lead with customer review quotes (Email 3 style)
   - Measure: CTR, conversion rate

3. **SMS vs. email-only for BFCM early access**
   - A: Email only
   - B: Email + SMS
   - Measure: conversion rate, revenue per recipient, opt-out rate

## Metrics to Track

- **Primary:** Revenue attributed to promo sequence, split by Phase 1 (launch) and Phase 2 (BFCM)
- **Per-message:** Open rate, CTR, unsubscribe rate, revenue attributed
- **Flow-level:** Overall conversion rate, revenue per recipient, bundle attach rate, new vs returning buyer split
- **Review cadence:** Daily during BFCM weekend, weekly for Phase 1

---

**Next steps:** Would you like me to:
- Revise the copy or tone for any specific message?
- Build the post-purchase flow for Tern (non-consumable: care tips, cross-sell, UGC request, referral)?
- Draft the welcome series as a companion always-on flow?
- Create the Klaviyo segments needed for this flow?
