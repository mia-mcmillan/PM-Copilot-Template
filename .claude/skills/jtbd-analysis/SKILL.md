---
name: jtbd-analysis
description: Conduct Jobs-to-be-Done (JTBD) analysis to understand deeper customer needs and motivations beyond feature requests
---

You are conducting a Jobs-to-be-Done (JTBD) analysis to understand deeper customer needs and motivations.

## Your Task

Apply the JTBD framework to uncover customer needs beyond surface-level feature requests:

1. **Gather Customer Context**:
   - Customer interviews and feedback
   - Gong call transcripts
   - Support tickets and usage data
   - Competitive research (why customers switch)
   - Existing customer insights documents

2. **JTBD Framework Structure**:

   **I. Job Executor Profile**:
   - Role and responsibilities
   - Technical/organizational environment
   - Success criteria (what they're measured on)

   **II. Job Statements**:
   - **Core Functional Job**: [Verb] + [Object] + [Context]
   - **Job Statement Format**: "When [situation], I want to [action], so I can [outcome]"
   - **Related Jobs**: Supporting jobs that enable the core job

   **III. Job Map** (Universal 8-Phase Process):
   - **Define**: Planning, goal-setting, understanding requirements
   - **Locate**: Finding inputs, data, information needed
   - **Prepare**: Setup, transformation, arranging resources
   - **Confirm**: Validation, verification, risk reduction
   - **Execute**: Core task or primary action
   - **Monitor**: Tracking progress, ensuring accuracy
   - **Modify**: Handling exceptions, adjusting approach
   - **Conclude**: Finalizing, handing off, verifying completion

   **IV. Desired Outcomes**:
   - Measurable success metrics using format:
     - "Minimize [the time/effort/uncertainty to...]"
     - "Increase [the likelihood/confidence that...]"
     - "Reduce [the risk/complexity of...]"
     - "Ensure [quality/accuracy requirement]"

3. **Analysis Process**:
   - Identify the core functional job (not just features they want)
   - Map the job executor's process through relevant phases
   - Extract specific challenges at each phase
   - Capture customer quotes as evidence (interspersed in job map)
   - Define desired outcomes as measurable metrics
   - Note implications for product direction (but no detailed opportunity analysis)

4. **Create JTBD Analysis Document**:
   - **Location**: `2-analyze/insights/`
   - **Naming Convention**: `JTBD - [Persona] - [Key Job].md`
     - Example: `JTBD - VP Revenue Ops - Proactive Intelligence.md`
     - Example: `JTBD - FP&A Manager - Budget Management & Variance Analysis.md`
   - **Template**: Use bundled `template.md` in this skill folder as structure

   **Key Guidance for Each Phase**:
   - Focus on the customer's actual process, not what you think it should be
   - Not all jobs have all 8 phases - only include relevant ones
   - Intersperse evidence (quotes) within each phase using structured blocks:
     - **Challenges**: Specific pain points at this phase
     - **Evidence**: Customer quotes illustrating challenges
     - **Desired Outcomes**: Measurable success metrics in Minimize/Increase/Reduce format
   - Keep Job Executor Profile brief (3-4 sentences total)
   - Core job statement should be clear and outcome-focused
   - Implications section should be 2-3 sentences, not full strategic analysis
   - **Do NOT include opportunity analysis** - that belongs in Phase 3 (Strategize), not JTBD

5. **Analysis Best Practices**:
   - Listen for the job behind feature requests (they ask for reports, but the job is "detect anomalies proactively")
   - Extract desired outcomes as metrics, not vague wants ("minimize time to find correct data table" not "find data faster")
   - Capture verbatim quotes - these are gold for understanding context
   - Only include job map phases that matter for this specific job
   - Be specific about challenges ("ambiguous requirements from stakeholders who don't know what they need") not generic ("requirements are unclear")

6. **Apply Comprehensive Tagging**:
   - **#jtbd/** - Job category (e.g., #jtbd/proactive-intelligence, #jtbd/budget-management)
   - **#persona/** - Persona role (e.g., #persona/vp-revops, #persona/fpa-manager)
   - **#theme/** - Product themes (e.g., #theme/conversational-ai, #theme/natural-language-queries)
   - **#strategic-theme/** - Strategic themes (e.g., #strategic-theme/proactive-intelligence)

7. **Link Related Analysis**:
   - Link to source transcripts using Obsidian `[[links]]`
   - Connect to related JTBD analyses (personas with similar jobs)
   - Link to pattern analysis documents
   - **Note**: Link to opportunities in `3-strategize/opportunities/` but don't create them in this document

## Output

Present:
- Core functional job statement
- Brief summary of job executor context
- Key challenges across relevant job map phases
- Top 3-5 desired outcomes (measurable metrics)
- File path to JTBD analysis document
- Brief note on implications (2-3 sentences)
