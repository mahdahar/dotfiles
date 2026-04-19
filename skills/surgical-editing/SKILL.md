---
name: surgical-editing
description: Provides guidelines for precise, line-by-line file modifications to avoid full file rewrites.
---

# Surgical Editing Workflow

Use this skill whenever you need to modify an existing file. Follow these rules to ensure minimal impact on the codebase.

## 1. Prioritize String Replacement
- **Action**: Always use the `edit` tool with small, unique `old_string` blocks.
- **Constraint**: Do NOT replace the entire file content unless the file is under 20 lines or requires a total structural overhaul.
- **Precision**: Select a "context window" of 3-5 lines around your change to ensure the `old_string` is unique.

## 2. Validation Steps
- **Read First**: Before calling `edit`, always use `read_file` to capture the exact indentation and whitespace of the target lines.
- **Check Syntax**: If the file is part of a compiled/transpiled language (e.g., TS, Rust), run a check command (like `npm run lint` or `cargo check`) immediately after editing.

## 3. Handling Conflicts
- If the `edit` tool fails due to a non-unique match, expand the `old_string` to include more surrounding context.
- If multiple edits are needed in one file, batch them into a single `edit` call with an array of objects to minimize file system writes.

## 4. Examples
### ❌ Avoid (Full Overwrite)
Instead of rewriting a 200-line file to change one variable, find that specific variable.

### ✅ Preferred (Surgical)
Old String:
```javascript
const apiEndpoint = "https://api.com";
const timeout = 5000;
