# CLAUDE.md

This file provides guidance to Claude Code when working in this repository.

## Project Overview

Japanese newsletter published on GitHub Pages.
Audience: Japanese readers interested in English learning and global business.
Author voice: YOSUKE (英語コーチング・ビジネスの実践者)

## Directory Structure

```
newsletters/          # Published newsletter files
  YYYY-MM-DD.md       # One file per issue, named by date
CLAUDE.md             # This file
README.md
```

## Newsletter Creation Workflow

Use `/newsletter` slash command for daily issue creation (`.claude/commands/newsletter.md`).
The command automates research → write → review → commit/push.

Manual steps if needed:
1. Research with `general-purpose` agent (WebSearch/WebFetch) in parallel across 3 topics
2. Write `newsletters/YYYY-MM-DD.md` per style rules below
3. Self-review: facts accurate? concise? reader action included?
4. Commit and push to active feature branch

---

## Newsletter Style Rules

### Opening (fixed format)
```
どうも。YOSUKEです

---------------------------
このメルマガでは

・英語学習のためになる話
・経営、ビジネスの話
・役に立つ考え方など

をちょっと深く書いてます
---------------------------
```

### Body
- **One theme, explored deeply** — not a roundup of multiple news items
- Short sentences. Frequent line breaks. No dense paragraphs.
- Conversational tone: `〜んです`, `〜ですね`, `〜だと思っています`
- Write from YOSUKE's perspective as a practitioner (英語コーチング経験、ビジネス実践)
- Include concrete examples, anecdotes, or English phrases where relevant
- When using English phrases, show Japanese context → English translation pattern
- Pose questions to the reader to build engagement

### Closing (fixed)
```
ご参考までに！
```

<important if="writing a newsletter">
Do NOT:
- Use `#` headers inside the newsletter body
- Use bullet-point lists as the main content structure
- Write like a news article or press release (no "今日のハイライト", no "01｜" section headers)
- Cover multiple news topics as a roundup — pick ONE theme and go deep
- Pad with filler phrases
</important>

---

## Git Workflow

- **Branch**: Always work on the designated `claude/...` feature branch
- **Push**: `git push -u origin <branch-name>`
- **Commit message**: Descriptive, one line summary of the newsletter topic
- **Do NOT push to main** without explicit user instruction
- **One file per commit**: Do not bundle multiple file changes into a single commit

## Subagent Usage

- **Research tasks** (web search, multi-URL fetching): use `general-purpose` agent
- **Codebase exploration**: use `Explore` agent
- **Planning complex changes**: use `Plan` agent
- Run independent research queries in parallel when possible
- Use Opus for planning/review, Sonnet for writing/execution

## Context Management

- Run `/compact` when context reaches ~50% to maintain performance
- Keep this CLAUDE.md under 200 lines
- Use `/rewind` (Esc Esc) to undo if Claude goes off-track
