---
name: analyze-pattern
description: Cross-source pattern recognition to identify recurring themes across JTBD interviews, customer feedback, market research, and product intelligence sources
---

You are conducting cross-source pattern recognition to identify recurring themes across JTBD interviews, customer feedback, market research, and other product intelligence sources.

## Your Task

Identify and document patterns by synthesizing evidence from multiple sources:

1. **Scan Analysis Sources**:
   - **Primary Source**: `2-analyze/insights/` - JTBD analyses, customer feedback syntheses
   - **Supporting Sources**:
     - `1-collect/customer-interviews/` - Interview transcripts
     - `1-collect/exports/` - Gong calls, Snowflake data
     - Market research, competitive intelligence
     - Usage data and product analytics

2. **Identify Recurring Patterns**: Look for:
   - **Pain Points**: Repeated frustrations across multiple personas
   - **Behavioral Patterns**: Common workflows, workarounds, or habits
   - **Organizational Patterns**: Structural issues affecting multiple roles
   - **Market Patterns**: Trends, competitive dynamics, ecosystem shifts
   - **Opportunity Patterns**: Recurring needs or jobs-to-be-done

3. **Pattern Validation**: Strong patterns typically have:
   - **3+ independent sources** of evidence
   - **Direct quotes** from customers/stakeholders
   - **Quantifiable impact** (time, cost, risk)
   - **Clear root causes** (not just symptoms)
   - **Strategic significance** (affects product direction)

4. **Check for Existing Patterns First**: Before creating a new pattern, scan `2-analyze/patterns/` to see if this pattern already exists.

   **Update Existing Pattern When**:
   - New source shows the **same pattern** you already documented
   - Same root causes, just more evidence
   - Strengthens confidence in existing pattern
   - Validates pattern across more customer segments

   **What to Update**:
   - Add new persona/source to "Evidence Across Sources" section
   - Update frequency metadata: `Observed in 4/4 → 7/7 interviews`
   - Strengthen Strategic Implications if new insights emerge
   - Add version history entry at bottom

   **Example Update**:
   ```markdown
   ## Evidence Across Sources

   [Existing 4 personas...]

   ---

   ### FP&A Manager (Akanksha) [NEW]
   **Quote**: "[New supporting quote]"
   **Context**: [Context]
   **Impact**: [Impact]
   **Frequency**: [Frequency]

   ---

   ## Version History

   - **v1.0**: Initial pattern from 4 JTBD interviews (2025-11-06)
   - **v1.1**: Added evidence from 3 new business user interviews (2025-11-13)
   ```

   **Create New Pattern When**:
   - You discover a **different** recurring theme
   - Distinct root causes from existing patterns
   - Represents a separate strategic opportunity
   - Would be confusing to merge with existing patterns
   - New pattern complements but doesn't duplicate existing ones

5. **Create or Update Pattern Document**:
   - **Location**: `2-analyze/patterns/`
   - **Naming**: `[Pattern Name] - Pattern.md`
   - **Template**: Use bundled `template.md` in this skill folder as structure
   - **Format**: Hybrid YAML frontmatter (for Obsidian features) + inline metadata (for readability)

   **Document Structure**:
   ```markdown
   ---
   # YAML Frontmatter (for Obsidian Properties, Dataview, filtering)
   pattern-id: PAT-XXX
   severity: Critical  # Critical/High/Medium/Low
   frequency-observed: X
   frequency-total: Y
   frequency-percentage: 0  # Calculate as (observed/total)*100
   category: Organizational  # Organizational/Process/Technical/Market/Competitive/Behavioral
   date: YYYY-MM-DD
   personas: []  # List of persona names/roles from evidence
   tags:
     - pattern/[pattern-type]
     - pattern/[category]
     - pain/[pain-point]
     - theme/[theme]
     - strategic-theme/[strategic-theme]
   ---

   # [Pattern Name] - Pattern

   **Pattern ID**: PAT-XXX
   **Severity**: Critical/High/Medium/Low
   **Frequency**: Observed in X/Y sources (%)
   **Category**: [Type]

   ## Pattern Summary
   [1-2 paragraph description]

   ## Evidence Across Sources
   ### [Persona/Source 1]
   **Quote**: "[Direct quote]"
   **Context**: [Situation]
   **Impact**: [Effect]
   **Frequency**: [How often]

   [Repeat for all sources - typically 3-7]

   ## Pattern Characteristics
   ### Root Causes
   ### Consequences

   ## Current Workarounds

   ## Related Patterns

   ## Strategic Implications
   ### Opportunity Sizing
   ### Solution Requirements
   ### Competitive Positioning

   ## Product Strategy Recommendations
   ### Immediate Actions
   ### Long-Term Strategy
   ### Discovery Needed

   ## Metrics to Track

   ## Tags
   #pattern/[type] #pain/[pain-point] #theme/[theme]

   ## Links
   **Supporting Evidence**: [[JTBD analyses]]
   **Related Patterns**: [[Other patterns]]
   **Strategic Documents**: [[Strategy docs]]
   ```

6. **Pattern Naming Conventions**:
   - Use descriptive, searchable names
   - Examples from existing patterns:
     - "Data Access Bottleneck - Pattern"
     - "Trust & Verification Anxiety - Pattern"
     - "Insight vs Dashboard Gap - Pattern"
     - "Manual Data Aggregation - Pattern"
     - "Cross-System Context Challenge - Pattern"

7. **Apply Comprehensive Tagging**:
   - **#pattern/** - Pattern type (e.g., #pattern/bottleneck, #pattern/organizational, #pattern/behavioral)
   - **#pain/** - Pain categories (e.g., #pain/data-access, #pain/dependency, #pain/manual-work)
   - **#theme/** - Product themes (e.g., #theme/self-service, #theme/trust, #theme/automation)
   - **#strategic-theme/** - Strategic themes (e.g., #strategic-theme/analyst-empowerment)

8. **Link to Supporting Evidence**:
   - Link to JTBD analyses using Obsidian `[[links]]`
   - Connect to related patterns (cross-reference)
   - Link to strategic documents or roadmap items
   - Reference specific opportunities that address this pattern

## Pattern Severity Guidelines

**Critical**:
- Affects multiple customer segments
- High frequency across sources (75%+)
- Significant business impact (revenue risk, churn risk)
- Competitive differentiation opportunity
- Blocks strategic objectives

**High**:
- Affects key customer segments
- Observed in 50-75% of sources
- Notable business impact
- Influences product direction
- Solvable with reasonable investment

**Medium**:
- Affects specific segments
- Observed in 25-50% of sources
- Measurable but not critical impact
- Worth tracking and validating
- Future opportunity

**Low**:
- Emerging signal
- Observed in <25% of sources
- Minor impact
- Watch for trend development

## Output

Present your findings with:
- **Pattern name** and severity
- **Evidence summary**: Which sources show this pattern
- **Key quotes**: 2-3 most compelling quotes
- **Strategic implication**: Why this matters for product strategy
- **File path**: Location of created pattern document
- **Recommended actions**: Immediate next steps

## Important Notes

- **Evidence-driven**: Every pattern must have concrete quotes and examples
- **Multi-source validation**: Don't create patterns from single sources
- **Strategic focus**: Prioritize patterns with product/business impact
- **Actionable**: Each pattern should lead to clear product recommendations
- **Cross-reference**: Link patterns to JTBD analyses and opportunities
- **Use Obsidian links**: All references use `[[wiki-style links]]`
- **Metadata consistency**: Ensure YAML frontmatter and inline metadata match (e.g., `pattern-id: PAT-001` in YAML = `**Pattern ID**: PAT-001` inline). YAML enables Obsidian features (Properties panel, Dataview queries, filtering); inline metadata provides human readability.