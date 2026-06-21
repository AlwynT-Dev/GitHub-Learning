# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

This is **not a software project** — it is a hands-on learning lab where the owner (Alwyn,
new to the industry) is learning Git and GitHub from scratch, guided step by step. There is
no application code, build system, test suite, or linter, and none should be invented.

The "work" here is practicing Git/GitHub itself: making commits, branching, pushing to a
remote, and opening pull requests. Treat the act of using Git in this repo as the subject
matter, not incidental tooling.

## Commands

There is no build/test/lint toolchain. The relevant commands are the Git commands being
practiced, e.g.:

- `git status` — inspect the current state (used constantly)
- `git add <file>` / `git commit -m "message"` — stage and save a snapshot
- `git log --oneline` — review history
- `git switch -c <branch>` / `git merge <branch>` — branch and integrate
- `git push` / `git pull` / `git clone` — sync with GitHub (once a remote is configured)

A remote (`origin`) is not yet configured; pushing to GitHub is a later module.

## How to work in this repo

- **Teaching mode.** The user is a beginner who learns hands-on. Explain one small concept,
  perform one action, verify it worked, then continue. Avoid jargon dumps; use plain-language
  analogies. Quiz the user occasionally to confirm understanding before advancing.
- **Go slowly and one module at a time.** A module-by-module curriculum is tracked in the
  session task list (configure identity → first commits → undo/.gitignore → GitHub account →
  push → branches → pull requests → cheat-sheet). Do not race ahead through multiple modules
  at once.
- **Narrate Git's output.** After running a Git command, walk through what the output means
  rather than assuming the user can read it.

## Files

- `README.md` — the project's front page; doubles as the user's running log of what they have
  learned. Keep it updated as a teaching artifact as new concepts are covered.
- `git-cheatsheet.md` — (planned) a reusable summary of the standard Git/GitHub workflow for
  the user to reference in all future projects.
