# CLAUDE.md — AI Park Starter Kit

---

## 1. はじめに

このスターターキットは、Claude Code で使えるAIエージェント＆スキルのパッケージです。
`.claude/` フォルダをあなたのプロジェクトに置くだけで、マーケティング特化のAIアシスタントが使えるようになります。

### セットアップ

1. この `.claude/` フォルダを、あなたの作業フォルダの直下にコピー
2. この `CLAUDE.md` も同じ場所にコピー
3. Claude Code を起動 → 自動的にスキルが読み込まれます

---

## 2. コンテキストコスト設計（最重要）

Claude Codeの性能はコンテキスト管理で決まる。

```
Tier 0: CLAUDE.md + rules/    → 全メッセージに入る。1行でも減らす
Tier 1: Read（knowledge等）   → セッション中残る。必要時だけ読む
Tier 2: commands/              → /skill起動で親に読み込み。重いスキルは注意
Tier 3: agents/                → 独立コンテキスト。親にコスト0。並列可
```

### agents/ vs commands/ の判断基準

| | commands/ | agents/ |
|---|---|---|
| 起動 | ユーザーが `/skill` で手動 | Claude が Agent tool で自動 |
| コンテキスト | 親と共有（Tier 2） | 独立（Tier 3） |
| 適する用途 | オーケストレーター・対話型 | レビュー・評価・並列サブタスク |

**原則: 重い専門タスクはagents/、ユーザー対話が必要なものはcommands/**

---

## 3. ファイル構造

```
.claude/
  commands/   ← /skill で起動するスキル
  agents/     ← Agent tool で自動起動するサブエージェント
  knowledge/  ← スキルが必要時に読むナレッジDB
  rules/      ← 自動適用ルール（anonymize / security / lp-rules）
```

### ナレッジ（knowledge/）の使い方

| ファイル | 用途 | 読むタイミング |
|---|---|---|
| pak-philosophy.md | マーケ哲学（全判断基準） | クリエイティブ制作・評価時 |
| hook-db.md | フックコピーDB | フック設計・評価時 |
| cta-db.md | CTAコピーDB | CTA設計・評価時 |
| park-architecture.md | Park Skills設計原則 | スキル新規作成・改善時 |

---

## 4. 主要スキル一覧

### クリエイティブ制作系
- `/banner-park` — バナー制作（N1×コンセプト→バナー群を生成）
- `/shortad-park` — ショート動画広告の台本＆素材設計
- `/記事LP-park` — 記事LP制作（戦略翻訳型）
- `/concept-park` — コンセプト設計（対話型）
- `/research-park` — 市場調査＆戦略設計

### 記事フィードバック系
- `/article-fb-cmo` — 記事LPの総合診断（8エージェント統合）
- `/article-fb-hook` — フック強度分析
- `/article-fb-narrative` — 感情アーク分析
- `/article-fb-trust` — 信頼構造分析
- `/article-fb-cta` — CTA分析
- `/article-fb-offer` — オファー分析
- `/article-fb-competitive` — 競合比較分析

### ユーティリティ系
- `/lp-speed` — LP表示速度の診断＆修正
- `/anonymize` — 個人情報の匿名化
- `/meeting-prep` — ミーティング準備
- `/proposal-park` — 提案書作成

---

## 5. カスタマイズ方法

### 自分のクライアントを追加する
`.claude/clients/` フォルダを作成し、以下の形式でファイルを追加:

```markdown
# クライアント名

## 基本情報
- 商品: ...
- ターゲット: ...
- 目標: ...

## KPI
- ...
```

### 自分のidentity.mdを作る
`.claude/identity.md` を作成し、AIの人格・口調・行動規範を定義すると、あなた専用のAIアシスタントになります。

### ナレッジを追加する
`.claude/knowledge/` に業界知識や自社データのmdファイルを追加すると、スキルが自動参照します。

---

## 6. 注意事項

- APIキーはコードに直書きしない（環境変数で管理: ~/.zshrc 等）
- クライアントデータをGitにpushする場合は匿名化を徹底
- 薬機法・景表法に関わる表現は必ずチェック

> **迷ったらAIに聞く。でも最終判断は人間がする。**
