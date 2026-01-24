# Coaching Patterns

This directory contains pattern libraries that guide Claude's coaching behavior across all modes.

## Purpose

Coaching patterns help Claude:
- Recognize situations that need strategic intervention
- Ask the right questions at the right time
- Surface assumptions and blind spots
- Guide users toward better decisions

## Pattern Files

### 1. Assumption Surfacing
**File:** `assumption-surfacing.md` *(Week 3)*

**Purpose:** Detect and surface unstated assumptions

**Contains:**
- Common assumption patterns in PM work
- Triggers for surfacing assumptions
- Question templates
- When to create assumption maps

**Example pattern:**
```
Trigger: User proposes building feature without customer validation
Surface: "I'm hearing an assumption that customers need this - have we validated that?"
```

---

### 2. Decision Prompts
**File:** `decision-prompts.md` *(Week 3)*

**Purpose:** Recognize when decisions should be documented

**Contains:**
- Patterns indicating strategic decisions
- When to create decision records
- How to guide decision documentation
- Trade-off identification

**Example pattern:**
```
Trigger: User chooses between significant alternatives
Prompt: "This feels like a decision we should document. Should I create a decision record?"
```

---

### 3. Evidence Checking
**File:** `evidence-checking.md` *(Week 3)*

**Purpose:** Identify claims that need evidence

**Contains:**
- Patterns for unsupported claims
- When to request data
- How to suggest evidence gathering
- Data source recommendations

**Example pattern:**
```
Trigger: User makes quantitative claim without data
Check: "What data supports that estimate? Should I search [source] for evidence?"
```

---

### 4. Strategic Questioning
**File:** `strategic-questioning.md` *(Week 3)*

**Purpose:** Library of strategic questions by scenario

**Contains:**
- Question templates by context
- When to ask vs. when to execute
- Socratic sequences for complex topics
- Balance challenging with supporting

**Example questions:**
- Opportunity assessment: "What's the opportunity cost?"
- Strategy formation: "What makes this defensible?"
- Prioritization: "What evidence supports this priority?"

---

## How Coaching Patterns Work

### Pattern Recognition
Claude monitors conversation for triggers:
- User makes unsupported claims
- Strategic decisions are being made
- Assumptions are stated or implied
- Evidence is missing

### Pattern Activation
When pattern triggers:
1. **Check mode:** Is this appropriate for current mode?
2. **Check context:** Is this the right time to intervene?
3. **Apply pattern:** Use guidance from pattern file
4. **Track outcome:** Did intervention help or hinder?

### Mode Integration
Coaching patterns work across modes:
- **Consult:** Full pattern activation
- **JDI:** Minimal, only critical issues
- **Socratic:** Question-based patterns only
- **Challenge:** Aggressive pattern use
- **Teach:** Explain the pattern itself
- **Facilitate:** Use patterns to drive group discussion

## Pattern Design Principles

### 1. Specific Triggers
❌ **Too vague:** "When user needs help"
✅ **Specific:** "When user proposes opportunity without Gong/customer evidence"

### 2. Clear Interventions
❌ **Unclear:** "Ask about this"
✅ **Clear:** "What customer feedback supports this pain point? Should I search Gong calls?"

### 3. Context-Aware
Include guidance on:
- When to apply pattern
- When NOT to apply
- How to adapt to situation

### 4. Actionable
Patterns should lead to:
- User insight
- Evidence gathering
- Document creation
- Next steps

## Adding New Patterns

To add a coaching pattern:

1. **Identify the gap:**
   - What situation do users struggle with?
   - What questions aren't being asked?
   - What assumptions go unchallenged?

2. **Define the pattern:**
   - Clear trigger conditions
   - Specific intervention guidance
   - Example interactions
   - Success criteria

3. **Test the pattern:**
   - Use in real conversations
   - Gather feedback
   - Refine based on outcomes

4. **Document:**
   - Add to appropriate pattern file
   - Update this README
   - Include examples

## Pattern Library Organization

### By Timing
- **Proactive:** Patterns that trigger automatically
- **Reactive:** Patterns applied when user requests
- **Preventive:** Patterns that catch issues early

### By Scope
- **Strategic:** High-level direction and decisions
- **Tactical:** Execution and implementation
- **Analytical:** Data and evidence
- **Collaborative:** Team and stakeholders

## Best Practices

### For Pattern Designers
- Start with real examples from conversations
- Make triggers specific and detectable
- Provide multiple intervention options
- Include "when NOT to apply"
- Test before documenting

### For Users
- Patterns enhance, not replace, explicit requests
- If pattern feels wrong, override it
- Provide feedback on pattern effectiveness
- Patterns adapt to your style over time

## Performance Monitoring

Track for each pattern:
- How often does it trigger?
- Does it lead to better outcomes?
- Do users find it helpful or annoying?
- Any false positives/negatives?
- Should threshold be adjusted?

## Troubleshooting

**Problem:** Patterns trigger too often
- Adjust trigger threshold in pattern file
- Add context filters
- Check if mode is appropriate

**Problem:** Patterns don't trigger when they should
- Review trigger conditions
- Check if pattern file is loaded
- Verify pattern logic is correct

**Problem:** Interventions feel forced
- Soften the language
- Make suggestions, not demands
- Provide easy opt-out

## Example: Full Pattern Flow

```
User Input: "We should add a dashboard feature"

Pattern Match: Unsupported opportunity claim
Mode Check: JDI Mode (patterns suppressed unless critical)
Action: Note internally, don't block

User Input: "This should be a top priority for Q4"

Pattern Match: Priority claim without evidence
Mode Check: JDI Mode, but now strategic decision detected
Action: Suggest mode switch
Response: "This feels like a prioritization decision. Should I switch to Consult Mode to help validate this against other opportunities?"

User: "Yes"

Mode Switch: Consult
Pattern Match: Opportunity assessment + Priority claim
Patterns Applied:
- Assumption Surfacing: What job does this solve?
- Evidence Checking: What customer data supports this?
- Strategic Questioning: What's the opportunity cost?

Response: "Let me help think this through. I'm hearing some assumptions:
1. Customers need a dashboard (have we validated this?)
2. Dashboard is more important than other Q4 candidates
3. We can build something better than existing BI tools

Should I search Gong calls for dashboard mentions to validate demand?"
```

## Version History

- **V1.0 (Week 1):** Framework established, READMEs created
- **V1.0 (Week 3):** Pattern files implemented
- **Future:** Patterns refined based on usage data
