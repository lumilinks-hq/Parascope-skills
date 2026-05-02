# Parascope Skills

[Parascope](https://parascope.design) が配布する [Claude Code](https://docs.anthropic.com/en/docs/claude-code/skills) 向けスキル集。

AI コーディングエージェントが日本語のWebサイト・アプリを構築するときに、英語圏のデフォルト（`line-height: 1.5`、65ch 行長、Inter 単体指定、フラットな敬語）をそのまま当てると破綻します。このリポジトリは、日本語固有のデザイン知識を Claude Code Skill 形式で提供し、生成コードの品質を底上げします。

## Install

リポジトリ単位で一括インストール:

```bash
npx skills add lumilinks-hq/Parascope-skills
```

## Skills

| スキル | 概要 | ステータス |
|---|---|---|
| [`/zen`](./.claude/skills/zen/README.md) | 日本語デザイン品質（タイポグラフィ / UIコピー / 統合批評） | ✅ v0.2.0 |

各スキルの詳細・使い方・カバーする領域は、上記リンク先の README を参照してください。今後、デザイン × AI に関するスキルを順次追加予定です。

## Author

[Parascope](https://parascope.design) — デザイン × AI のキュレーションメディア

## License

Apache 2.0
