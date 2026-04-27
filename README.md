# Git

Here’s a **clean, practical Git guide** you can drop directly into a README. No fluff, just real workflows developers actually use.

---

```md
# 🚀 Git Quick Guide (Real-World Dev Workflow)

This is a practical Git command guide covering daily development scenarios.

---

## 🧠 Core Mental Model

Working Directory → Staging → Commit → Push

```

edit → git add → git commit → git push

````

---

## 🌱 1. Create & Work on Feature Branch

```bash
git checkout main
git pull
git checkout -b feature/your-feature
````

---

## 🚀 2. Push New Branch to GitHub

```bash
git push -u origin feature/your-feature
```

After first push:

```bash
git push
```

---

## 🔄 3. Keep Branch Updated (Rebase from Main)

```bash
git checkout main
git pull

git checkout feature/your-feature
git rebase main
git push -f
```

---

## ⚠️ 4. Resolve Rebase Conflicts

```bash
# fix conflicts manually
git add .
git rebase --continue
```

Abort if needed:

```bash
git rebase --abort
```

---

## ✏️ 5. Amend Last Commit (same day changes)

```bash
git add -A
git commit --amend --no-edit
git push -f
```

---

## 🔙 6. Undo Last Commit (keep changes)

```bash
git reset --soft HEAD~1
```

---

## ❌ 7. Undo Last Commit (delete changes)

```bash
git reset --hard HEAD~1
```

---

## 🧹 8. Reset Branch to Remote

```bash
git fetch origin
git reset --hard origin/feature/your-branch
```

---

## 🔁 9. Reset to Specific Branch State

```bash
git reset --hard feature/feature_name
```

---

## 🔍 10. Check Status & Changes

```bash
git status
git diff
```

---

## 📦 11. Stage Changes

```bash
git add -A        # everything
git add .         # current folder
git add file.py   # specific file
```

---

## 🔀 12. Merge Branch

```bash
git checkout main
git pull
git merge feature/your-feature
```

---

## 🌿 13. Create Branch from Current Branch

```bash
git checkout -b feature/new-branch
```

---

## 🌍 14. Checkout Remote Branch

```bash
git fetch origin
git checkout -b feature/branch origin/feature/branch
```

---

## 🗑️ 15. Delete Branch

### Local:

```bash
git branch -d feature/branch
```

### Remote:

```bash
git push origin --delete feature/branch
```

---

## 🔄 16. Pull Latest Changes

```bash
git pull
```

---

## 🧠 17. Fetch Without Merging

```bash
git fetch origin
```

---

## 🔍 18. View Branches

```bash
git branch        # local
git branch -r     # remote
git branch -a     # all
```

---

## 📜 19. View Commit History

```bash
git log --oneline --graph
```

---

## 🧪 20. Compare Branches

```bash
git diff branchA branchB
```

---

## 📂 21. Get File from Another Branch

```bash
git checkout branch-name -- path/to/file
```

---

## 🧹 22. Stash Changes (temporary save)

```bash
git stash
git stash pop
```

---

## 🔥 23. Force Push (use carefully)

```bash
git push -f
```

Use only when:

* rebasing
* amending commits
* your branch only

---

## ⚠️ Common Mistakes

* ❌ Working directly on `main`
* ❌ Forgetting `git add` after changes
* ❌ Force pushing shared branches
* ❌ Not pulling before starting work

---

## 💡 Recommended Workflow

```bash
git checkout main
git pull
git checkout -b feature/xyz

# work
git add -A
git commit -m "feat: add xyz"
git push -u origin feature/xyz

# before PR
git checkout main
git pull
git checkout feature/xyz
git rebase main
git push -f
```

---

## 🧾 Commit Prefix Guide

| Prefix   | Use                              |
| -------- | -------------------------------- |
| feat     | new feature                      |
| fix      | bug fix                          |
| refactor | code change (no behavior change) |
| chore    | infra/config                     |
| feat!    | breaking change                  |

---

## 🧠 Golden Rules

* Commit often, push clean
* Keep main branch clean
* Use meaningful branch names
* Rebase instead of merge for features
* Don’t panic → Git rarely loses data

---

## 🚀 One-Line Summary

```text
create → commit → push → rebase → clean history → PR
```


