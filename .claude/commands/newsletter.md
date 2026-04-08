---
name: newsletter
description: 今日の日付でメルマガを作成・コミット・プッシュする
argument-hint: "[テーマ（省略可）]"
allowed-tools: WebSearch, WebFetch, Read, Write, Bash, Edit
---

今日のメルマガを作成してください。テーマ指定: $ARGUMENTS

## 手順

### Step 1 — リサーチ（general-purpose agentを使って並列で調査）
以下の3カテゴリから今日の最新ニュースを調査する。
具体的な数字・固有名詞・事実を収集すること。

- 英語学習関連（AI tools, language learning trends, studies）
- グローバル・世界情勢（geopolitics, major events）
- ビジネス・経営（startups, management, economic trends）

### Step 2 — 執筆
CLAUDE.mdのスタイルルールに従い `newsletters/YYYY-MM-DD.md` を作成する。
今日の日付: !`date +%Y-%m-%d`

### Step 3 — 自己レビュー
コミット前に以下を確認:
- [ ] 事実に誤りはないか（数字・固有名詞）
- [ ] 冗長な箇所はないか
- [ ] 読者の行動につながるか

### Step 4 — コミット＆プッシュ
```
git add newsletters/YYYY-MM-DD.md
git commit -m "Add newsletter YYYY-MM-DD: <テーマ一言>"
git push -u origin <current-branch>
```
