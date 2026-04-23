---
name: brand-review
description: Set up your brand voice, product catalog, and customer profiles, or review content against them. Use to onboard a new brand, check a draft before it ships, audit copy for voice consistency, or screen for legal and compliance flags.
argument-hint: "<content to review> or 'setup'"
---

# Brand Review

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../../CONNECTORS.md).

Two modes: **Brand Setup** (build your brand guidelines from scratch) and **Brand Review** (check content against those guidelines). The skill detects which mode to use automatically, or the user can ask explicitly.

## Trigger

User runs `/brand-review` or asks to review, check, or audit content against brand guidelines. User runs `/brand-review setup` or asks to set up, create, or define brand voice, products, or customer profiles.

## Mode Detection

1. Check whether `brand/voice.md`, `brand/products.md`, and `brand/customers.md` contain filled-in content (not just template placeholders).
2. If all three are empty or contain only template scaffolding, or if the user explicitly asks to set up their brand, enter **Mode 1: Brand Setup**.
3. If brand files are populated and the user provides content to review, enter **Mode 2: Brand Review**.
4. If brand files are partially filled in, ask: "Some brand files are already started. Would you like to continue setup where you left off, or review content against what you have so far?"

---

## Mode 1: Brand Setup

Guide the user through a structured conversation to build their brand guidelines. Save outputs to the template files in `brand/`.

### Setup Flow

Work through these sections in order. For each section, ask focused questions, synthesize the answers, and confirm with the user before saving. Do not dump all questions at once — keep it conversational.

#### 1. Brand Personality

Ask: "Describe your brand as if it were a person. What are they like at a dinner party? How do friends describe them? What would they never do?"

Synthesize into a 2-3 sentence personality statement. Confirm with the user.

Save to: `brand/voice.md`

#### 2. Voice Attributes

Ask the user to pick 3-5 attributes from the spectrums below (or define their own), then for each one, define "we are" and "we are not" boundaries.

| Spectrum | One End | Other End |
|----------|---------|-----------|
| Formality | Formal, institutional | Casual, conversational |
| Authority | Expert, authoritative | Peer-level, collaborative |
| Emotion | Warm, empathetic | Direct, matter-of-fact |
| Complexity | Technical, precise | Simple, accessible |
| Energy | Bold, energetic | Calm, measured |
| Humor | Playful, witty | Serious, earnest |
| Aspiration | Aspirational, elevated | Grounded, relatable |

For each chosen attribute, capture:

- **We are**: what this means in practice
- **We are not**: the common overcorrection to avoid
- **This sounds like**: example sentence
- **This does NOT sound like**: example sentence

Save to: `brand/voice.md`

#### 3. Tone Spectrum by Channel

Walk through each DTC channel and ask how the brand voice should flex:

| Channel | Prompt |
|---------|--------|
| Instagram | "What's the vibe on your grid vs. Stories vs. Reels? How polished vs. raw?" |
| TikTok | "How casual do you go? Do you lean into trends or stay on-brand regardless?" |
| Email | "Welcome series vs. promo vs. winback — how does the tone shift?" |
| SMS | "How familiar can you be? Emoji use? Abbreviations?" |
| Product pages | "Educational or hype-driven? How technical do you get about ingredients/materials?" |
| Ads (Meta/Google) | "Punchy and benefit-led? Storytelling? UGC-style?" |
| Blog | "Thought-leader angle or practical how-tos? What depth?" |
| Customer support | "How do you handle complaints? Returns? Damage control?" |

Capture a 1-2 sentence tone description and a short example for each channel.

Save to: `brand/voice.md`

#### 4. Product Catalog

For each hero SKU (start with the top 3-5), capture:

- **Product name** (as it appears on-site)
- **Price point** (or price range)
- **Key claims** — the approved marketing claims for this product
- **Ingredients / materials** — what matters to the customer
- **Differentiators** — what makes this different from competitors
- **Common objections** — what holds people back from buying
- **Proof points** — clinical results, certifications, awards, press mentions

Ask: "What are your hero products — the ones that show up in most of your marketing? Let's start with those."

Save to: `brand/products.md`

#### 5. Customer Profiles

For each key segment, capture:

- **Who they are** — demographics, psychographics, shopping behavior
- **Why they buy** — the trigger or need that brings them to the brand
- **Who gifts** — if gifting is a use case, who gives and who receives
- **Their language** — phrases they actually use in reviews, DMs, and UGC (pull from real reviews if available)
- **Objections** — what they worry about before purchasing
- **Where they hang out** — which channels, communities, influencers they follow

Ask: "Who's your core customer? And is there a secondary buyer — maybe someone who gifts your product, or a different demographic that's growing?"

Save to: `brand/customers.md`

#### 6. Terminology

Capture:

- **Preferred terms** — the words and phrases the brand uses (e.g., "clean beauty" not "natural beauty")
- **Avoided terms** — words that are off-brand or carry the wrong connotation
- **Product-specific language** — how to talk about ingredients, materials, processes
- **Competitor-owned terms** — language to avoid because it reinforces a competitor's positioning

Ask: "Are there any words your brand always uses — or never uses? Any terms your competitors own that you want to steer clear of?"

Save to: `brand/voice.md` (terminology section)

### After Setup

Confirm all files are saved and say: "Your brand is set up. You can now run `/brand-review` with any content to check it against these guidelines. You can also update any section by asking me to edit your brand voice, products, or customer profiles."

---

## Mode 2: Brand Review

Review marketing content against the brand guidelines stored in `brand/voice.md`, `brand/products.md`, and `brand/customers.md`.

### Inputs

1. **Content to review** — accept content in any of these forms:
   - Pasted directly into the conversation
   - A file path or knowledge base reference
   - A URL to a published page
   - Multiple pieces for batch review

2. **Brand guidelines** — loaded automatically from `brand/` directory files. If files are missing or incomplete, offer to run setup first.

3. **Campaign context** (if applicable) — check `campaigns/` directory for an active campaign brief. If found, also review content against the locked campaign strategy: is the content on-theme? Does it match the campaign arc phase? Does it use the right offer mechanics? Does it align with the creative direction from the brief? Flag deviations as Medium severity.

### Review Process

Evaluate the content against each of these dimensions:

#### Voice and Tone

- Does the content match the brand personality and voice attributes in `brand/voice.md`?
- Is the tone appropriate for the specific channel (per the tone-by-channel table)?
- Are there shifts in voice that feel inconsistent?
- Flag specific sentences or phrases that deviate, with an explanation of why

#### Terminology and Language

- Are preferred brand terms used correctly?
- Are any avoided terms or competitor-owned terms present?
- Is product-specific language accurate (ingredient names, material descriptions, process terms)?
- Are product names, branded terms, and trademarks formatted correctly?

#### Product Claim Verification

Cross-reference the copy against `brand/products.md`:

- Do claims in the content match approved claims for the referenced products?
- Are any unapproved claims being made (benefits, percentages, results)?
- Are price points accurate if mentioned?
- Are ingredient/material descriptions correct?
- Flag any claim that does not appear in the approved product file as **High severity**

#### Messaging and Positioning

- Does the content align with defined messaging pillars or value propositions?
- Is the content speaking to the right customer profile (per `brand/customers.md`)?
- Is the language mirroring how customers actually talk about the product?
- Is the content reinforcing or contradicting brand positioning?

#### Customer Language Alignment

- Does the copy use language that resonates with the target customer profiles?
- Are objections being addressed (or accidentally reinforced)?
- Does the tone match how the audience expects to be spoken to on this channel?

#### Proof-to-Psychology Match

If `brand/customers.md` includes Buyer Psychology sections, check whether the content uses the right TYPE of proof for the stated audience:

- **Research-driven buyer** → needs data, specs, test results, peer reviews, comparison information. If the copy provides only vibes, lifestyle imagery, or emotional appeals without substantiation, the proof strategy is mismatched.
- **Social/aspirational buyer** → needs UGC, creator endorsements, before/after transformations, volume social proof ("10,000 customers switched"). If the copy leads with specs and technical data without social validation, the proof strategy is mismatched.
- **Gift-giver** → needs best-seller status, reviews from other gift-givers ("I got this for my husband and he uses it every day"), price-as-thoughtfulness framing, return policy reassurance. If the copy uses the primary buyer's proof strategy (specs, personal transformation), it's speaking to the wrong person.

Flag mismatches as **Medium severity**: "Proof type doesn't match buyer psychology for [stated audience]. The [audience type] buyer needs [correct proof type], but this content leads with [actual proof type]."

If buyer psychology sections don't exist in `brand/customers.md`, skip this check and note: "For more precise proof-matching, add Buyer Psychology sections to your customer profiles via `/brand-review setup`."

#### Style Guide Compliance

- Grammar and punctuation per style guide (Oxford comma, title case vs. sentence case, etc.)
- Formatting conventions (headers, lists, emphasis)
- Number formatting, date formatting
- Emoji usage appropriate to channel
- Hashtag and mention conventions (for social content)

#### Engagement & Persuasion Quality

Beyond on-brand checks, evaluate whether the content is actually GOOD — would it perform in market? This is the difference between "correct" and "compelling."

**Hook strength:**
- Does the first line / subject line / headline stop the scroll? Read it between two competitor ads — does it stand out?
- Is it specific (scenario, number, sensory detail) or generic ("Don't miss out", "You'll love this")?
- Does it earn the next line, or does it try to do everything at once?

**Variant diversity (for multi-variant content):**
- Are hooks/subject lines genuinely different angles, or the same idea reworded?
- Label each variant's angle (pain point, scenario, social proof, curiosity, direct benefit, identity, contrarian, comparison). Flag if 2+ share the same angle.
- Minimum 4 distinct angles in any set of 5+ variants.

**Competitive distinctiveness:**
- Apply the **swap test**: could a competitor put their name on this copy and use it? If yes, flag as Medium severity: "Copy is on-brand but not distinctive — a competitor could use this with a name swap."
- Check for brand-specific proof (product specs, test data, customer language) vs. generic category claims.

**Persuasion structure:**
- Is there tension before resolution? (Problem/gap before product.) Content that leads with the product has no pull.
- Is proof placed at the moment of doubt, not the moment of introduction?
- Are objections anticipated and addressed, or left for the reader to stew on?
- Is the CTA specific ("Shop the Bottle Parka — $34") or vague ("Shop now")?
- Is urgency real (shipping deadline, seasonal, inventory) or manufactured ("Don't miss out!")?

**Severity guide for engagement issues:**
- **High**: Hook is generic enough to be any brand's. Multiple variants are the same angle reworded. CTA is missing or vague.
- **Medium**: Copy is on-brand and correct but wouldn't outperform a competitor's content. Proof placement is suboptimal. Swap test borderline.
- **Low**: Minor persuasion improvements — could reorder for better tension, could add a specificity detail.

Include engagement findings in the main Detailed Findings table alongside voice, claims, and compliance issues. In the Summary, add a one-line engagement assessment: "Engagement: [Strong / Needs work / Weak] — [reason]."

### Without Brand Guidelines (Generic Review)

If brand files are not configured, evaluate the content for:

#### Clarity
- Is the main message clear within the first sentence or two?
- Are sentences concise and scannable?
- Is the CTA obvious?

#### Consistency
- Is the tone consistent throughout?
- Are terms used consistently?
- Is formatting consistent?

#### Effectiveness
- Is the content appropriate for the implied channel?
- Are claims specific and credible?
- Would the target reader take the desired action?

### Legal and Compliance Flags (Always Checked)

Regardless of whether brand guidelines are configured, flag:

#### General Compliance
- **Unsubstantiated claims** — superlatives ("best", "fastest", "#1") without evidence or qualification
- **Missing disclaimers** — health claims, performance claims, or guarantees that need legal disclaimers
- **Comparative claims** — comparisons to competitors that could be challenged
- **Copyright concerns** — content that appears closely paraphrased from other sources
- **Testimonial issues** — quotes or endorsements without proper attribution or disclosure

#### DTC-Specific Compliance
- **FTC influencer disclosure** — paid partnerships, gifted products, and affiliate links must be clearly and conspicuously disclosed. Flag content that appears to be sponsored or incentivized but lacks "#ad", "#sponsored", "Paid partnership with...", or equivalent disclosure. Disclosure must be hard to miss (not buried in hashtags or below the fold).
- **Subscription auto-renewal language** — if the content promotes a subscription, does it clearly state the recurring charge, frequency, and how to cancel? Flag vague language like "subscribe and save" without the required terms.
- **Before/after claim disclaimers** — beauty, wellness, and supplement content that implies transformation must include "results may vary", "individual results may vary", or similar language. Flag before/after imagery references or testimonials that lack disclaimers.
- **"Results may vary" requirements** — any testimonial, case study, or user story that implies specific outcomes needs a typicality disclaimer. Flag missing disclaimers.
- **UGC usage rights and attribution** — flag content that appears to use customer photos, videos, or quotes without clear indication that usage rights have been obtained. Note when attribution is missing.
- **Health and beauty claim substantiation** — flag claims about product efficacy (e.g., "clinically proven", "dermatologist tested", "reduces wrinkles by 40%") and verify they match approved claims in `brand/products.md`. Unsubstantiated health or beauty claims are **High severity**.

### Tone by Channel Reference

Use this table when evaluating whether tone is appropriate for the content's channel:

| Channel | Tone Characteristics | Example |
|---------|---------------------|---------|
| Product pages | Clear, benefit-led, scannable, trust-building | "Formulated with 2% salicylic acid to clear pores without over-drying. Dermatologist tested." |
| Instagram (feed) | Polished, aspirational, concise, caption-aware | "Your new everyday essential. Clean ingredients, real results." |
| Instagram (Stories/Reels) | Casual, behind-the-scenes, reactive, personality-forward | "POV: you finally found a sunscreen that doesn't leave a white cast" |
| TikTok | Raw, trend-aware, conversational, hook-driven | "I was today years old when I learned my moisturizer was doing nothing. Here's what I switched to." |
| Email | Personal, segmented by intent, clear CTA, value-first | "We noticed you left something behind. Here's 10% off to make it yours." |
| SMS | Ultra-concise, familiar, urgent, one CTA | "Your restock is ready. Grab it before it sells out: [link]" |
| Ads (Meta/Google) | Benefit-led, scroll-stopping, proof-driven, CTA-clear | "3,000+ five-star reviews. See why customers are switching." |
| Blog | Educational, SEO-aware, credible, longer-form | "Everything you need to know about retinol — when to start, how to layer it, and what to avoid." |
| Customer support | Empathetic, solution-oriented, clear, brand-consistent | "We're sorry about that. A replacement is on its way — you should see tracking within 24 hours." |

#### Tone by Situation

| Situation | Tone Adaptation |
|-----------|----------------|
| Product launch | Excited, confident, benefit-forward, FOMO-aware |
| Restock / back in stock | Urgent, celebratory, concise |
| Sale or promotion | Energetic, clear on terms, scarcity-aware |
| Customer success / UGC feature | Grateful, celebratory, crediting the customer |
| Issue or recall | Transparent, empathetic, accountable, solution-first |
| Subscription pitch | Reassuring, value-focused, clear on terms and cancellation |
| Onboarding (post-purchase) | Welcoming, educational, setting expectations |
| Winback | Warm, low-pressure, reminder of value |
| Price increase | Honest, respectful, explaining the why, solution-oriented |

#### Tone Adaptation Rule
The voice attributes remain fixed. Tone dials them up or down based on context. For example, if a brand is "bold and warm":
- In a product launch, dial up boldness
- In an issue response, dial up warmth
- Neither attribute disappears; the balance shifts

### Voice Attribute Spectrums

When evaluating or defining brand voice, position attributes on a spectrum:

| Spectrum | One End | Other End |
|----------|---------|-----------|
| Formality | Formal, institutional | Casual, conversational |
| Authority | Expert, authoritative | Peer-level, collaborative |
| Emotion | Warm, empathetic | Direct, matter-of-fact |
| Complexity | Technical, precise | Simple, accessible |
| Energy | Bold, energetic | Calm, measured |
| Humor | Playful, witty | Serious, earnest |
| Aspiration | Aspirational, elevated | Grounded, relatable |

For each chosen attribute, document it in this format:

**[Attribute name]**
- **We are**: [what this means in practice]
- **We are not**: [common misinterpretation to avoid]
- **This sounds like**: [example sentence demonstrating the attribute]
- **This does NOT sound like**: [example sentence violating the attribute]

Example:

**Approachable**
- **We are**: friendly, clear, jargon-free, like a knowledgeable friend giving honest advice
- **We are not**: dumbed-down, overly casual, or trying too hard to be relatable
- **This sounds like**: "Here's what makes this formula different — and whether it's right for your skin."
- **This does NOT sound like**: "OMG you NEED this, bestie!! It's literally life-changing!!"

### Style Guide Enforcement

#### Grammar and Mechanics
Document and enforce these choices consistently:

| Rule | Options | Example |
|------|---------|---------|
| Oxford comma | Yes / No | "clean, effective, and affordable" vs. "clean, effective and affordable" |
| Sentence case vs. title case (headings) | Sentence / Title | "How to build a routine" vs. "How to Build a Routine" |
| Contractions | Use / Avoid | "you'll" vs. "you will" |
| Em dash spacing | No spaces / Spaces | "this—and more" vs. "this — and more" |
| Numbers | Spell out 1-9, numerals 10+ / Always numerals | "five shades" vs. "5 shades" |
| Percent | % / percent | "50%" vs. "50 percent" |
| Price formatting | $XX / $XX.00 | "$29" vs. "$29.00" |
| Lists | Periods / No periods on fragments | "Hydrates all day." vs. "Hydrates all day" |
| Emoji | Channel-specific rules | Instagram: moderate; Email: minimal; Product pages: none |

#### Formatting Conventions
- Heading hierarchy (when to use H1, H2, H3)
- Bold and italic usage (bold for emphasis, italic for product names or terms)
- Link text (descriptive, never "click here")
- Image alt text requirements (especially for product images and accessibility)
- Hashtag conventions (branded hashtags, quantity limits)
- CTA formatting (button text, link styling)

#### Punctuation and Emphasis
- Exclamation mark policy (limited use, never more than one, channel-dependent)
- Ellipsis usage (acceptable in casual social, avoid in product pages and email)
- ALL CAPS policy (acceptable for single-word emphasis in social/SMS, avoid elsewhere)
- Emoji usage by channel

### Terminology Management

#### Preferred Terms

Maintain a list of preferred terms and their incorrect alternatives:

| Use This | Not This | Notes |
|----------|----------|-------|
| [brand-specific preferred terms] | [brand-specific avoided terms] | [context] |

#### Product and Ingredient Language
- Official product names and capitalization
- How to describe key ingredients or materials (approved phrasing)
- Claim-safe language vs. language that triggers compliance flags
- How to handle shade names, size names, variant names

#### Inclusive Language
- Use gender-neutral language unless targeting a specific demographic
- Avoid ableist language
- Be mindful of skin-tone language and body-related terms (especially in beauty/wellness)
- Use person-first language where appropriate
- Avoid culturally specific idioms that may not translate

#### Competitor and Category Terms
- How to refer to your product category (use your preferred framing)
- How to refer to competitors (by name or generically — most DTC brands avoid naming competitors)
- Terms competitors have coined that you should avoid
- Your preferred differentiation language

## Output Format

Present the review as:

### Summary
- Overall assessment: how well the content aligns with brand standards (or general quality)
- 1-2 sentence summary of the biggest strengths
- 1-2 sentence summary of the most important improvements
- Channel appropriateness check (is the tone right for where this will be published?)

### Detailed Findings

For each issue found, provide:

| Issue | Location | Severity | Suggestion |
|-------|----------|----------|------------|

Where severity is:
- **High** — contradicts brand voice, contains a compliance risk, uses unapproved product claims, or significantly undermines messaging
- **Medium** — inconsistent with guidelines but not damaging; wrong tone for channel
- **Low** — minor style or preference issue

### Product Claim Check

If the content references specific products, include a dedicated section:

| Claim in Content | Approved in brand/products.md? | Status |
|-----------------|-------------------------------|--------|

### Revised Sections

For the top 3-5 highest-severity issues, provide a before/after showing the original text and a suggested revision.

### Legal/Compliance Flags

List any legal or compliance concerns separately with recommended actions. Group by:
- FTC / disclosure issues
- Claim substantiation issues
- Subscription language issues
- UGC / rights issues

## After Review

Ask: "Would you like me to:
- Revise the full content with these suggestions applied?
- Focus on fixing just the high-severity issues?
- Review additional content against the same guidelines?
- Update your brand voice, products, or customer profiles?"
