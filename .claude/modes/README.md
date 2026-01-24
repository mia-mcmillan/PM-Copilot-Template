# Coaching Modes

PM Copilot operates in different modes depending on the type of work. Each mode has distinct behavior and is loaded on-demand to keep context usage efficient.

## Available Modes

### 1. JDI Mode (Default)
**File:** `jdi.md`

**When to use:**
- Well-defined tasks
- Template-based work
- Data analysis
- Implementation tasks
- User wants to "just get it done"

**Behavior:** Just do it. Efficient, action-oriented, minimal questioning

**Activate:** (default) or `/mode jdi`

---

### 2. Consult Mode
**File:** `consult.md`

**When to use:**
- Strategy formation
- Big decisions
- Opportunity assessment
- Prioritization
- Resource allocation
- User wants thinking challenged

**Behavior:** Strategic consulting: proactive questioning, assumption surfacing, evidence-seeking

**Activate:** `/mode consult`

---

### 3. Socratic Mode
**File:** `socratic.md`

**When to use:**
- User is stuck or uncertain
- Building PM intuition
- Learning by discovery

**Behavior:** Only asks questions, doesn't provide answers

**Activate:** `/mode socratic`

---

### 4. Challenge Mode
**File:** `challenge.md`

**When to use:**
- High-stakes decisions
- Stress-testing ideas
- Before committing resources

**Behavior:** Argues opposite side, finds flaws, challenges vigorously

**Activate:** `/mode challenge`

---

### 5. Facilitate Mode
**File:** `facilitate.md`

**When to use:**
- Workshops
- Team decisions
- Stakeholder alignment

**Behavior:** Structures discussions, captures outputs, synthesizes

**Activate:** `/mode facilitate`

---

### 6. Teach Mode
**File:** `teach.md`

**When to use:**
- Teaching frameworks
- Skill development
- Understanding concepts

**Behavior:** Explains reasoning, provides examples, suggests practice

**Activate:** `/mode teach`

---

## How Modes Work

### Modular Loading
- Each mode is a separate file loaded on-demand
- Keeps CLAUDE.md slim and focused
- Reduces context usage
- Makes modes easy to iterate and improve

### Mode Switching
**User can switch explicitly:**
```
/mode consult
/mode jdi
/mode socratic
/mode challenge
```

**Claude may suggest switching:**
"This feels like a strategic decision. Should I switch to Consult Mode?"

### Default Behavior
- **Default:** JDI Mode
- **Auto-switch:** Claude may suggest mode switches based on context
- **User control:** User can override and choose any mode

## Adding New Modes

To add a new mode:

1. **Create mode file:** `.claude/modes/new-mode.md`
2. **Define:**
   - Purpose
   - Core behaviors
   - When to use
   - Example interactions
   - Success indicators
3. **Update CLAUDE.md:** Add mode to mode-switching logic
4. **Update this README:** Document the new mode
5. **Test:** Ensure mode loads and behaves correctly

## Best Practices

### For Mode Designers
- Keep modes focused on specific contexts
- Provide concrete examples
- Define clear activation criteria
- Include success indicators
- Specify when to switch out

### For Users
- Use Consult for big decisions
- Use JDI for defined tasks
- Switch modes explicitly when needed
- Experiment with different modes
- Provide feedback on mode effectiveness

## Mode Interaction Matrix

| Current Mode | Good Transition To | When |
|--------------|-------------------|------|
| JDI | Consult | Hit a big decision |
| JDI | Teach | Need framework explanation |
| Consult | Socratic | User should figure it out |
| Consult | Challenge | Need stress-testing |
| Consult | JDI | Direction is clear |
| Challenge | Consult | Done challenging, need constructive path |
| Teach | JDI | Ready to apply the framework |

## Troubleshooting

**Problem:** Mode doesn't seem to activate
- Check spelling: `/mode consult` not `/mode consulting`
- Try explicit request: "Switch to consult mode"
- Verify mode file exists and is properly formatted

**Problem:** Claude keeps questioning in JDI Mode
- Explicitly state: `/mode jdi` or "just do it"
- Check if task actually needs Consult Mode
- May indicate task has hidden strategic elements

**Problem:** Not enough challenge in Consult Mode
- Request more: "Challenge this harder" or "What am I missing?"
- Try Challenge Mode for maximum pushback
- Provide feedback: "I need you to be more skeptical"

## Performance Monitoring

Track these for each mode:
- Does mode activate correctly?
- Does behavior match mode definition?
- Does user find mode helpful?
- Any hallucinations or missed instructions?
- Context usage stays healthy?

See: `6-execute/reviews/V1-Performance-Tracking.md` *(after directory migration)*

## Version History

- **V1.0 (Week 1):** Execution, Strategic Partner
- **V1.0 (Week 2):** +Socratic, Devil's Advocate, Facilitator, Learning
- **V1.0 (Week 2.5):** Mode rename - action-oriented verbs (JDI, Consult, Challenge, Teach, Facilitate)
- **Future:** Additional modes based on user needs
