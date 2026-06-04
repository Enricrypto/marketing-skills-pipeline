# Agent Workflows: Skills in Action

Detailed step-by-step workflows showing exactly when and how each agent activates and applies skills.

---

## 1. RESEARCHER AGENT

**Role**: Market discovery, competitive analysis, customer validation

**Input**: User feature idea or hypothesis ("We should build X")

**Duration**: 3–7 days

**Skills Activated**: market-research, competitive-analysis

---

### WORKFLOW

#### Step 1: Activate market-research Skill
**What**: Customer discovery and TAM/SAM/SOM analysis

**How**:
- Read skill: `~/.claude/skills/marketing/market-research.md`
- Conduct: Customer interviews (5–10 target customers)
- Document: Pain points, desired outcomes, willingness to pay
- Calculate: TAM (total addressable market), SAM (serviceable), SOM (serviceable obtainable)

**Deliverable**: Research notes with customer quotes + market sizing

**Example**:
- Pain point: "[Specific customer problem identified in interviews]"
- Market: [Market size calculation] TAM
- Willingness: $[price range] for solution

---

#### Step 2: Activate competitive-analysis Skill
**What**: Competitive landscape + positioning opportunities

**How**:
- Read skill: `~/.claude/skills/marketing/competitive-analysis.md`
- Analyze: 3–5 direct competitors
- Document: Features, pricing, messaging, strengths, weaknesses
- Identify: White space (what they're NOT doing)
- Map: Positioning matrix (price vs. quality, online vs. local, etc.)

**Deliverable**: Competitive brief with positioning gaps

**Example**:
- Competitors position: "[Generic positioning]" (common approach)
- Your gap: "[Specific differentiator]" (underexploited opportunity)
- Positioning: "[Unique value proposition]"

---

#### Step 3: Synthesize Into Research Report
**Output**: 3–5 page Research Report

**Includes**:
- Customer pain points (ranked by frequency)
- Market size (TAM/SAM/SOM)
- Competitive landscape
- 3 strategic opportunities
- Recommended direction (with confidence level)

**Success Criteria**:
- [ ] Customer research qualitative + quantitative
- [ ] 3+ competitors analyzed
- [ ] Market size estimated
- [ ] Strategic opportunity identified with evidence
- [ ] Next step clear (proceed to Story Writer)

---

## 2. STORY WRITER AGENT

**Role**: Convert research into user story + psychology anchors

**Input**: Research Report (from Researcher)

**Duration**: 2–3 days

**Skills Activated**: marketing-ideas, psychology-patterns, customer-journey

---

### WORKFLOW

#### Step 1: Activate marketing-ideas Skill
**What**: Brainstorm feature angles and value propositions

**How**:
- Read skill: `~/.claude/skills/marketing/marketing-ideas.md`
- Use: Idea frameworks (Problem-Solution, Before-After, Fear-Aspiration)
- Generate: 3–5 distinct feature angles
- Evaluate: Which aligns with research + competitive opportunity

**Deliverable**: 3–5 feature angles with research support

**Example**:
- Angle 1: "[Outcome-focused benefit]"
- Angle 2: "[Authority/expertise angle]"
- Angle 3: "[Risk-reduction angle]"

---

#### Step 2: Activate psychology-patterns Skill
**What**: Identify which Cialdini principle(s) drive the decision

**How**:
- Read skill: `~/.claude/skills/marketing/psychology-patterns.md`
- Map: Research insight → Psychology principle
- Select: 1–2 principles to anchor messaging
- Document: Why this principle resonates with customer

**Deliverable**: Psychology anchor (principle + rationale)

**Example**:
- Research: [Customer pain/desire identified]
- Principle: **[Scarcity/Authority/Social Proof/Loss Aversion/etc.]**
- Messaging anchor: "[How messaging will leverage this principle]"

---

#### Step 3: Activate customer-journey Skill
**What**: Map user workflow from awareness → decision

**How**:
- Read skill: `~/.claude/skills/marketing/customer-journey.md`
- Identify: Awareness → Consideration → Decision → Retention stages
- For each stage: What question do they have? What objection?
- Document: Stage + key message needed

**Deliverable**: Customer journey map with messaging by stage

**Example**:
```
AWARENESS: "[Customer's initial problem/need]"
→ Message: "[Why this is a common problem]"

CONSIDERATION: "[Customer evaluating options]"
→ Message: "[How your solution differs from alternatives]"

DECISION: "[Customer ready to buy]"
→ Message: "[Risk reversal / guarantee / proof]"

RETENTION: "[After purchase]"
→ Message: "[Progress confirmation / community / next milestone]"
```

---

#### Step 4: Write User Story
**Output**: User Story (with acceptance criteria)

**Format**:
```
As a [persona from research],
I want [feature/message that solves pain point],
So that [outcome that addresses psychology principle].

Acceptance Criteria:
- [ ] Feature addresses identified pain point
- [ ] Psychology principle applied to messaging
- [ ] Customer journey stages mapped
- [ ] Success measurable (conversion rate target)
```

**Example**:
```
As a [target customer type],
I want to [achieve specific outcome],
So that [benefit they receive].

Acceptance Criteria:
- [ ] [Feature or messaging] addresses [identified pain]
- [ ] [Psychology principle] applied in copy/design
- [ ] [Journey stage] messaging clear
- [ ] Target conversion rate: [X]%
```

**Success Criteria**:
- [ ] Story aligns with research insights
- [ ] Acceptance criteria are testable
- [ ] Psychology principle identified
- [ ] Customer journey mapped
- [ ] Ready for human approval

---

## 3. SPEC WRITER AGENT

**Role**: Technical blueprint + business context

**Input**: Approved user story (from Story Writer)

**Duration**: 2–3 days

**Skills Activated**: marketing-plan, competitive-analysis, objection-mapping, sales-enablement, pricing-strategy, launch-strategy

---

### WORKFLOW

#### Step 1: Activate marketing-plan Skill
**What**: Campaign roadmap + phase sequencing

**How**:
- Read skill: `~/.claude/skills/marketing/marketing-plan.md`
- Define: Phase 1 (awareness) → Phase 2 (consideration) → Phase 3 (decision)
- Assign: Channels + budget + duration for each phase
- Document: Success metrics per phase

**Deliverable**: Campaign phases with channels + budgets

**Example**:
```
PHASE 1 (Weeks 1–2): Awareness
- Channel 1: [Organic/Paid/Social]
- Channel 2: [Another acquisition channel]
- Budget: $[amount]
- Success metric: [conversion metric to track]

PHASE 2 (Weeks 3–4): Consideration
- Channel 1: [Email/Content/Retargeting]
- Channel 2: [Social proof/Community]
- Budget: $[amount]
- Success metric: [engagement metric]

PHASE 3 (Week 5+): Decision + Retention
- Channel 1: [Direct sales/Offers]
- Channel 2: [Community/Loyalty]
- Budget: $[amount]
- Success metric: [conversion/retention metric]
```

---

#### Step 2: Activate competitive-analysis Skill (revisited)
**What**: Competitive positioning for this specific campaign

**How**:
- Read skill: `~/.claude/skills/marketing/competitive-analysis.md`
- Compare: How should we position differently from competitors?
- Identify: Messaging angles they're NOT using
- Document: Differentiation strategy

**Deliverable**: Positioning statement

**Example**:
```
Competitors position: "[Generic positioning]"
Your positioning: "[Specific, differentiated value prop]"
Messaging differentiator: "[What makes you uniquely qualified/different]"
```

---

#### Step 3: Activate objection-mapping Skill
**What**: Customer objections + counter-arguments

**How**:
- Read skill: `~/.claude/skills/marketing/objection-mapping.md`
- List: Top 5 objections from research + journey map
- For each: Write counter-argument + proof (testimonial, stat, guarantee)
- Document: Where to place each objection handler

**Deliverable**: Objection map with counter-arguments

**Example**:
```
OBJECTION 1: "[Common customer concern]"
COUNTER: [Evidence/testimonial/stat addressing this]
PLACEMENT: [Where on landing page/email/funnel]

OBJECTION 2: "[Price or commitment concern]"
COUNTER: [Payment plan/guarantee/proof]
PLACEMENT: [Checkout page/pricing section]

OBJECTION 3: "[Efficacy/results concern]"
COUNTER: [Case study/before-after/testimonial]
PLACEMENT: [Above fold/social proof section]
```

---

#### Step 4: Activate sales-enablement Skill
**What**: Sales team materials + talking points

**How**:
- Read skill: `~/.claude/skills/marketing/sales-enablement.md`
- Create: Sales script, objection handlers, pricing justification
- Document: Response templates for common questions
- Prepare: Team training agenda

**Deliverable**: Sales enablement kit

**Example**:
```
SALES SCRIPT (Discovery Call):
"Tell me about [situation]. What's the biggest challenge?" → Listen
"How long has this been going on?" → Understand urgency
"What have you tried so far?" → Understand past failures
"If we could fix this [timeframe], how would that change [outcome]?" → Paint vision

OBJECTION HANDLER:
Customer: "[Common objection]"
Script: "[Counter-argument with proof/guarantee]"

PRICING JUSTIFICATION:
"$[price] = $[price per unit/time] for [specific value]
Alternative cost = $[comparison] with [drawback]
You save $[amount] and get [benefit]"
```

---

#### Step 5: Activate pricing-strategy Skill
**What**: Price model + tier decisions

**How**:
- Read skill: `~/.claude/skills/marketing/pricing-strategy.md`
- Analyze: Value delivered vs. price
- Consider: Payment plans, bundles, tiered options
- Document: Pricing rationale

**Deliverable**: Pricing model + justification

**Example**:
```
OPTION 1: Single tier ($X, [description])
- Pro: [Simple/Clear/Focused]
- Con: [Leaves money on table/Too restrictive]

OPTION 2: Tiered ($X Basic, $Y Standard, $Z Premium)
- Pro: [Captures segments/Flexibility]
- Con: [Complex/Confusion risk]

RECOMMENDATION: [Option selected]
Rationale: [Why this tier structure best serves market]
```

---

#### Step 6: Activate launch-strategy Skill
**What**: Launch sequencing + rollout plan

**How**:
- Read skill: `~/.claude/skills/marketing/launch-strategy.md`
- Phase: Soft launch (beta) → launch (GA) → scale
- Identify: Success metrics for each phase
- Document: Rollback plan if metrics miss

**Deliverable**: Launch roadmap

**Example**:
```
SOFT LAUNCH (Week 1):
- Audience: [Internal/Beta customers/Early adopters]
- Goal: [Initial validation metric]
- Metric: [Target conversion/engagement rate]
- Rollback: If [failure condition], return to [previous step]

LAUNCH (Week 2):
- Audience: [Target market segment]
- Goal: [Volume metric]
- Metric: [Expected conversion/acquisition rate]
- Scale condition: If [success metric], increase budget/audience

SCALE (Week 3+):
- Audience: [Broader market]
- Goal: [Sustained growth metric]
- Metric: [Predictable CAC/LTV ratio]
```

---

#### Step 7: Write Technical Brief
**Output**: 2–3 page Technical Brief

**Includes**:
- Campaign phases + channels
- Positioning statement + differentiation
- Objection map with counter-arguments
- Sales script + enablement materials
- Pricing model + rationale
- Launch roadmap + success metrics
- Risks + rollback plan

**Success Criteria**:
- [ ] All acceptance criteria from story mapped to deliverables
- [ ] Budget + timeline clear
- [ ] Success metrics defined and measurable
- [ ] Risks identified with mitigation
- [ ] Ready for human approval

---

## 4. BACKEND BUILDER AGENT

**Role**: API routes, databases, integrations, automation

**Input**: Approved brief (from Spec Writer)

**Duration**: 1–2 weeks

**Skills Activated**: analytics-setup, conversion-audit, revops, seo-programmatic (conditional), churn-prevention (conditional)

---

### WORKFLOW

#### Step 1: Activate analytics-setup Skill
**What**: Conversion tracking infrastructure

**How**:
- Read skill: `~/.claude/skills/marketing/analytics-setup.md`
- Setup: Analytics events for each conversion milestone
- Create: Conversion goals based on customer journey
- Document: Event names + parameters
- Verify: Tracking pixels firing in development

**Deliverable**: Analytics implementation (code + events)

**Example**:
```javascript
// Event: Landed on key page
gtag('event', 'page_view', {
  page_path: '/[key-page]',
  page_title: '[Page title]'
});

// Event: Form submission (first conversion milestone)
gtag('event', 'form_submit', {
  form_id: '[form_identifier]',
  form_name: '[form_purpose]'
});

// Event: Second conversion milestone
gtag('event', '[milestone_name]', {
  event_value: [value_amount],
  milestone_type: '[description]'
});

// Event: Final conversion (revenue/customer)
gtag('event', 'conversion_complete', {
  event_value: [customer_value],
  conversion_type: '[description]'
});
```

---

#### Step 2: Activate conversion-audit Skill
**What**: Establish baseline conversion rates

**How**:
- Read skill: `~/.claude/skills/marketing/conversion-audit.md`
- Measure: Current rates for each funnel stage
- Identify: Conversion bottlenecks (where do people drop off?)
- Document: Baseline metrics

**Deliverable**: Baseline audit report

**Example**:
```
BASELINE AUDIT (Before Campaign):
Stage 1 (Awareness): 1,000 visitors/month
Stage 2 (Consideration): 50 leads (5% conversion)
Stage 3 (Decision): 15 conversions (30% of leads = 1.5% of visitors)

BOTTLENECK: Only 30% of Stage 2 → Stage 3
→ Likely causes: [Common drop-off reasons]
→ Fix: [Targeted improvement]
```

---

#### Step 3: Activate revops Skill
**What**: CRM integration + automation

**How**:
- Read skill: `~/.claude/skills/marketing/revops.md`
- Setup: Lead capture → CRM
- Automate: Lead routing, email triggers, task assignments
- Document: CRM workflow automation

**Deliverable**: CRM automation (code + workflows)

**Example**:
```
WORKFLOW: [Initial capture] → CRM → [Follow-up automation]

1. Customer completes [action]
   ↓
2. Data → CRM
   ↓
3. [Qualification logic applied]
   ↓
4. Lead assigned to [team member/process]
   ↓
5. Email trigger: "[Automated message]"
   ↓
6. If no response in [timeframe]: [Escalation action]
   ↓
7. If [positive action]: [Next step in workflow]
```

---

#### Step 4: (Conditional) Activate seo-programmatic Skill
**What**: Programmatic content generation (if applicable)

**How**:
- Read skill: `~/.claude/skills/marketing/seo-programmatic.md`
- Create: Content template for scaled generation
- Generate: Pages/content at scale using template
- Document: Deduplication rules + link structure

**Deliverable**: Programmatic content (templates + generated assets)

**Example**:
```
TEMPLATE: /[resource]-[parameter]/index.md

Title: "[Resource title] for {{parameter}}"
Content sections:
- Why [Audience] Choose [Your approach]
- Local/Specific Proof (from [parameter])
- Your Method/Approach
- FAQ for [Parameter]
- CTA: "[Action] for {{parameter}}"

GENERATED ASSETS:
- /[resource]-[param1]/
- /[resource]-[param2]/
- /[resource]-[param3]/
... (scale to [N] variations)
```

---

#### Step 5: Write Backend Code
**Output**: API routes + database models + integrations

**Includes**:
- Form submission endpoint
- Lead creation in CRM
- Analytics event tracking
- Email automation triggers
- Payment processing (if applicable)
- Conversion goal definitions

**Success Criteria**:
- [ ] All endpoints implemented
- [ ] Database models created
- [ ] Conversion tracking wired
- [ ] CRM integration tested
- [ ] Email automation tested
- [ ] Typecheck passes
- [ ] Unit tests written (>80% coverage)

---

## 5. FRONTEND BUILDER AGENT

**Role**: Components, pages, UI, forms, landing pages

**Input**: Approved brief + Backend API summary

**Duration**: 1–2 weeks

**Skills Activated**: landing-page-copy, form-optimization, social-proof-strategy, schema-markup, psychology-patterns

---

### WORKFLOW

#### Step 1: Activate landing-page-copy Skill
**What**: Page structure + persuasive copy

**How**:
- Read skill: `~/.claude/skills/marketing/landing-page-copy.md`
- Create: Page outline (headline → subheading → sections → CTA)
- Write: Copy for each section (problem → solution → proof → CTA)
- Document: Copy rationale

**Deliverable**: Landing page outline + copy

**Example**:
```
HEADLINE: "[Specific benefit statement]"
(Psychology: [Principle], Urgency: [If applicable])

SUBHEADING: "[Risk reversal or unique guarantee]"
(Removes: [Primary barrier])

SECTION 1: Problem
Headline: "[Customer pain point]"
Copy: "[Specific examples of the problem]"

SECTION 2: Solution
Headline: "[How your solution works]"
Copy: "[Explain method/approach briefly]"

SECTION 3: Social Proof
Testimonials: [Number] customer stories with results
(Psychology: Social proof, Authority)

SECTION 4: Guarantee/Risk Reversal
Copy: "[Clear guarantee statement with timeline]"
(Psychology: Loss aversion mitigation)

SECTION 5: CTA
Button: "[Specific action]"
Copy: "[Urgency/timeline + low barrier]"
```

---

#### Step 2: Activate form-optimization Skill
**What**: Reduce form friction

**How**:
- Read skill: `~/.claude/skills/marketing/form-optimization.md`
- Minimize: Form fields (ideal = 3 fields max)
- Sequence: Ask non-sensitive questions first → sensitive
- Document: Field rationale

**Deliverable**: Form design + field sequence

**Example**:
```
FORM: "[Form purpose]"

FIELDS (Optimized):
1. [Low-barrier field] (Text input)
   Rationale: [Why this first]
   
2. [Qualification field] (Dropdown/Radio)
   Rationale: [Route/filter logic]
   
3. [Email/Contact field] (Email input)
   Rationale: [Essential for follow-up]

REMOVED FIELDS:
- [Field name] (Rationale: [Why removed for initial capture])
- [Field name] (Rationale: [Ask after initial conversion])

RESULT: [N] fields = [Expected impact on conversion]
```

---

#### Step 3: Activate social-proof-strategy Skill
**What**: Build trust through social signals

**How**:
- Read skill: `~/.claude/skills/marketing/social-proof-strategy.md`
- Collect: Customer testimonials (video, text, photos)
- Place: Social proof above the fold
- Document: Which proof types work

**Deliverable**: Social proof components

**Example**:
```
TESTIMONIAL BLOCK (Above fold positioning):
Format: [Video/Text/Photo-based testimonial]
- Customer name + [key detail]
- Before state: "[Initial problem/skepticism]"
- After state: "[Results achieved]"
- Quote: "[Specific benefit/transformation]"

TEXT TESTIMONIALS (Support sections):
- [N] short testimonials (2–3 sentences each)
- Include: Name, [relevant detail], result achieved
- Spread: Across page for multiple trust touchpoints

STATS/PROOF:
- "[Percentage]% of [customers] achieved [outcome]"
- "[Number]+ [items/customers] [metric]"
- "[Rating]/5 stars, [number] reviews"
```

---

#### Step 4: Activate schema-markup Skill
**What**: Structured data for AI discoverability

**How**:
- Read skill: `~/.claude/skills/marketing/schema-markup.md`
- Add: Appropriate schema types (LocalBusiness, Product, Article, etc.)
- Add: Review/AggregateRating schema
- Validate: Using schema validation tools

**Deliverable**: JSON-LD schema code

**Example**:
```json
{
  "@context": "https://schema.org",
  "@type": "[Schema type]",
  "name": "[Business/Product name]",
  "description": "[Brief description]",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "[Address]",
    "addressLocality": "[City]",
    "addressRegion": "[Region]",
    "postalCode": "[Code]",
    "addressCountry": "[Country]"
  },
  "telephone": "[Phone]",
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "[Rating]",
    "reviewCount": "[Count]"
  },
  "offers": {
    "@type": "Offer",
    "priceCurrency": "[Currency]",
    "price": "[Price]",
    "name": "[Offer name]"
  }
}
```

---

#### Step 5: Activate psychology-patterns Skill
**What**: Apply behavioral principles to design

**How**:
- Read skill: `~/.claude/skills/marketing/psychology-patterns.md`
- Apply: [Principle] to [Design element]
- Apply: [Principle] to [Copy placement]
- Document: Each design decision linked to psychology

**Deliverable**: Psychology-informed design

**Example**:
```
DESIGN DECISION → PSYCHOLOGY PRINCIPLE

1. Headline "[Specific benefit with number/timeline]"
   → Specificity reduces anxiety (Certainty Effect)

2. "[Guarantee statement]"
   → Loss Aversion: Risk of loss > opportunity for gain
   → Risk Reversal removes barrier

3. Testimonials above fold (not bottom)
   → Social Proof: Early success demonstration
   → Reduces decision anxiety

4. [High-contrast button color]
   → Attention: Color contrast draws eye
   → Action: Button text = specific action verb

5. "[Progress indicator or timeline]"
   → Clarity: Reduces cognitive load
   → Timeline: Reduces uncertainty
```

---

#### Step 6: Build Landing Page Components
**Output**: React/Next.js components + pages

**Includes**:
- Hero section (headline + CTA)
- Problem section
- Solution section
- Social proof section
- FAQ section
- Form component (optimized)
- Footer with schema markup

**Success Criteria**:
- [ ] Page responsive (mobile + desktop)
- [ ] Form submits to backend API
- [ ] All copy matches brief
- [ ] Social proof visible above fold
- [ ] Schema markup valid
- [ ] Typecheck passes
- [ ] Component tests written
- [ ] Performance: Core Web Vitals pass

---

## 6. MARKETING BUILDER AGENT

**Role**: Copy, ads, email, landing pages, funnels

**Input**: Approved brief + Backend/Frontend APIs

**Duration**: 1–2 weeks

**Skills Activated**: copywriting, ad-creative, email-sequences, + conditional (pricing-strategy, lead-magnets, referral-programs, etc.)

---

### WORKFLOW

#### Step 1: Activate copywriting Skill
**What**: Persuasive messaging across all channels

**How**:
- Read skill: `~/.claude/skills/marketing/copywriting.md`
- Write: Headline variations (3–5)
- Write: Body copy (problem → solution → proof → CTA)
- Test: Headlines against psychology principles
- Document: Copy rationale

**Deliverable**: Copy variations for A/B testing

**Example**:
```
HEADLINE VARIATION 1: "[Benefit-focused headline]"
Psychology: [Principle]
Targets: [Audience segment]

HEADLINE VARIATION 2: "[Authority/guarantee headline]"
Psychology: [Principle]
Targets: [Different audience segment]

HEADLINE VARIATION 3: "[Pain/loss-focused headline]"
Psychology: [Principle]
Targets: [Yet another segment]

BODY COPY (Variation 1):
Problem: "[Specific pain point from research]"
Solution: "[How your solution addresses this]"
Proof: "[Stat/testimonial/guarantee]"
CTA: "[Specific action]"
```

---

#### Step 2: Activate ad-creative Skill
**What**: Visual ads + copy pairing

**How**:
- Read skill: `~/.claude/skills/marketing/ad-creative.md`
- Create: 3 image variations (states: problem, solution, proof)
- Create: 3 copy variations per image
- Design: Ad anatomy (image → headline → body → CTA)
- Document: Which combo targets which audience

**Deliverable**: Ad variations ready for platforms

**Example**:
```
AD VARIATION 1:
Image: [State representing problem]
Headline: "[Problem-focused headline]"
Body: "[Problem + solution + urgency]"
CTA: "[Action button]"
Target: [Audience segment]

AD VARIATION 2:
Image: [State representing success]
Headline: "[Outcome-focused headline]"
Body: "[Results achieved + guarantee]"
CTA: "[Action button]"
Target: [Different audience]

AD VARIATION 3:
Image: [Authority/expert image]
Headline: "[Expertise/authority headline]"
Body: "[Methodology + differentiation]"
CTA: "[Action button]"
Target: [Skeptical audience]
```

---

#### Step 3: Activate email-sequences Skill
**What**: Automated email flows

**How**:
- Read skill: `~/.claude/skills/marketing/email-sequences.md`
- Create: Onboarding sequence (immediate, day 3, day 7)
- Create: Nurture sequence for interested prospects
- Create: Post-purchase/confirmation sequence
- Document: Triggers + if/then logic

**Deliverable**: Email sequences with templates

**Example**:
```
SEQUENCE 1: [Initial action trigger]

Email 1 (Immediate): "[Welcome/Confirmation message]"
- Include: [Key information from their action]
- Include: [Next step/recommendation]
- CTA: "[Specific action]"

Email 2 (Day X, If [condition]): "[Social proof/case study]"
- Include: [Relevant example]
- Include: "[Specific benefit shown]"
- CTA: "[Continue action]"

Email 3 (Day Y, If [condition]): "[Urgency/scarcity]"
- Include: [Time-limited element]
- Include: [Guarantee/risk reversal]
- CTA: "[Complete action]"

SEQUENCE 2: [Confirmation/Purchase trigger]

Email 1 (Immediate): "[Next steps/Expectations]"
- Include: [Timeline/Deliverable]
- Include: [FAQ/Preparation]
- Include: [Support info]

Email 2 (Day before/After): "[Reminder/Progress]"
- Include: [Timeline confirmation]
- Include: [FAQ/Help resources]

Email 3 (Post-completion): "[Feedback/Continuation]"
- Include: [Feedback request]
- Include: [Next milestone/upsell]
```

---

#### Step 4: (Conditional) Activate pricing-strategy Skill
**What**: Price messaging + payment plans

**How**:
- Read skill: `~/.claude/skills/marketing/pricing-strategy.md`
- Create: Pricing messaging (reframing)
- Create: Payment plans (remove barriers)
- Document: Price psychology

**Deliverable**: Pricing messaging + payment terms

**Example**:
```
PRICING MESSAGING:
"$X for [offering]"
→ Reframe: "$X/[period] for [specific value]"
→ Compare: "Alternative = $Y with [drawback]"
→ Benefit: "You save $Z and get [outcome]"

PAYMENT PLAN:
- Option 1: Full payment upfront → [Incentive if any]
- Option 2: Installments ($X × [periods]) → [Total same or higher]
- Option 3: [Alternative model] → [Terms]

MESSAGING: "[Most accessible option highlighted]" (highlights option, not full price)
```

---

#### Step 5: Write Email Copy + Ad Copy + Marketing Copy
**Output**: Email templates, ad copy variations, promotional materials

**Includes**:
- Email sequences (on-boarding, nurture, post-purchase, win-back)
- Ad copy variations per image (9+ ad combos)
- Landing page promotional copy
- CTA button text variations
- Social media post copy

**Success Criteria**:
- [ ] All copy tested against psychology principles
- [ ] Ad variations ready for A/B testing
- [ ] Email sequences have clear triggers + if/then logic
- [ ] Copy matches landing page messaging (consistency)
- [ ] CTA specific + action-oriented

---

## 7. TEST VERIFIER AGENT

**Role**: Write acceptance tests, verify criteria met

**Input**: All built code + approved acceptance criteria

**Duration**: 1 week

**Skills Activated**: ab-testing, conversion-audit, analytics-setup, google-ads (conditional), meta-ads (conditional)

---

### WORKFLOW

#### Step 1: Activate ab-testing Skill
**What**: A/B test design + statistical rigor

**How**:
- Read skill: `~/.claude/skills/marketing/ab-testing.md`
- Design: Control vs. Variant
- Calculate: Sample size for statistical significance
- Document: Hypothesis, primary metric, secondary metrics

**Deliverable**: A/B test plan

**Example**:
```
A/B TEST: [Element being tested]

HYPOTHESIS: [Test assumption: "X increases Y"]

CONTROL: [Current version]
VARIANT: [New version]

PRIMARY METRIC: [Key measurement]
- Control baseline: [Current %]
- Expected improvement: +[%]
- Sample size needed: [N] per variant
- Duration: ~[timeframe]

SECONDARY METRICS:
- [Metric 2] (expected: [direction])
- [Metric 3] (expected: [direction])

SUCCESS CRITERIA:
- If Variant ≥ [target]: Winning variant
- If Variant < [target]: Continue with Control
```

---

#### Step 2: Activate conversion-audit Skill
**What**: Baseline conversion measurement

**How**:
- Read skill: `~/.claude/skills/marketing/conversion-audit.md`
- Measure: Conversion rates per funnel stage
- Measure: Drop-off points
- Document: Bottleneck analysis

**Deliverable**: Conversion audit report

**Example**:
```
CONVERSION AUDIT (Week 1):

Stage 1: [Visitors]: [Number]
Stage 2: [Leads]: [Number] ([%] conversion)
Stage 3: [Customers]: [Number] ([%] conversion)

BOTTLENECK: Only [%] of Stage [X] → Stage [Y]
→ Root cause: [Hypothesis]
→ Fix: [Proposed improvement]
```

---

#### Step 3: Activate analytics-setup Skill
**What**: Verify conversion tracking active

**How**:
- Read skill: `~/.claude/skills/marketing/analytics-setup.md`
- Test: All events firing
- Verify: Conversion goals configured
- Document: Event names + parameters matching

**Deliverable**: Conversion tracking audit

**Example**:
```
TRACKING VERIFICATION:

Event 1: [Event name]
- When: [Trigger condition]
- Parameters: [Tracked data]
- Verified: ✓ Firing in [Analytics platform]
- Used for: [Goal/Metric]

Event 2: [Event name]
- When: [Trigger condition]
- Parameters: [Tracked data]
- Verified: ✓ Firing in [Analytics platform]
- Used for: [Goal/Metric]

STATUS: All tracking verified and active
```

---

#### Step 4: Write Acceptance Tests
**Output**: Test suite (acceptance tests)

**Includes**:
- Test: [Feature] loads and displays [elements]
- Test: [Form/Action] submission captures data + sends backend
- Test: [Analytics events] fire on [trigger]
- Test: [Email automation] triggers on [condition]
- Test: [A/B test] serving at [split %]

**Success Criteria**:
- [ ] All acceptance criteria have corresponding test
- [ ] Tests passing (100% pass rate)
- [ ] Coverage > 80% of critical paths
- [ ] A/B test sample size calculated

---

## 8. VALIDATOR AGENT

**Role**: Compare implementation vs. brief, audit for gaps

**Input**: All built code + all tests + approved brief

**Duration**: 3–5 days

**Skills Activated**: conversion-audit, analytics-setup, seo-audit-gsp, competitive-analysis, attribution (conditional)

---

### WORKFLOW

#### Step 1: Activate conversion-audit Skill
**What**: Verify conversion targets met

**How**:
- Read skill: `~/.claude/skills/marketing/conversion-audit.md`
- Check: Conversion rates ≥ acceptance criteria
- Check: All funnel stages measurable
- Document: Gap if actual < target

**Deliverable**: Conversion gap report

**Example**:
```
ACCEPTANCE CRITERIA: [Stage 1] → [Stage 2] converts [X]%

ACTUAL MEASUREMENT (Week 1):
- Stage 1: [Number]
- Stage 2: [Number]
- Conversion rate: [%] [✓ PASS / ✗ FAIL]

VALIDATION: [Pass/Fail with details]
```

---

#### Step 2: Activate analytics-setup Skill
**What**: Verify tracking infrastructure complete

**How**:
- Read skill: `~/.claude/skills/marketing/analytics-setup.md`
- Check: All events implemented + firing
- Check: Conversion goals configured
- Check: Automations working
- Document: Any gaps

**Deliverable**: Analytics implementation audit

**Example**:
```
ANALYTICS CHECKLIST:

[ ✓ ] Analytics property created + tracking active
[ ✓ ] [Event 1] fires + counts
[ ✓ ] [Event 2] fires + counts
[ ✓ ] [Event 3] fires + counts
[ ✗ ] [Event 4] not yet implemented
      → Gap: [Needed for: measuring X]
      → Timeline: [When to complete]

ACTION: [What needs to be done]
```

---

#### Step 3: Activate competitive-analysis Skill
**What**: Verify positioning differentiation vs. competitors

**How**:
- Read skill: `~/.claude/skills/marketing/competitive-analysis.md`
- Check: Messaging ≠ competitors' messaging
- Check: Differentiation present (from brief)
- Check: Proof/testimonials match
- Document: Positioning confirmation

**Deliverable**: Competitive positioning validation

**Example**:
```
POSITIONING REQUIREMENT (from brief):
"[Unique value proposition]"

VALIDATION:
Page headline: [Text] ✓
Guarantee: [Text] ✓ (Differentiator)
Proof: [What used] ✓

Comparison to competitors:
- Competitor A: [Position] ✓ Different
- Competitor B: [Position] ✓ Different

VALIDATION: Positioning differentiated
```

---

#### Step 4: Write Validation Report
**Output**: Gap Report (critical/major/minor)

**Format**:
```
ACCEPTANCE CRITERIA → IMPLEMENTATION VALIDATION

Criterion 1: [Specific criteria]
Status: ✓ PASS ([Evidence])

Criterion 2: [Specific criteria]
Status: ⚠ MAJOR GAP ([Problem])
Fix needed: [Solution + Timeline]

Criterion 3: [Specific criteria]
Status: ✓ PASS ([Evidence])

OVERALL: [X]/[Y] criteria passed, [N] gaps (critical/major/minor)
Ready for launch: [Yes/No with conditions]
```

**Success Criteria**:
- [ ] Zero critical gaps
- [ ] All major gaps have fix plan
- [ ] Acceptance criteria validated
- [ ] Ready for human PR approval

---

## End-to-End Flow Recap

```
INPUT: Feature idea
  ↓
RESEARCHER: market-research + competitive-analysis
  ↓ (3-day research)
STORY WRITER: marketing-ideas + psychology-patterns + customer-journey
  ↓ (create user story)
CHECKPOINT 1: Human approves story
  ↓
SPEC WRITER: marketing-plan + competitive-analysis + objection-mapping + sales-enablement + pricing-strategy + launch-strategy
  ↓ (create brief)
CHECKPOINT 2: Human approves brief
  ↓ (parallel build)
BACKEND BUILDER: analytics-setup + conversion-audit + revops + [seo-programmatic, churn-prevention]
FRONTEND BUILDER: landing-page-copy + form-optimization + social-proof-strategy + schema-markup + psychology-patterns
MARKETING BUILDER: copywriting + ad-creative + email-sequences + [pricing, lead-magnets, referral-programs]
  ↓ (all builders complete)
TEST VERIFIER: ab-testing + conversion-audit + analytics-setup + [google-ads, meta-ads]
  ↓ (tests pass)
VALIDATOR: conversion-audit + analytics-setup + seo-audit-gsp + competitive-analysis + [attribution]
  ↓ (gaps documented, no critical blockers)
CHECKPOINT 3: Human approves PR + gaps
  ↓
SHIPPED ✓
```

---

**Created**: 2026-06-04  
**Agents**: 8  
**Skills**: 45 (used in 16 agent workflows)  
**Checkpoints**: 3 human approval gates  
**Examples**: Generic, templatable for any industry
