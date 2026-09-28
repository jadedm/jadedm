# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

The GitHub profile README for `jadedm` (`github.com/jadedm/jadedm`). `README.md` renders on the
public profile page at github.com/jadedm. There is no application code, build, lint or test suite.
Anything merged to `main` is public immediately.

## Checking a change

There is nothing to run. The check is the content itself:

- Every link must resolve for a logged-out visitor. A link to a private repo 404s on the public
  profile (removed in `c4e15de` for that reason). Check with `curl -sI <url>` or
  `gh repo view <owner>/<repo> --json visibility`.
  npmjs.com answers 403 to curl whatever the page state, so check npm links with `npm view` instead.
- Version numbers and statuses in the NestJS modules table must match what is actually published:
  `npm view @jadedm/<module> version`.
- Preview rendering with `gh markdown-preview` if installed, otherwise read the PR's rendered diff.

## Content rules

The README is personal brand copy under the owner's name.

- Lead is "Founder, Inoltro Digital". The older Fractional CTO, Hyphn, Juvo and Welooped framing was
  dropped deliberately in `1c9b36f`; do not reintroduce it.
- Never use the self-descriptors fractional, consultant, senior or enterprise-scale. Show seniority
  through facts (years, named products, shipped versions).
- No em dashes in prose. No emojis, no hype words.
- Engagement calls to action point at manishj.com; the studio links point at inoltro.ai.
- The repo description (shown on repo lists and search, not in `README.md`) follows the same rules.
  It is not in git, so a README rebrand does not update it. Read it with
  `gh repo view --json description`; changing it (`gh repo edit --description`) is public, so
  confirm the wording with the owner first.

## Workflow

Changes go through a branch and PR, not a direct push to `main`. Branch as `docs/<slug>` or
`chore/<slug>`, conventional commit subject (`docs: ...`), body saying why the change is needed.
PRs here have been merged with merge commits, not squash.
