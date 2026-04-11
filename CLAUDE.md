# Zen — Japanese Design Skills for AI Coding Agents

日本語に最適化された美しいインターフェースを作るための Skills パッケージ。

AI コーディングエージェント（Claude Code 等）が日本語のWebサイト・アプリケーションを構築する際に、英語圏のデザインルールをそのまま適用して起きる問題を防ぐ。

## スキル一覧

| スキル | 概要 | 状態 |
|---|---|---|
| `/zen-typeset` | 日本語タイポグラフィの評価・改善 | ✅ v0.1.0 |
| `/zen-clarify` | 日本語UIコピー・マイクロコピーの評価・改善 | ✅ v0.1.0 |
| `/zen-critique` | 日本語デザイン品質の統合批評 | ✅ v0.1.0 |

## インストール

```bash
npx skills add parascope/zen
```

## なぜ Zen か

AI が生成するフロントエンドコードは英語圏のルールで設計されている。`line-height: 1.5`、`max-width: 65ch`、Inter フォント — どれも日本語では破綻する。

Zen は日本語固有のデザイン知識を構造化し、AI が日本語サイトを作る際に正しい判断ができるようにする。

## 提供元

[Parascope](https://parascope.design) — デザイン × AI のキュレーションメディア
