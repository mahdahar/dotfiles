---
name: git-ship
description: Stage, Conventional Commit, push.
---

# Git Ship
1. Verify git repo + changes.
2. `git add .`
3. Build commit from staged diff:
   - Subject: `<type>(<scope>): <summary>`
   - Body: why, what, impact.
4. `git commit -m "<subject>" -m "<body>"`
5. `git push`
6. On fail: stop, report exact error + next fix.
