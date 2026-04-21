---
name: git-ship
description: Stage with git add ., create a detailed Conventional Commit message from staged changes, then git push. Use when user says git-ship, ship, or git ship.
---

# Git Ship

1. Ensure this is a git repo and there are changes to commit.
2. Run:
```bash
git add .
```
3. Inspect staged diff and write a detailed Conventional Commit message:
   - Subject: `<type>(<scope>): <summary>` (imperative, concise)
   - Body: why, what changed, key files/areas, and notable impact.
4. Commit:
```bash
git commit -m "<subject>" -m "<body>"
```
5. Push:
```bash
git push
```
6. If commit/push fails, stop and report exact error with next fix.
