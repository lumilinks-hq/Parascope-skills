# Zen

Japanese Design Skills for AI Coding Agents.

日本語に最適化された美しいインターフェースを作るための [Claude Code Skills](https://docs.anthropic.com/en/docs/claude-code/skills) パッケージ。

## Install

```bash
npx skills add kgsi/zen
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
- プロファイル別推奨値 — media / saas / docs / dashboard で最適値が違う
- Reject / Warn 条件 — `break-all` 全体適用、本文の過剰な `letter-spacing` 等は即差し戻し
- 責務分離 — 本文 / 見出し / 表 / フォームのルールを分けて評価
- CSSレシピ — 修正提案時に使える再利用可能なCSS断片

**設計思想:**

タイポグラフィを音楽に例える — ハーモニー（文字サイズの比率）、リズム（余白の規則性）、メロディ（コンテンツそのもの）。恣意的な値の集合ではなく、数学的な法則に従った体系として設計する。

### `/zen-clarify` — UXコピー

日本語UIコピー・マイクロコピーを評価し、具体的な改善を提案する。

```
/zen-clarify src/components/login-form.tsx
```

**カバーする領域:**
- 敬語レベルの一貫性 — 一画面内でトーンが揺れていないか
- ボタンラベル — 活用形式（体言止め / 辞書形 / ます形）の統一
- エラーメッセージ — 「原因 + 対処法」構造、温度感の調整
- カタカナ語の密度 — 和語で通じるなら和語
- 主語・目的語の明示 — 「削除しました」→ 何が？
- 空状態 — 導線とCTAの提供

### `/zen-critique` — 統合批評

タイポグラフィ + UXコピー + サイト全体の設計品質を横断的に批評する。

```
/zen-critique src/app/page.tsx
```

**独自の評価観点:**
- 情報密度と余白 — 日本語の視覚密度に余白が合っているか
- 和洋バランス — 英語ナビ × 日本語コンテンツのちぐはぐさ
- フォーム設計 — 氏名順序、郵便番号補完、入力モード
- レスポンシブ — 見出しの不自然な改行、ボタンの折り返し
- ダークモード — 日本語フォントの可読性補正
- アクセシビリティ — `lang="ja"`、コントラスト比
- 壊れやすい場所チェック — 本文と見出しの混同、`break-all` 乱用、表/フォーム分離、mixed-script 崩れ

## Why "Zen"

禅 — 引き算の美学、意図的な余白、静けさの中の力。日本語デザインが持つべき品質そのもの。

## Author

[Parascope](https://parascope.design) — デザイン × AI のキュレーションメディア

## License

Apache 2.0
