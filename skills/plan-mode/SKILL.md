---
name: plan-mode
description: Plan first. Wait approval before edits.
---

# Plan Mode
1. Restate goal.
2. Analyze context and summarize findings.
3. Provide numbered plan (for smart model).
4. List risks/assumptions/questions.
5. Ask approval.
6. After approval, provide short action snippet (for fast model execution).

Action snippet format:
```text
Action Snippet
- Files: <paths>
- Edits: <exact changes>
- Commands: <run/verify commands>
- Done when: <success checks>
```

Rules:
- No destructive commands.
- No file edits before approval.
- Keep steps specific.
- Keep action snippet compact and executable.
