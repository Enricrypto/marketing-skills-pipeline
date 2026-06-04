# Marketing Skills Pipeline

A comprehensive 45-skill marketing library with agent workflows, skill dependencies, and audit framework. Built for the Marketing OS and applied across SaaS, services, and growth teams.

**Location**: `/Users/enriqueibarra/.claude/skills/marketing/`

---

## Agent Workflow & Skills Pipeline

```
RESEARCHER AGENT
├─ Input: User story (feature idea)
├─ Skills: [market-research, competitive-analysis]
├─ Output: Research Report
└─ Gates next step

         ↓ (3-day decision)

STORY WRITER AGENT
├─ Input: Research Report
├─ Skills: [marketing-ideas, customer-journey, psychology-patterns]
├─ Output: User Story + Acceptance Criteria
└─ CHECKPOINT 1: Approve story (human)

         ↓ (explicit approval)

SPEC WRITER AGENT
├─ Input: Approved user story
├─ Skills: [marketing-plan, competitive-analysis]
├─ Output: Technical Brief (what to build + why)
└─ CHECKPOINT 2: Approve brief (human)

         ↓ (explicit approval)

BUILDER AGENTS (Parallel)
├─ BACKEND BUILDER
│  ├─ Input: Approved brief
│  ├─ Skills: [analytics-setup, conversion-audit, revops]
│  └─ Output: API routes, databases, services
│
├─ FRONTEND BUILDER
│  ├─ Input: Approved brief + Backend API summary
│  ├─ Skills: [landing-page-copy, form-optimization, social-proof-strategy]
│  └─ Output: Components, pages, UI
│
└─ Marketing BUILDER
   ├─ Input: Approved brief
   ├─ Skills: [copywriting, ad-creative, email-sequences, pricing-strategy]
   └─ Output: Copy, ads, funnels, landing pages

         ↓ (all builders done)

TEST VERIFIER AGENT
├─ Input: All built code + acceptance criteria
├─ Skills: [ab-testing, conversion-audit, analytics-setup]
├─ Output: Acceptance tests (pass/fail)
└─ Gates next step

         ↓ (tests pass)

VALIDATOR AGENT
├─ Input: Implementation + tests
├─ Skills: [conversion-audit, analytics-setup, competitive-analysis]
├─ Output: Gap report (severity: critical/major/minor)
└─ CHECKPOINT 3: Approve PR (human)

         ↓ (explicit approval)

SHIPPED ✓
```

---

## Skills by Category (45 Total)

### SEO & Content (8)
| Skill | Agent | When to Use |
|-------|-------|------------|
| seo-audit-gsp | Researcher, Validator | Baseline ranking audit |
| seo-programmatic | Backend Builder | Templated page generation |
| seo-authority | Backend Builder | Build domain authority (90+ days) |
| schema-markup | Frontend Builder | Structured data for AI discoverability |
| ai-seo | Story Writer | AI search optimization |
| content-strategy | Spec Writer | Content roadmap |
| site-architecture | Spec Writer | URL structure, hierarchy |
| analytics-setup | Test Verifier, Validator | Conversion tracking |

### CRO & Psychology (9)
| Skill | Agent | When to Use |
|-------|-------|------------|
| conversion-audit | Validator | Baseline conversion rate |
| landing-page-copy | Frontend Builder | Page copy + structure |
| psychology-patterns | Story Writer | Behavioral anchors for features |
| objection-mapping | Spec Writer | Handle customer objections |
| form-optimization | Frontend Builder | Reduce form friction |
| pricing-psychology | Builder | Price positioning |
| social-proof-strategy | Frontend Builder | Testimonials, social signals |
| urgency-scarcity | Builder | Time-limited offers |
| ab-testing | Test Verifier | Statistical validation |

### Copy & Content (6)
| Skill | Agent | When to Use |
|-------|-------|------------|
| email-sequences | Builder | Onboarding, nurture flows |
| copywriting | Builder | Persuasive writing |
| cold-email | Builder | Outreach |
| social-content | Builder | Social media posts |
| copy-editing | Builder | Polish & quality |
| video-scripts | Builder | Video marketing |

### Sales & GTM (7)
| Skill | Agent | When to Use |
|-------|-------|------------|
| sales-enablement | Spec Writer | Sales team training |
| pricing-strategy | Spec Writer | Price model, tiers |
| competitor-comparison | Researcher, Validator | Positioning vs. competitors |
| revops | Backend Builder | Revenue operations, CRM |
| prospecting | Builder | Lead generation |
| launch-strategy | Spec Writer | Launch sequencing |
| market-research | Researcher | Customer discovery |

### Growth & Retention (6)
| Skill | Agent | When to Use |
|-------|-------|------------|
| lead-magnets | Builder | Lead capture |
| free-tool-strategy | Builder | Viral lead generation |
| referral-programs | Builder | Word-of-mouth growth |
| churn-prevention | Backend Builder | Reduce customer cancellation |
| lifecycle-email | Builder | Automation by stage |
| community-marketing | Builder | Sticky product + moat |

### Paid & Measurement (4)
| Skill | Agent | When to Use |
|-------|-------|------------|
| google-ads | Builder, Test Verifier | Search ads |
| meta-ads | Builder, Test Verifier | Facebook/Instagram ads |
| ad-creative | Builder | Ad design + copy |
| attribution | Validator | Multi-touch attribution |

### Strategy (5)
| Skill | Agent | When to Use |
|-------|-------|------------|
| marketing-plan | Spec Writer | Annual roadmap |
| competitive-analysis | Researcher, Validator | Competitive positioning |
| marketing-ideas | Story Writer | Ideation |
| customer-journey | Story Writer | Customer flow mapping |
| (implied) |  |  |

---

## Skill Dependencies & Workflow

```
CORE FOUNDATION
├─ market-research
├─ competitive-analysis
└─ customer-journey

AWARENESS & POSITIONING
├─ marketing-ideas
├─ marketing-plan
├─ content-strategy
└─ site-architecture

MESSAGING & COPY
├─ copywriting
├─ landing-page-copy
├─ email-sequences
├─ ad-creative
└─ video-scripts

PSYCHOLOGY & CONVERSION
├─ psychology-patterns
├─ objection-mapping
├─ form-optimization
├─ social-proof-strategy
├─ urgency-scarcity
└─ conversion-audit

PAID ACQUISITION
├─ google-ads
├─ meta-ads
└─ attribution

ORGANIC & SEO
├─ seo-audit-gsp
├─ seo-programmatic
├─ seo-authority
├─ ai-seo
├─ schema-markup
└─ analytics-setup

RETENTION & GROWTH
├─ lifecycle-email
├─ churn-prevention
├─ referral-programs
├─ free-tool-strategy
├─ lead-magnets
└─ community-marketing

SALES & OPERATIONS
├─ pricing-strategy
├─ pricing-psychology
├─ sales-enablement
├─ revops
├─ prospecting
└─ cold-email

TESTING & VALIDATION
├─ ab-testing
├─ conversion-audit
└─ analytics-setup
```

---

## Agent Skills Matrix

### Researcher Agent
**Role**: Market discovery, competitive landscape, customer research

**Skills used**:
- market-research (primary)
- competitive-analysis (primary)
- customer-journey (secondary)

**Deliverable**: Research Report (3–5 pages)

**Success criteria**:
- [ ] Customer pain points identified
- [ ] 3+ competitors analyzed
- [ ] Market size estimated
- [ ] TAM/SAM/SOM calculated

---

### Story Writer Agent
**Role**: Turn research into user stories with psychology anchors

**Skills used**:
- marketing-ideas (primary)
- psychology-patterns (primary)
- customer-journey (secondary)

**Deliverable**: User Story + Acceptance Criteria

**Success criteria**:
- [ ] Story follows "As a [persona], I want [benefit] so that [outcome]"
- [ ] Acceptance criteria are testable
- [ ] Psychology pattern(s) identified
- [ ] Value prop clear

---

### Spec Writer Agent
**Role**: Technical blueprint + business context

**Skills used**:
- marketing-plan (primary)
- competitive-analysis (secondary)
- objection-mapping (secondary)
- sales-enablement (secondary)
- pricing-strategy (secondary)
- launch-strategy (secondary)

**Deliverable**: Technical Brief (2–3 pages)

**Success criteria**:
- [ ] Implementation steps clear
- [ ] Success metrics defined
- [ ] Dependencies listed
- [ ] Risks identified

---

### Backend Builder Agent
**Role**: API routes, data models, integrations, automation

**Skills used**:
- seo-programmatic (conditional)
- seo-authority (conditional)
- analytics-setup (primary)
- conversion-audit (primary)
- revops (primary)
- churn-prevention (conditional)

**Deliverable**: API code + services

**Success criteria**:
- [ ] All endpoints implemented
- [ ] Database models created
- [ ] Conversion tracking wired
- [ ] Typecheck passes
- [ ] Tests written

---

### Frontend Builder Agent
**Role**: Components, pages, UI, forms, landing pages

**Skills used**:
- landing-page-copy (primary)
- form-optimization (primary)
- social-proof-strategy (primary)
- schema-markup (secondary)
- psychology-patterns (secondary)

**Deliverable**: React/Next.js components + pages

**Success criteria**:
- [ ] All pages responsive
- [ ] Forms optimized (< 3 fields)
- [ ] Social proof visible
- [ ] CTA clear + prominent
- [ ] Typecheck passes
- [ ] Tests written

---

### Marketing Builder Agent
**Role**: Copy, ads, email, landing pages, funnels

**Skills used**:
- copywriting (primary)
- ad-creative (primary)
- email-sequences (primary)
- pricing-strategy (conditional)
- lead-magnets (conditional)
- free-tool-strategy (conditional)
- referral-programs (conditional)
- lifecycle-email (conditional)
- cold-email (conditional)
- social-content (conditional)
- video-scripts (conditional)
- prospecting (conditional)
- community-marketing (conditional)

**Deliverable**: Marketing copy, ads, email funnels

**Success criteria**:
- [ ] Copy tested vs. baseline
- [ ] Ads have 3+ variations
- [ ] Email flow has clear CTAs
- [ ] Social proof included

---

### Test Verifier Agent
**Role**: Write acceptance tests, verify criteria met

**Skills used**:
- ab-testing (primary)
- conversion-audit (primary)
- analytics-setup (secondary)
- google-ads (conditional)
- meta-ads (conditional)

**Deliverable**: Acceptance tests (pass/fail)

**Success criteria**:
- [ ] Tests cover all acceptance criteria
- [ ] A/B test design valid
- [ ] Conversion tracking verified
- [ ] Sample size sufficient

---

### Validator Agent
**Role**: Compare implementation vs. brief, audit for gaps

**Skills used**:
- conversion-audit (primary)
- analytics-setup (primary)
- seo-audit-gsp (secondary)
- competitive-analysis (secondary)
- attribution (conditional)

**Deliverable**: Gap Report (severity: critical/major/minor)

**Success criteria**:
- [ ] All brief requirements met
- [ ] No critical gaps
- [ ] Tests passing
- [ ] Typecheck passing
- [ ] Ready for human review

---

## Audit Checklist

### Pre-Launch Audit

**Story Stage**:
- [ ] Research completed (3-day rule)
- [ ] Story approved by human
- [ ] Acceptance criteria testable
- [ ] Psychology pattern identified

**Brief Stage**:
- [ ] Brief written from approved story
- [ ] Implementation steps clear
- [ ] Success metrics defined
- [ ] Brief approved by human

**Build Stage**:
- [ ] Backend: All endpoints, DB, tracking
- [ ] Frontend: All pages, responsive, forms optimized
- [ ] Marketing: Copy, ads, email flows
- [ ] All code typechecked
- [ ] All code tested

**Test Stage**:
- [ ] Acceptance tests written
- [ ] Tests passing
- [ ] A/B test design valid
- [ ] Sample size sufficient

**Validation Stage**:
- [ ] No critical gaps found
- [ ] All acceptance criteria met
- [ ] Validator sign-off
- [ ] Ready for PR review

**Post-Launch Audit**:
- [ ] Conversion tracking active
- [ ] Analytics dashboard created
- [ ] Team trained
- [ ] 30-day metrics review scheduled
- [ ] Iteration plan ready

---

## Quick Reference: Which Skill for What?

### "Our conversion rate is too low"
→ conversion-audit, landing-page-copy, form-optimization, objection-mapping

### "We don't know which ads work"
→ ab-testing, google-ads, meta-ads, attribution, ad-creative

### "Customers are leaving"
→ churn-prevention, lifecycle-email, community-marketing, social-proof-strategy

### "We need more leads"
→ lead-magnets, free-tool-strategy, prospecting, cold-email, referral-programs

### "Competitors are winning"
→ competitive-analysis, competitor-comparison, pricing-strategy, positioning

### "Our content isn't ranking"
→ seo-audit-gsp, seo-programmatic, content-strategy, schema-markup, ai-seo

### "Our emails underperform"
→ email-sequences, copywriting, psychology-patterns, ab-testing

### "We need to launch faster"
→ launch-strategy, marketing-plan, sales-enablement, prospecting

---

## File Structure

```
/Users/enriqueibarra/.claude/skills/marketing/
├─ seo-audit-gsp.md
├─ seo-programmatic.md
├─ seo-authority.md
├─ schema-markup.md
├─ ai-seo.md
├─ content-strategy.md
├─ site-architecture.md
├─ analytics-setup.md
├─ conversion-audit.md
├─ landing-page-copy.md
├─ psychology-patterns.md
├─ objection-mapping.md
├─ form-optimization.md
├─ pricing-psychology.md
├─ social-proof-strategy.md
├─ urgency-scarcity.md
├─ ab-testing.md
├─ email-sequences.md
├─ copywriting.md
├─ cold-email.md
├─ social-content.md
├─ copy-editing.md
├─ video-scripts.md
├─ sales-enablement.md
├─ pricing-strategy.md
├─ competitor-comparison.md
├─ revops.md
├─ prospecting.md
├─ launch-strategy.md
├─ market-research.md
├─ lead-magnets.md
├─ free-tool-strategy.md
├─ referral-programs.md
├─ churn-prevention.md
├─ lifecycle-email.md
├─ community-marketing.md
├─ google-ads.md
├─ meta-ads.md
├─ ad-creative.md
├─ attribution.md
├─ marketing-plan.md
├─ competitive-analysis.md
├─ marketing-ideas.md
└─ customer-journey.md (implied)
```

---

## How to Use This Pipeline

### For a New Campaign:

1. **Activate Researcher** → Market research + competitive analysis
2. **Activate Story Writer** → User story + psychology anchors
3. **Get human approval** on story
4. **Activate Spec Writer** → Brief with metrics + launch plan
5. **Get human approval** on brief
6. **Activate Builders** (Backend + Frontend + Marketing in parallel)
7. **Activate Test Verifier** → Acceptance tests
8. **Activate Validator** → Gap audit
9. **Get human approval** on PR
10. **Launch** ✓

### For a Quick Fix (Typo/Copy Correction):

→ Skip agents, edit directly, no checkpoints needed

### For a Refactor (3+ files, no user-facing change):

→ Run Validator only (gap audit), then commit

---

## Psychology Patterns Used

Every skill is grounded in one or more psychology patterns:

- **Scarcity** → urgency-scarcity, pricing-psychology
- **Social Proof** → social-proof-strategy, community-marketing, email-sequences
- **Authority** → seo-authority, sales-enablement, competitor-comparison
- **Reciprocity** → referral-programs, free-tool-strategy, lead-magnets
- **Belonging** → community-marketing, social-content
- **Loss Aversion** → churn-prevention, objection-mapping
- **Curiosity** → ad-creative, copy-editing, video-scripts
- **Habit Formation** → lifecycle-email, community-marketing
- **Status** → pricing-psychology, social-proof-strategy

---

## Metrics & Success

**Research Stage**:
- Market size identified
- Customer pain points mapped
- Competitive landscape clear

**Story Stage**:
- Acceptance criteria testable
- Psychology pattern applied

**Build Stage**:
- Code typecheck + tests passing
- Conversion tracking active
- 3 A/B test variations ready

**Test Stage**:
- Acceptance tests passing
- Sample size sufficient
- Conversion uplift measurable

**Validation Stage**:
- Zero critical gaps
- All criteria met
- Ready for launch

**Post-Launch (30 days)**:
- Conversion rate change measurable
- User feedback collected
- Iteration plan ready

---

## Notes

- Skills are **activatable during each phase**, not retroactively
- Each skill = 1000–2000 words of tactical content
- All skills cross-linked by dependency
- Dog grooming (WashDog) used as anchoring example throughout
- **No emoji in production** — use real icon libraries only

**Created**: 2026-06-04  
**Total Skills**: 45  
**Last Updated**: Session #[current]
