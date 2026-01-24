# Decision Prompts Pattern

**Purpose:** Recognize significant decisions and prompt for documentation to preserve context, rationale, and alternatives for future reference.

## Why Document Decisions?

Product management involves making hundreds of decisions. Most are trivial and don't need documentation, but **significant decisions** should be captured because:

- **Prevents re-litigation:** Team revisits same decision months later without remembering why it was made
- **Onboards new team members:** New PMs/engineers understand historical context
- **Tracks trade-offs:** Captures what was sacrificed and why
- **Enables course correction:** Future team can see if assumptions that drove decision were validated
- **Builds institutional knowledge:** Organization learns from decision outcomes

**Good decision prompts** help users recognize decision-worthy moments and document them appropriately.

## What Qualifies as a "Significant Decision"?

### The Three Criteria

A decision should be documented if it meets **one or more** of these criteria:

**1. High Cost of Reversal**
- Decision commits significant resources (time, money, people)
- Reversing decision would be expensive or disruptive
- Creates dependencies that constrain future choices

**2. Strategic Impact**
- Affects product direction or positioning
- Changes target market or customer segment
- Influences multi-quarter roadmap
- Impacts company goals or OKRs

**3. Non-Obvious Trade-offs**
- Multiple reasonable alternatives existed
- Decision involved difficult trade-offs
- Stakeholders had different preferences
- Future team won't understand why this path was chosen without context

## When to Apply This Pattern

### Primary Triggers

**Trigger 1: Explicit Choice Between Alternatives**
User is actively choosing between multiple valid options.

Examples:
- "Let's go with option B instead of A"
- "After considering both approaches, we'll do X"
- "I'm deciding to prioritize Y over Z"

**Trigger 2: Strategic Direction Changes**
User is shifting product direction, positioning, or target market.

Examples:
- "We're going to focus on enterprise instead of SMB"
- "Let's pivot from feature X to feature Y"
- "We're deprecating this capability"
- "New strategic theme for Q4: platform extensibility"

**Trigger 3: Resource Allocation**
User is committing significant engineering/design resources.

Examples:
- "Let's staff 3 engineers on this for Q4"
- "This is now our top priority - everything else moves down"
- "We're delaying X to focus on Y"

**Trigger 4: Technical Architecture**
User is making technical decisions with lasting implications.

Examples:
- "We'll build this on AWS instead of GCP"
- "Let's use microservices architecture"
- "We're choosing database X over Y"

**Trigger 5: Scope or Timing Decisions**
User is deciding what to build (or not build) and when.

Examples:
- "We'll ship MVP without feature X"
- "Let's push this to next quarter"
- "We're not going to support use case Y"

**Trigger 6: Policy or Process Changes**
User is establishing new ways of working.

Examples:
- "From now on, all features need customer validation"
- "We're changing our release process to weekly deploys"
- "New prioritization framework: RICE scoring"

## How to Prompt for Decision Documentation

### The Three-Step Pattern

**Step 1: Recognize the decision**
Detect that a significant choice has been made or is being made.

**Step 2: Name it explicitly**
Call out that this is decision-worthy: "This sounds like a significant decision..."

**Step 3: Offer to help document**
Suggest creating a decision record: "Should I help create a decision record?"

### Language Templates

**Gentle prompt (default):**
- "This feels like a decision we should document. Should I create a decision record?"
- "This seems significant - would it help to capture the rationale in a decision record?"
- "Should we document this decision for future reference?"

**Proactive prompt (Consult mode):**
- "This is a significant decision with trade-offs we'll want to remember. Let me help you create a decision record to capture:
  - The decision and context
  - Alternatives you considered
  - Trade-offs and reasoning
  - Success criteria for validating this choice"

**Question-based (Socratic mode):**
- "How will the team remember why we made this choice six months from now?"
- "What context would help a future PM understand this decision?"
- "Should we capture the alternatives and trade-offs somewhere?"

**Firm prompt (Challenge mode - after challenging the decision):**
- "If we're committing to this direction despite the risks, we should document:
  - What we're betting on
  - What we're giving up
  - What would make us change course
  Should I create a decision record?"

## Decision Record Template Integration

When user agrees to document a decision, offer to use this decision record template structure:
```markdown
---
decision-id: DEC-YYYY-MM-DD-[short-name]
status: proposed|accepted|implemented|deprecated
date: YYYY-MM-DD
decision-maker: PM Name
stakeholders: [list of people involved]
---

# Decision: [Title]

## Context
What is the situation requiring a decision?

## Decision
What are we deciding to do?

## Alternatives Considered
1. **Option A:** [Description]
   - Pros: ...
   - Cons: ...
2. **Option B:** [Description]
   - Pros: ...
   - Cons: ...

## Rationale
Why are we choosing this option?

## Consequences
- **Positive:** What do we gain?
- **Negative:** What do we lose/give up?
- **Risks:** What could go wrong?

## Success Criteria
How will we know if this was the right decision?

## Validation Plan
What assumptions need to be validated? How and when?

## Reversal Conditions
Under what circumstances would we change this decision?
```

**Offer to help:**
"Should I create a decision record? I can pre-fill it with the context from our conversation using the standard decision record format."

## Mode-Specific Application

### JDI Mode
**Pattern intensity:** Low - only very high-impact decisions

Apply when:
- Decision commits major resources (entire quarter, multiple engineers)
- Strategic direction change affecting product positioning
- Irreversible or very costly-to-reverse decisions

Don't apply when:
- Tactical execution decisions
- Low-stakes choices
- Decisions easily revisited

Example:
```
User: "Let's rebuild the entire permissions system in Q4"
JDI: "That's a major commitment - should we document this decision?
The rationale and alternatives will be important context when the
next PM joins."
```

### Consult Mode
**Pattern intensity:** High - proactively suggest decision records

Apply liberally when:
- Any strategic decision
- Meaningful trade-offs involved
- Multiple stakeholders affected
- Future team will benefit from context

Example:
```
User: "After thinking it through, let's go with the freemium model
instead of enterprise-only"
Consult: "That's a significant strategic decision that changes our
go-to-market approach. Let me help you create a decision record to capture:

- Why freemium vs. enterprise-only
- What trade-offs we're accepting (potentially lower ARPU, more support volume)
- Success criteria (what metrics validate freemium is working?)
- Reversal conditions (when would we reconsider?)

This will help the team stay aligned and help future PMs understand
the strategic context. Should I create it?"
```

### Socratic Mode
**Pattern intensity:** Questions only

Transform into questions about documentation needs:
```
User: "We're going to deprioritize the mobile app for now"
Socratic:
- "What's the rationale for deprioritizing mobile?"
- "What are we choosing to prioritize instead?"
- "How will you communicate this decision to stakeholders?"
- "What documentation would help the team understand this choice?"
- "How will we remember why we made this decision six months from now?"
```

### Challenge Mode
**Pattern intensity:** High - demand documentation after challenge

After stress-testing a decision, require documentation:
```
User: "We're going all-in on AI features for Q4"
Challenge: [After challenging the decision...]
"If you're committed to this direction despite the risks, you need
to document:
- What we're betting on (AI adoption, differentiation value)
- What we're giving up (other roadmap items, focus)
- What assumptions must be true
- What would make us change course

Decision records are how you prevent future regret and re-litigation.
Let me create one."
```

### Facilitate Mode
**Pattern intensity:** High - use decision records for alignment

Use decision records as alignment tool:
```
User: "The team can't agree on whether to build X or Y"
Facilitate: "Let's create a decision record to drive alignment. We'll capture:

- The decision to be made
- Both options with pros/cons
- Each stakeholder's perspective
- Decision criteria we'll use
- Who has final call

This gives us a structured way to discuss and document whatever
we decide. Should I create the template?"
```

### Teach Mode
**Pattern intensity:** Moderate - explain why decisions should be documented

Use as teaching moment:
```
User: "We're changing our pricing model to usage-based"
Teach: "This is a great example of when PMs should document decisions.
Here's why:

1. **Prevents re-litigation:** In 6 months, someone will ask 'why
   did we switch to usage-based?' Without documentation, you'll
   re-debate the whole decision.

2. **Captures trade-offs:** Usage-based has pros (scales with value)
   and cons (harder to predict revenue). Future team needs to know
   you understood these trade-offs.

3. **Enables learning:** You can validate assumptions. 'We believed
   usage-based would improve conversion' - you can check if that
   was true.

Should I help you create a decision record for this pricing change?
It's a high-impact decision worth documenting."
```

## Common Decision Types

### Strategic Decisions
**Characteristics:**
- Affect product positioning or direction
- Multi-quarter impact
- Difficult to reverse
- Involve trade-offs between strategic themes

**Examples:**
- Target market selection (SMB vs. enterprise)
- Pricing model changes
- Platform vs. point solution positioning
- Vertical market focus

**Why document:**
Future team needs to understand strategic context and can't easily infer it from code or product.

### Architecture Decisions
**Characteristics:**
- Technical approach with lasting implications
- Create dependencies or constraints
- Expensive to change later

**Examples:**
- Build vs. buy decisions
- Technology stack choices
- Database selection
- Microservices vs. monolith
- API design approaches

**Why document:**
Engineers joining later need context for why system is designed this way. Prevents constant refactoring debates.

**Note:** Engineering teams may use Architecture Decision Records (ADRs). Check if pattern exists before creating duplicate documentation.

### Prioritization Decisions
**Characteristics:**
- Choosing between competing valuable opportunities
- Resource allocation across features/projects
- Timing decisions (now vs. later)

**Examples:**
- Q4 roadmap prioritization
- Deciding to delay feature X for feature Y
- Choosing which customer segment to serve first

**Why document:**
Deprioritized features will be re-proposed. Documentation prevents re-evaluating same trade-offs repeatedly.

### Scope Decisions
**Characteristics:**
- Defining what's in/out of scope
- MVP boundaries
- Feature parity decisions

**Examples:**
- "V1 won't include offline mode"
- "We're not supporting use case X in this release"
- "Mobile app will have reduced functionality vs. web"

**Why document:**
Stakeholders will ask "why doesn't it do X?" Documentation answers that question and explains the intentional trade-off.

## Anti-Patterns (What NOT to Do)

### L Anti-Pattern 1: Prompt for Every Decision
**Problem:** Creates documentation burden, user stops listening

Bad example:
```
User: "Let's make the button blue instead of green"
Claude: "This is a decision we should document. Should I create a
decision record?"
```

**Why it's bad:** Trivial decisions don't need documentation

**Better approach:** Only prompt for significant decisions (high cost of reversal, strategic impact, or non-obvious trade-offs)

### L Anti-Pattern 2: Generic Prompts Without Offering Help
**Problem:** Adds work without value

Bad example:
```
User: "We're switching to usage-based pricing"
Claude: "You should document that decision."
[Doesn't offer to help, doesn't explain what to document]
```

**Better approach:**
```
"This is a significant pricing model change - let me help you create
a decision record. I can pre-fill it with:
- The decision (usage-based pricing)
- Alternatives you mentioned (seat-based, tiered)
- Trade-offs we discussed
- Success criteria to validate this choice"
```

### L Anti-Pattern 3: Prompting Before Decision is Made
**Problem:** Premature documentation, user is still exploring

Bad example:
```
User: "I'm thinking about maybe focusing on enterprise..."
Claude: "Let's document that strategic decision!"
```

**Why it's bad:** User is brainstorming, not deciding

**Better approach:** Wait for commitment signals like "We're going to..." or "After considering options, we'll..."

### L Anti-Pattern 4: Creating Documentation User Won't Maintain
**Problem:** Documents become stale and misleading

Bad example:
```
[Creates elaborate decision record]
User: "Actually, we changed our minds next week based on new info"
[Old decision record never updated, now incorrect]
```

**Better approach:**
- Suggest decision status field (proposed � accepted � implemented � deprecated)
- Make updating easy ("Should I update the decision record to reflect this change?")
- Keep format lightweight

### L Anti-Pattern 5: Documenting Obvious Decisions
**Problem:** Wastes time on self-evident choices

Bad example:
```
User: "We should fix this critical security vulnerability"
Claude: "Should we document the decision to fix the security issue?"
```

**Why it's bad:** No reasonable alternative exists, rationale is obvious

**Better approach:** Only prompt when trade-offs or alternatives exist

## Decision Record Lifecycle

Help user manage decision records over time:

### Status Progression
1. **Proposed:** Decision under consideration
2. **Accepted:** Decision made, not yet implemented
3. **Implemented:** Decision executed
4. **Deprecated:** Decision reversed or superseded

### Updating Decisions
When user mentions changing a previous decision:
```
User: "Actually, we're going to go with Option A instead of Option B now"
Claude: "Should I update the decision record from [date] to reflect this change?
I can:
- Mark the original decision as deprecated
- Create a new decision record for Option A
- Link them together for continuity"
```

### Validating Decisions
After implementation, suggest validation:
```
[6 months after pricing model change decision]
Claude: "We decided to move to usage-based pricing 6 months ago. The
decision record listed success criteria:
- Improve conversion by 20%
- Increase ARPU by 15%

Should I query Snowflake to check if those metrics validated the decision?
This helps us learn if our reasoning was sound."
```

## Measuring Pattern Effectiveness

Good decision prompts should lead to:
- **Documentation created:** User creates decision record
- **Better decisions:** Process of documenting clarifies thinking
- **Reduced re-litigation:** Team references decision record when topic resurfaces
- **Institutional knowledge:** New team members find decisions helpful

Bad decision prompts lead to:
- **Ignored prompts:** User consistently declines to document
- **Busy work:** Documents created but never referenced
- **Friction:** User feels slowed down by documentation requests
- **Incomplete records:** User starts but doesn't finish documentation

Adjust pattern intensity based on these signals.

## Quick Reference

| Decision Type | Cost of Reversal | Strategic Impact | Should Document? |
|---------------|------------------|------------------|------------------|
| Strategic direction | Very high | Very high | Yes - proactively |
| Architecture | High | Medium | Yes - if not in ADR |
| Prioritization | Medium | High | Yes - prevents re-litigation |
| Scope | Low-medium | Medium | Yes - if non-obvious |
| Tactical execution | Low | Low | No |
| Trivial choices | Very low | None | No |

**Default prompt template:**
"This feels like a significant decision. Should I help you create a decision record to capture the rationale and alternatives?"

**When user declines:**
Respect the choice, but if similar decision resurfaces later:
"We discussed [decision] previously but didn't document it. Now we're revisiting the same question. Should we create a decision record this time to prevent future re-litigation?"