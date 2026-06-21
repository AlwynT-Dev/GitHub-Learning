# Git & GitHub Cheat-Sheet

My personal reference for the standard workflow, by task. Built from my hands-on learning.

> Mental model: **Working files → (git add) → Staging → (git commit) → History → (git push) → GitHub**

---

## 0. One-time setup (per computer)
```bash
git config --global user.name "Alwyn"
git config --global user.email "alwyn.b.tan@gmail.com"
git config --global init.defaultBranch main
git config --global --list          # check settings
```

## 1. Start a NEW project
**Option A — brand new, local first:**
```bash
git init                            # turn this folder into a repo
# ...create files...
git add .                           # stage everything
git commit -m "Initial commit"
# then make an EMPTY repo on github.com (no README/gitignore), then:
git remote add origin <url>
git push -u origin main
```
**Option B — project already on GitHub:**
```bash
git clone <url>                     # downloads everything + sets up origin
```

## 2. The everyday loop (do this constantly)
```bash
git status                          # what's going on right now?
git diff                            # what did I change (before staging)?
git add <file>                      # stage specific file  (or: git add .  for all)
git diff --staged                   # review what I'm about to commit
git commit -m "Clear message"       # save a snapshot
git push                            # upload to GitHub
```

## 3. Branching (work without breaking main)
```bash
git branch                          # list branches (* = current)
git switch -c <branch-name>         # create AND switch to a new branch
git switch main                     # switch back to main
# ...edit, add, commit on the branch...
git switch main
git merge <branch-name>             # fold branch into main (be ON the destination)
git branch -d <branch-name>         # delete merged branch (must NOT be on it)
```

## 4. Pull Request workflow (team / professional)
```bash
git switch -c <branch-name>         # 1. new branch
# ...edit, add, commit...
git push -u origin <branch-name>    # 2. push the branch to GitHub
# 3. Open the PR on github.com (use the link Git prints, or the green button)
# 4. Review the diff, then "Merge pull request" + delete branch on GitHub
git switch main
git pull                            # 5. bring the merge down to local main
git branch -d <branch-name>         # 6. delete local branch
```

## 5. Undo / fix things (don't panic)
```bash
git restore <file>                  # discard uncommitted edits to a file
git restore --staged <file>         # unstage (keep edits, take out of the box)
git commit --amend -m "new msg"     # fix the LAST commit's message (if not pushed)
git switch -                        # jump back to the previous branch
```

## 6. Inspect / look around
```bash
git log --oneline                   # compact history
git log                             # full history (author, date, message)
git diff <commitA> <commitB>        # compare two commits
git branch -a                       # list local AND remote branches
git remote -v                       # show configured remotes (origin url)
```

## 7. Golden rules
- Commit **often** with **clear messages** — committed work is safe; uncommitted can be lost.
- `git status` is your friend — run it whenever unsure. Read its hints.
- Never commit secrets (passwords, API keys) — use `.gitignore` (e.g. `.env`).
- `main` should always work — experiment on branches, merge when ready.
- Pull before you start working if others might have pushed.
