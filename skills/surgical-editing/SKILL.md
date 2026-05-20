---
name: surgical-editing
description: Minimal, precise edits.
---

# Surgical Editing
- Prefer `edit` with small unique `oldText`.
- Avoid full rewrites unless required.
- Read target lines first (exact whitespace).
- Batch multiple edits per file in one `edit` call.
- If match not unique, expand context.
- Run relevant checks after edits.
- Change only needed lines.
