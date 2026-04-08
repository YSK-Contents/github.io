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

### Step 1 — Research
Use the `general-purpose` agent (with WebSearch/WebFetch) to research today's news across:
- 英語学習関連（AI tools, language learning trends, studies）
- グローバル・世界情勢（geopolitics, major events）
- ビジネス・経営（startups, management, economic trends）

Gather concrete facts, numbers, and names. Do not fabricate.

### Step 2 — Write
Create `newsletters/YYYY-MM-DD.md` following the style rules below.

### Step 3 — Self-review before committing
- [ ] 事実に誤りはないか（数字・固有名詞を確認）
- [ ] 冗長な箇所はないか
- [ ] 読者の行動につながるか（具体的なアクションがあるか）

### Step 4 — Commit and push
Commit to the active feature branch and push.

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

### Do NOT
- Use `#` headers inside the newsletter body
- Use bullet-point lists as the main content structure
- Write like a news article or press release
- Use multiple `##` sections like a report
- Pad with filler phrases

---

## Git Workflow

- **Branch**: Always work on the designated `claude/...` feature branch
- **Push**: `git push -u origin <branch-name>`
- **Commit message**: Descriptive, one line summary of the newsletter topic
- **Do NOT push to main** without explicit user instruction

## Subagent Usage

- **Research tasks** (web search, multi-URL fetching): use `general-purpose` agent
- **Codebase exploration**: use `Explore` agent
- **Planning complex changes**: use `Plan` agent
- Run independent research queries in parallel when possible

## Context Management

- Run `/compact` when context reaches ~50% to maintain performance
- Keep this CLAUDE.md under 200 lines
