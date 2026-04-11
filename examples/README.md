# /typeset-ja スキル比較デモ

SaaS LP「TaskFlow」を題材に、`/typeset-ja` スキルの有無でタイポグラフィがどう変わるかを比較する。

## ファイル

- `before.html` — スキルなし（典型的なAI生成LP）
- `after.html` — `/typeset-ja` 適用後

## 比較表

| 観点 | Before（スキルなし） | After（スキルあり） |
|---|---|---|
| **フォント** | `Inter` のみ。日本語フォント未指定 | `Inter` + `Noto Sans JP` + 游ゴシック Medium フォールバック |
| **行間** | `line-height: 1.5` | `line-height: 1.8`（日本語の視覚密度に合わせて） |
| **行長** | `max-width: 70ch`（広すぎ） | 長文のみ `max-width: 36em`。カード・UIには適用しない（レイアウト優先） |
| **文字サイズ** | 恣意的（15px, 17px, 19px, 22px...） | モジュラースケール ratio 1.25（0.64 / 0.8 / 1 / 1.25 / 1.5625 / 1.953 / 2.441rem） |
| **余白** | 場当たり的（18px, 35px, 70px...） | Vertical Rhythm（行送り 1.8rem の倍数で統制） |
| **字間** | `letter-spacing: 0.05em`（広すぎ） | `letter-spacing: 0`（日本語のデフォルトが最適） |
| **ウェイト** | `font-weight: 700` の多用 | 見出し `500`、本文 `400`。日本語は画数が多く 500 で十分 |
| **約物** | 処理なし | 見出し: `"palt" 1`、和欧間: `"chws" 1, "vchw" 1` |
| **禁則処理** | 設定なし | `line-break: strict; overflow-wrap: break-word;` |
| **料金の数字** | デフォルト | `"tnum" 1`（等幅数字で桁揃え） |
| **体系性** | なし（値に根拠がない） | 全値がスケールまたはリズム単位の倍数（「なぜこの値か」に答えられる） |

## 確認方法

```bash
open skills-sample/before.html
open skills-sample/after.html
```

ブラウザで並べて見比べる。特に本文の読みやすさ、見出しの重さ、全体のリズム感の違いに注目。
