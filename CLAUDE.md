# Parascope Skills — Claude Code skills by Parascope

[Parascope](https://parascope.design) が配布する Claude Code 向けスキル集。

AI コーディングエージェント（Claude Code 等）が日本語のWebサイト・アプリを構築する際に、英語圏のデザインルールをそのまま適用して起きる問題を防ぐためのドメイン特化スキルを提供する。

## 収録スキル

| スキル | 概要 | バージョン |
|---|---|---|
| `/zen` | 日本語デザイン品質（タイポグラフィ / UIコピー / 統合批評）。`--mode typeset|clarify|critique` で観点を切替 | v0.2.0 |

`/zen` は単一スキル + 3 モード構成。依頼内容から自動ルーティング、`--mode` で明示指定可。

| モード | 観点 | リファレンス |
|---|---|---|
| `typeset` | 日本語タイポグラフィの評価・改善 | `.claude/skills/zen/references/typeset.md` |
| `clarify` | 日本語UIコピー・マイクロコピーの評価・改善 | `.claude/skills/zen/references/clarify.md` |
| `critique` | 日本語デザイン品質の統合批評（typeset + clarify + 横断品質） | `.claude/skills/zen/references/critique.md` |

ドメイン知識は `.claude/skills/zen/references/japanese-{typography,ux-copy,design-quality}.md` に分離。

## インストール

```bash
npx skills add lumilinks-hq/Parascope-skills
```

## なぜ Parascope Skills か

AI が生成するフロントエンドコードは英語圏のルールで設計されている。`line-height: 1.5`、`max-width: 65ch`、Inter フォント — どれも日本語では破綻する。

Parascope Skills は、デザイン × AI のドメイン知識を Claude Code Skill 形式で構造化し、AI が日本語サイトを作る際に正しい判断ができるようにする。

## 提供元

[Parascope](https://parascope.design) — デザイン × AI のキュレーションメディア
