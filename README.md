# Zen

Japanese Design Skills for AI Coding Agents.

日本語に最適化された美しいインターフェースを作るための [Claude Code Skills](https://docs.anthropic.com/en/docs/claude-code/skills) パッケージ。

## Install

```bash
npx skills add parascope/zen
```

## Skills

### `/zen-typeset` — タイポグラフィ

日本語Webタイポグラフィを評価し、具体的な改善を提案する。

```
/zen-typeset src/app/page.tsx
```

**カバーする領域:**
- 行長 — `em` 基準（`ch` は日本語に不適）、長文コンテンツのみ制限
- 行間 — `line-height: 1.8`（日本語は英語より広く取る）
- フォント選定 — 日本語Webフォント、游ゴシック問題、和欧混植
- モジュラースケール — 比率に基づく文字サイズ体系
- Vertical Rhythm — 行送りの倍数で余白を統制
- 約物 — `palt` / `halt` / `chws` の使い分け
- ウェイト — 日本語フォントは画数が多く、500 で十分な太さがある
- 禁則処理 — `line-break: strict`

**設計思想:**

タイポグラフィを音楽に例える — ハーモニー（文字サイズの比率）、リズム（余白の規則性）、メロディ（コンテンツそのもの）。恣意的な値の集合ではなく、数学的な法則に従った体系として設計する。

## Coming Soon

- `/zen-clarify` — 日本語UXコピー・マイクロコピーの改善
- `/zen-critique` — 日本語サイトとしてのデザイン批評

## Why "Zen"

禅 — 引き算の美学、意図的な余白、静けさの中の力。日本語デザインが持つべき品質そのもの。

## Author

[Parascope](https://parascope.design) — デザイン × AI のキュレーションメディア

## License

Apache 2.0
