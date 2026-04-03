# AI Park スターターキット

Claude Code で使えるマーケティング特化AIエージェント＆スキルのパッケージです。

## セットアップ（3ステップ）

### Step 1: Claude Code をインストール
```
npm install -g @anthropic-ai/claude-code
```

### Step 2: このフォルダの中身をコピー
あなたの作業フォルダに、以下の2つをコピーしてください：
- `.claude/` フォルダ（まるごと）
- `CLAUDE.md` ファイル

```
あなたの作業フォルダ/
  ├── .claude/          ← これをコピー
  ├── CLAUDE.md         ← これをコピー
  └── （あなたのファイル）
```

### Step 3: Claude Code を起動
作業フォルダで以下を実行：
```
claude
```

自動的にスキルが読み込まれます。

## 使い方

起動したら、以下のようにスキルを呼び出せます：

| やりたいこと | コマンド |
|---|---|
| バナーを作りたい | `/banner-park` |
| 記事LPのフィードバックがほしい | `/article-fb-cmo` |
| 提案書を作りたい | `/proposal-park` |
| ミーティングの準備をしたい | `/meeting-prep` |
| LPの表示速度を改善したい | `/lp-speed` |

## 同梱内容

| フォルダ | 内容 | 数 |
|---|---|---|
| `.claude/agents/` | 自動起動する評価エージェント | 24体 |
| `.claude/commands/` | `/skill` で呼び出すスキル | 44個 |
| `.claude/knowledge/` | マーケ哲学・フックDB・CTA DB等 | 17ファイル |
| `.claude/rules/` | セキュリティ・薬機法・匿名化ルール | 4ファイル |

## 詳細ドキュメント

AI教科書で詳しい使い方を学べます：
https://isshins0919-svg.github.io/ai-park/reports/textbook/

## 作成者

澤田一進 ｜ 一進AI
