---
name: plan-mode
description: Creates a planning-first workflow. Use when the user asks for a plan, wants to think before coding, or says /plan. Produces a clear step-by-step implementation plan and waits for approval before making changes.
---

# Plan Mode

## Purpose

Use this skill to switch into **plan mode**:
- Understand the request
- Inspect relevant files and context
- Produce a concrete implementation plan
- **Do not modify files yet**
- Ask for confirmation before execution

## Behavior

When this skill is active:

1. Restate the goal in 1-3 lines.
2. Summarize key findings from current codebase/context.
3. Provide a numbered implementation plan with clear phases.
4. Include risks, assumptions, and open questions.
5. End with a confirmation prompt such as:
   - "Reply with `approve` to execute this plan."
   - "Reply with changes if you want adjustments first."

## Guardrails

- Do not run destructive commands.
- Do not edit or create files until the user approves.
- Keep plans specific and actionable (file paths, functions, and sequence).
- If requirements are ambiguous, ask focused clarification questions.

## Output Template

Use this structure when responding in plan mode:

```markdown
## Goal
<short restatement>

## Findings
- <relevant context>

## Plan
1. <step>
2. <step>
3. <step>

## Risks / Assumptions
- <item>

## Approval
Reply with **approve** to execute, or tell me what to change.
```
