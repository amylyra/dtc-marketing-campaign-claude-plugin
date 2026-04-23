---
name: email-sequence
description: Design and draft email + SMS flows with full copy, timing, branching logic, and performance benchmarks. Use when building welcome series, abandoned cart, post-purchase, win-back, or any DTC lifecycle flow — or when mapping a promo sequence end-to-end with SMS.
argument-hint: "[flow type]"
---

# Email + SMS Flow Builder

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../../CONNECTORS.md).

Design and draft complete email + SMS flows with full copy, timing, branching logic, and performance benchmarks for DTC lifecycle and campaign use cases. Every flow treats email and SMS as a unified retention system — same triggers, same flows, different message format per touchpoint.

## Trigger

User runs `/email-sequence` or asks to create, design, build, or draft an email flow, SMS flow, lifecycle sequence, abandoned cart flow, welcome series, post-purchase flow, win-back sequence, or any DTC retention flow.

## Brand Context

Before drafting any copy, check for the `brand/` directory:

- If `brand/voice.md`, `brand/products.md`, and/or `brand/customers.md` exist, auto-apply brand voice, product references, and customer language to all email and SMS copy. Inform the user: "I found your brand context and will apply it to all copy."
- If the `brand/` directory does not exist, prompt: "I don't have your brand context yet. Want to run `/brand-review` to set that up first, or paste your brand guidelines now?"

## Inputs

Gather the following from the user. If not provided, ask before proceeding:

1. **Flow type** — one of:
   - Welcome series
   - Abandoned cart
   - Post-purchase
   - Browse abandonment
   - Win-back
   - VIP/Loyalty
   - Back-in-stock
   - Price drop
   - Replenishment
   - Review request
   - Referral
   - Birthday/Anniversary
   - Product launch (promo)
   - Flash sale (promo)
   - Seasonal promo (promo)

2. **Goal** — what the flow should achieve (e.g., convert first purchase, recover abandoned cart, drive repeat purchase, reactivate lapsed customers, collect reviews)

3. **Audience** — who enters this flow, what behavioral trigger enrolls them, and any relevant segmentation details (purchase history, browse behavior, RFM segment, subscription status)

4. **Number of messages** (optional) — if not specified, recommend a count based on the flow type using the templates in the Flow Type Templates section below

5. **Timing/cadence preferences** (optional) — desired spacing between messages (e.g., "aggressive first 24 hours then taper", "match product usage cycle")

6. **Brand voice** — if configured in `brand/voice.md`, apply automatically and inform the user. If not configured, ask: "Do you have brand voice guidelines I should follow? If not, I'll use a clear, conversational DTC tone."

7. **Additional context** (optional):
   - Specific offers, discounts, or incentives to include
   - Product details, hero SKUs, or collections to feature
   - Average order value and median reorder interval
   - Existing tech stack (Klaviyo, Shopify, etc.)
   - Subscription or replenishment options available

## Always-On vs. Promo Distinction

Clearly distinguish between these two categories for the user:

### Always-On Lifecycle Flows (infrastructure, run continuously)
These are the core retention system. They trigger based on customer behavior and run 24/7:
- Welcome series
- Abandoned cart
- Post-purchase
- Browse abandonment
- Win-back
- Replenishment
- Review request
- Back-in-stock
- Price drop
- Referral
- Birthday/Anniversary

### Promo-Specific Sequences (campaign-driven, time-bound)
These layer on top of lifecycle flows and have a start/end date:
- Product launch
- Seasonal promo
- Flash sale
- VIP early access
- Collaboration or limited edition drop

When building a promo sequence, note which lifecycle flows it may conflict with and recommend suppression rules.

## Process

### 1. Flow Strategy

Before drafting any messages, define the overall flow architecture:

- **Flow category** — is this always-on lifecycle or promo-specific? State explicitly.
- **Narrative arc** — what story does this flow tell across all touchpoints? What is the emotional and logical progression?
- **Channel strategy** — which messages are email, which are SMS, and why. SMS should complement email, not duplicate it.
- **Escalation logic** — how does urgency, value, or incentive level build across the flow?
- **Success definition** — what specific action signals the flow has done its job and the recipient should exit?

### 2. Flow Diagram

For each flow, provide a visual diagram showing:
- Trigger event
- Time delays between messages
- Channel for each touchpoint (email or SMS)
- Conditional branches (opened/didn't open, clicked/didn't click, purchased/didn't purchase)
- Exit conditions

Example format:

```
[Trigger: Cart Abandoned] --> SMS 1 (1 hour): Cart reminder
                                |
                           Purchased? --Yes--> [EXIT: Recovered]
                                |
                                No
                                |
                                v
                          Email 1 (4 hours): Cart contents + social proof
                                |
                           Purchased? --Yes--> [EXIT: Recovered]
                                |
                                No
                                |
                           Opened? --Yes--> Email 2 (24 hours): Urgency + reviews
                                |                  |
                                No            Purchased? --Yes--> [EXIT: Recovered]
                                |                  |
                                v                  No
                          SMS 2 (24 hours):        |
                          "Still thinking?         v
                           Items selling fast"  Email 3 (48 hours): Final + incentive
                                |                  |
                                +---> [EXIT: 72-hour window closed]
```

### 3. Individual Message Design

For each message in the flow, produce:

#### Channel
- **Email** or **SMS** — state which

#### Timing
- When this message sends relative to the trigger event or previous message
- Note if timing should adjust based on engagement

#### Subject Line (email only)
- Provide 2-3 options per email
- Vary approaches: curiosity, benefit-driven, urgency, personalization, social proof
- Keep under 50 characters where possible; note preview behavior on mobile

#### Preview Text (email only)
- 40-90 characters that complement (not repeat) the subject line
- Should add context or intrigue that increases open likelihood

#### SMS Message Text (SMS only)
- 160 characters or fewer
- Clear CTA with shortened link
- Include required STOP language on first SMS in any flow
- Brand name identification at start or end

#### Message Purpose
- One sentence explaining why this message exists and what it moves the recipient toward

#### Body Copy (email only)
- Full draft ready to use
- Clear hierarchy: hook, body, CTA
- Short paragraphs (2-3 sentences max)
- Scannable formatting with bold key phrases where appropriate
- Personalization tokens where relevant (first name, product name, cart contents, order details)
- Product imagery placement notes

#### Primary CTA
- Button text and destination (email)
- Link destination (SMS)
- One primary CTA per message

#### Conditional Logic
- What happens if they engage (open, click, purchase)
- What happens if they do not engage
- Exit conditions at this step

### 4. Sequence Logic

Define flow control:

- **Branching conditions** — alternate paths based on engagement. For example:
  - "If opened email 1 but did not click, send SMS nudge instead of email 2"
  - "If clicked but did not purchase, branch to incentive path"
  - "If purchased, exit flow and enter post-purchase flow"
- **Exit conditions** — when a recipient converts, remove them from the flow. Define what "conversion" means for this specific flow.
- **Re-entry rules** — can someone re-enter the flow? Under what conditions? (e.g., "if they abandon cart again 7 days later, re-enter"; "win-back flow: re-enter if they lapse again after 90 days")

### Promo Psychology Rules

These aren't just operational — they protect against psychological damage to the customer relationship:

- **Buyer's remorse protection**: If a promo sequence follows a full-price period, suppress discount offers from customers who purchased at full price within the last 14 days. A customer who paid $34 anchored to that price as "fair." Seeing it for $28 ten days later reframes their purchase as a mistake. They don't feel smart — they feel cheated. Next time, they'll wait for the sale. You've permanently downgraded a full-price buyer into a discount-seeker.
- **Discount escalation trap**: If a customer received a discount offer in the last 7 days from ANY flow, do not send a deeper discount from this flow. Escalating discounts teaches the buyer: "if I wait, the deal gets better." Once trained, this is nearly impossible to untrain.
- **VIP discount paradox**: VIPs should receive ACCESS (early access, exclusive products) not DISCOUNTS. VIPs already buy at full price. A discount says "we think you need convincing" — it undermines the relationship. Give them status instead.
- **Post-promo quiet period**: After a tentpole promo (BFCM, anniversary sale), insert a 7-14 day quiet period with no promotional emails. Immediately following a promo with another promo trains the "there's always a deal" mentality.

- **Suppression rules** — do not send if:
  - The recipient is already in a higher-priority flow
  - They have purchased since entering the flow
  - They have contacted support in the last 48 hours
  - They are in a promo-specific sequence that conflicts
  - SMS: they have not opted in or are outside quiet hours

### 5. SMS Compliance

For any flow that includes SMS, include this compliance section:

- **TCPA requirements**: Must have express written consent before sending marketing SMS
- **Opt-in**: Single or double opt-in at checkout, pop-up, or keyword
- **Quiet hours**: Do not send SMS between 9pm and 9am in the recipient's local timezone
- **Required language**: First SMS in any flow must include brand name and STOP instructions (e.g., "Reply STOP to unsubscribe")
- **Frequency**: State the expected SMS frequency per flow so it can be disclosed at opt-in

### 6. Performance Benchmarks

Provide expected benchmarks for the flow type:

| Flow | Email Open Rate | Email CTR | SMS CTR | Key Metric |
|------|----------------|-----------|---------|------------|
| Welcome | 50-60% | 8-12% | 10-15% | First purchase rate |
| Abandoned cart | 40-50% | 5-10% | 10-20% | Recovery rate 5-15% |
| Post-purchase | 50-70% | 5-8% | 8-12% | Review submission rate, repeat purchase rate |
| Browse abandonment | 35-45% | 3-6% | 8-12% | Return-to-site rate |
| Win-back | 20-30% | 2-4% | 5-8% | Reactivation rate |
| Back-in-stock | 50-65% | 10-15% | 15-25% | Purchase rate |
| Replenishment | 45-55% | 8-12% | 10-15% | Reorder rate |

Adjust benchmarks based on the brand's category, price point, and purchase frequency if context is available.

## Flow Applicability by Product Type

Not all 12 flows apply to every brand. Before building, check the product type in `brand/products.md`:

| Flow | Consumable | Durable Goods | Fashion/Apparel | Subscription |
|------|-----------|---------------|-----------------|-------------|
| Welcome | Yes | Yes | Yes | Yes |
| Abandoned cart | Yes | Yes | Yes | Yes |
| Post-purchase | Yes | Yes (adapt: no replenishment) | Yes | Yes |
| Browse abandonment | Yes | Yes | Yes | Yes |
| Win-back | Yes | Yes (trigger: new product/season) | Yes (trigger: new collection) | Yes |
| VIP/Loyalty | Yes | Yes | Yes | Yes |
| Back-in-stock | Yes | Yes | Yes (high priority) | Rare |
| Price drop | Yes | Yes | Yes (high priority) | No |
| Replenishment | Yes | **Skip** | Rare | Built-in |
| Review request | Yes | Yes | Yes | Yes |
| Referral | Yes | Yes | Yes | Yes |
| Birthday | Yes | **Skip unless lifestyle brand** | Yes | Yes |

If a flow is marked "Skip," do not build it. Explain why to the user: "Replenishment flows don't apply to durable goods — your product lasts years. Instead, I'll build a new-product-notification flow and seasonal re-engagement."

### Durable Goods Post-Purchase Adaptation

Replace steps 5-6 from the standard post-purchase template (replenishment + second purchase incentive) with:
5. **New product notification** — "You bought The Bottle Parka. Meet The Phone Parka." Triggered by new product launch or approaching next season.
6. **Seasonal re-engagement** — "Ski season is back. Here's what's new." Timed to the start of the brand's peak season.
7. **Referral prompt** — After positive review or 60 days post-purchase.

### Adapting Flow Logic by Buyer Psychology

The same trigger (e.g., cart abandonment) requires different recovery strategy depending on buyer psychology. Check `brand/customers.md` for buyer psychology before designing the flow.

**Abandoned Cart — by buyer type:**

| Buyer Psychology | Recovery Strategy | Message Focus | Incentive |
|-----------------|-------------------|---------------|-----------|
| Researched (durable, technical) | Provide proof — they're deciding, not distracted | Comparison data, peer reviews, FAQ, "here's why others chose this" | Last resort. Free shipping before %. |
| Impulse (beauty, fashion) | Quick reminder — they were distracted | "Still thinking about it?" + social proof + urgency | Earlier in sequence. GWP or free shipping. |
| Gift-giver | Reassure — they're uncertain about the gift | "Best-seller" validation, return policy, arrival date, reviews from other gift-givers | Gift-wrapping or free shipping. |
| High-ticket ($200+) | Consultative — address specific objections | Warranty, customer service, detailed reviews, payment plan | Financing or bundle value, not %. |

**Win-Back — by product type:**

| Product Type | Win-Back Trigger | Win-Back Message |
|-------------|-----------------|-----------------|
| Consumable | X days past expected replenishment | "Running low? Time to restock." Rational, convenience-focused. |
| Durable | New product launch or new season | "You bought X. Meet Y." Product-focused, not relationship-focused. |
| Fashion | New collection or seasonal shift | "New arrivals — your style, updated." Identity-focused. |
| Seasonal | Approaching peak season | "Season is back. Here's what's new." Contextual. |

**Post-Purchase — by buyer psychology:**

| Buyer Psychology | Post-Purchase Focus | Avoid |
|-----------------|--------------------| ------|
| Researched / skeptical | Prove they made the right call. Usage tips, care instructions, performance data. "Here's how to get the most out of it." | Over-communicating. Respect their intelligence. |
| Social / enthusiast | Celebrate with them. Community, UGC request, "show us your [product]." | Being transactional too fast. Build relationship before cross-sell. |
| Gift-giver | Confirmation that the gift will be loved. Tracking, unboxing preview. Then: pivot to making THEM a customer. | Sending product-usage emails to someone who gifted it — they don't have the product. |

## Flow Type Templates

Use these as starting frameworks. Adapt length and content based on the user's goal and audience. Priority order for new brands building their retention system from scratch:

### 1. Welcome Series (3-5 emails + SMS over 7-14 days)
**Priority: Build first.** This is the highest-volume flow.
- SMS 1 (immediate): Thank you + discount code reminder
- Email 1 (immediate): Welcome, brand story, hero product intro, set expectations
- Email 2 (Day 2): Social proof — reviews, UGC, community
- Email 3 (Day 4): Hero product deep dive or best-sellers showcase
- Email 4 (Day 7): First-purchase incentive if they haven't bought
- Email 5 (Day 10): Segment by interest — ask preferences or use browse behavior to personalize
- Conditional: If they purchase at any point, exit and enter post-purchase flow

### 2. Abandoned Cart (3 emails + 2 SMS over 72 hours)
**Priority: Build second.** Highest direct revenue recovery.
- SMS 1 (1 hour): Simple reminder with cart link
- Email 1 (4 hours): Cart contents with product images, no discount yet
- Email 2 (24 hours): Social proof — reviews for carted items, "others are buying this"
- SMS 2 (36 hours): Urgency — "items selling fast" or low stock
- Email 3 (48 hours): Final touch — optional incentive (free shipping or small discount), urgency/scarcity
- Conditional: Exit immediately on purchase. If no purchase after 72 hours, exit and optionally enter browse abandonment retargeting.

### 3. Post-Purchase (5-7 emails + SMS over 30-60 days)
**Priority: Build third.** Highest ROI, most underbuilt flow for DTC brands.
1. **Order confirmation** (immediate, email): Thank you, order details, cross-sell recommendation ("pairs well with..."), set expectation for shipping timeline
2. **Shipping notification** (when shipped, email + SMS): Tracking link + brand storytelling moment ("Here's why we made this...")
3. **Delivery confirmation** (when delivered, email): "Your order arrived!" + care/usage tips + review request teaser
4. **Review request** (5-7 days post-delivery, email): Ask for review, optional photo incentive, make it easy with direct link to review form
5. **Replenishment reminder** (timed to product lifecycle, email + SMS): "Running low?" + easy reorder link + subscription offer
6. **Second purchase incentive** (if no repeat purchase by 2x median reorder interval, email): Personalized recommendation based on first purchase + modest incentive
7. **Cross-sell** (ongoing, email): Related products based on purchase history

### 4. Browse Abandonment (2-3 emails + 1 SMS over 48 hours)
- Email 1 (2 hours): "Still looking at [product]?" with product image and link
- SMS 1 (6 hours): Brief nudge with product link
- Email 2 (24 hours): Social proof for browsed products + related items
- Email 3 (48 hours): "These are going fast" or category best-sellers
- Conditional: Exit on purchase. Do not send if they have entered abandoned cart flow.

### 5. Win-Back (3-4 emails + 1 SMS over 30-60 days)
- Email 1 (Day 0, triggered by lapse threshold): "We miss you" — what's new since their last purchase
- Email 2 (Day 10): New products, best-sellers, or content they missed
- SMS 1 (Day 20): Short, personal "Come back" with incentive
- Email 3 (Day 30): Escalating offer — meaningful discount or free gift with purchase
- Email 4 (Day 45): Final attempt — "Is this goodbye?" with survey link + last-chance offer
- Conditional: Exit on purchase. If no engagement after full sequence, suppress from marketing for 30 days then move to sunset flow.

### 6. VIP/Loyalty (ongoing, triggered by RFM segment)
- Early access to new products or restocks
- Exclusive previews or behind-the-scenes content
- Thank-you messages at purchase milestones
- Birthday/anniversary offers
- Surprise gifts or bonus loyalty points

### 7. Back-in-Stock (1 email + 1 SMS, triggered)
- SMS (immediate on restock): "[Product] is back! Limited quantities." + link
- Email (immediate or 30 min after SMS): Product details, urgency, easy purchase CTA
- Conditional: Only send to profiles who browsed or wishlisted the item. Exit on purchase.

### 8. Price Drop (1-2 emails + 1 SMS, triggered)
- SMS (immediate): "[Product] just dropped to [price]!" + link
- Email 1 (immediate or 1 hour after SMS): Price comparison, product details, urgency
- Email 2 (24 hours, if no purchase): "Price won't last" reminder
- Conditional: Only send to profiles who browsed or wishlisted the item. Exit on purchase.

### 9. Replenishment (1-2 emails + 1 SMS, triggered by product usage cycle)
- Email 1 (timed to expected product depletion): "Running low on [product]?" + reorder link + subscription offer
- SMS 1 (3 days later if no reorder): Quick reminder with reorder link
- Email 2 (7 days later if no reorder): Last reminder + "Don't run out" + possible incentive
- Conditional: Exit on reorder. Adjust timing based on actual reorder data.

### 10. Review Request (1-2 emails, triggered post-delivery)
- Email 1 (5-7 days after delivery): Ask for review with direct link, optional photo/video incentive
- Email 2 (10-14 days after delivery, if no review): Softer follow-up — "Your opinion matters" + even simpler review process
- Conditional: Exit on review submission. Do not send if customer has contacted support about this order.

### 11. Referral (1-2 emails, triggered)
- Email 1 (triggered after positive review or 2nd purchase): Introduce referral program, "Share with friends, you both get [reward]"
- Email 2 (7 days later if no referral action): Reminder with social sharing links
- Conditional: Only trigger for customers with positive engagement signals.

### 12. Birthday/Anniversary (1 email + 1 SMS, triggered)
- Email (on birthday or purchase anniversary): Personal offer or gift, "This one's for you"
- SMS (same day): Short birthday wish + offer code
- Conditional: Requires date of birth or first purchase date in profile.

## Klaviyo-Specific Guidance

Since Klaviyo is connected via MCP:

### Flow Builder Concepts
- Reference Klaviyo's visual flow builder when describing trigger setup, time delays, conditional splits, and branching
- Use Klaviyo terminology: flows (not automations), profiles (not contacts), metrics (not events)
- Note where to use conditional splits vs. trigger splits

### Segmentation
- Recommend segment creation for flow targeting (e.g., "Create a segment for customers who purchased 60+ days ago and have not purchased since" for win-back)
- Reference Klaviyo profile properties for personalization: first name, last order date, total order count, predicted next order date, lifetime value

### Catalog Integration
- Back-in-stock and price drop flows use Klaviyo catalog feeds — note that the catalog must be synced from the ecommerce platform
- Product recommendations in post-purchase and browse abandonment can pull from Klaviyo's catalog-based recommendations

### A/B Testing
- Recommend A/B tests within flows: subject lines, send times, content variants, incentive levels
- Klaviyo supports A/B splits within flow branches — use these for optimization
- Suggest testing: discount percentage vs. free shipping, urgency vs. social proof, short vs. long copy

### Profile Properties for Personalization
- First name, last purchased product, cart contents, browse history
- Predicted gender, predicted next order date (if Klaviyo predictive analytics is enabled)
- Custom properties synced from ecommerce platform (subscription status, loyalty tier, etc.)

## Output

Present the complete flow with the following sections:

### Flow Overview Table

| # | Channel | Timing | Subject / SMS Text | Purpose | CTA | Condition |
|---|---------|--------|-------------------|---------|-----|-----------|

### Full Message Drafts
Each message with channel, timing, subject line options (email) or message text (SMS), preview text (email), purpose, body copy (email), CTA, and conditional logic.

### Flow Diagram
Text-based diagram showing the flow with email and SMS touchpoints, branching paths, time delays, and exit points.

### Branching Logic Notes
Summary of all conditions, exits, re-entry rules, and suppressions in a reference list.

### SMS Compliance Checklist
TCPA requirements, opt-in method, quiet hours, required STOP language, and frequency disclosure for this specific flow.

### A/B Test Suggestions
- 2-3 recommended A/B tests specific to this flow type
- What to test, how to split, and how to measure the winner
- Include at least one test comparing email-only vs. email+SMS for a specific touchpoint

### Metrics to Track
- Primary conversion metric for the flow (e.g., recovery rate, first purchase rate, repeat purchase rate)
- Per-message metrics: open rate (email), CTR (email and SMS), unsubscribe rate, revenue attributed
- Flow-level metrics: overall conversion rate, revenue per recipient, time to conversion
- Recommended review cadence: "Review performance weekly for the first month, then bi-weekly"

## After the Flow

Ask: "Would you like me to:
- Revise the copy or tone for any specific message?
- Add or remove an SMS touchpoint?
- Create a variation of this flow for a different customer segment?
- Draft the A/B test variants for subject lines or incentive levels?
- Build the next priority flow for your retention system?
- Set up the Klaviyo segments needed for this flow?"
