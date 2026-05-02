# Zen — Before / After 比較デモ

`/zen` の 3 モード（`typeset` / `clarify` / `critique`）を適用する前と後で、日本語サイトの品質がどう変わるかを視覚的に比較するサンプル集。

## 顔となる showcase

**Critique SaaS 複合（`critique-saas-before.html` / `critique-saas-after.html`）** — `critique` モードで 3 観点を統合した効果が最も伝わるデモ。SaaS「TaskFlow」の LP・ログイン画面・ダッシュボードを 1 ページにまとめ、タイポグラフィ・UIコピー・サイト全体の設計品質を横断的に改善している。

```bash
# ブラウザで比較ビューアを開く
open examples/compare.html
```

## 3 モード観点の比較表

### typeset モード（タイポグラフィ）

| 観点 | Before（スキルなし） | After（スキルあり） |
|---|---|---|
| **フォント** | `Arial, sans-serif` のみ。日本語フォント未指定 | `Noto Sans JP` + `Yu Gothic Medium` フォールバック。欧文も Noto Sans JP で描画 |
| **ウェイト** | `font-weight: 700` 多用 | 400 / 500 の 2 ウェイトに絞る（W2 クリア）。見出しは `palt` でメリハリ |
| **行間** | `line-height: 1.4`（日本語に窮屈） | 本文 1.8、**表・フォームは 1.5 に分離**（R6 クリア） |
| **行長** | 制限なし、または ch 単位 | 長文のみ `em` で制限。LP ヒーロー・CTA には適用しない |
| **文字サイズ** | 恣意的（13px, 15px, 17px, 24px, 28px） | Minor Third (1.2) モジュラースケールで統制 |
| **余白** | 場当たり的（12, 15, 18, 25, 30px...） | 8 の倍数（`--space-xs` 〜 `--space-2xl`） |
| **字間** | `letter-spacing: 0.04em`（日本語に過剰） | `0`（日本語のデフォルトが最適） |
| **約物** | なし | 見出し `palt`、和欧間 `chws`、数字 `tnum` |
| **禁則処理** | なし | `line-break: strict; overflow-wrap: anywhere;` |

### clarify モード（UIコピー）

| 観点 | Before | After |
|---|---|---|
| **ナビゲーション** | Home / Features / Pricing / Login | ホーム / 機能 / 料金 / ログイン |
| **ボタンラベル** | Submit / Cancel / Save Changes | ログインする / キャンセル / 変更を保存する（辞書形で統一） |
| **エラーメッセージ** | 「入力が不正です」「値が無効です」 | 「メールアドレスの形式が正しくありません。『example@domain.com』の形式で入力してください」（原因＋対処法） |
| **確認ダイアログ** | 「確認」「はい / いいえ」 | 「このタスクを削除しますか？」「削除する / キャンセル」（操作結果を明示、選択肢は具体アクション） |
| **フォーム順序** | First Name / Last Name | 姓 / 名（日本語順、`autocomplete` 属性付き） |
| **空状態** | 「No data」 | 「まだデータがありません」＋ CTA「タスクを作成する」 |
| **敬語** | 混在 | です／ます調で統一 |

### critique モード（サイト全体の設計品質）

| 観点 | Before | After |
|---|---|---|
| **lang 属性** | `<html lang="en">` | `<html lang="ja">` |
| **レイアウト** | 固定幅 `960px`（レスポンシブなし） | `max-width` + `auto` マージン、`@media (max-width: 768px)` で縦積み |
| **ダークモード** | 非対応 | `prefers-color-scheme: dark` 対応。補助テキストは AA クリアまでコントラスト調整 |
| **アクセシビリティ** | フォーカスリング削除、aria-label なし | `:focus-visible` 表示、アイコンボタンに日本語 `aria-label` |
| **モーション配慮** | 常時アニメ | `prefers-reduced-motion` 対応 |
| **Critical 減点条件** | `lang` 誤り ＋ 日本語フォント未指定 ＋ フォーカスリング削除（3 件該当で -2 減点） | 全てクリア |

## サンプル一覧

| ペア | モード | 題材 |
|---|---|---|
| `critique-saas-before.html` / `critique-saas-after.html` | **critique（3 観点統合）** | SaaS LP + ログイン + ダッシュボード |
| `before.html` / `after.html` | typeset | SaaS ランディングページ（単体） |
| `blog-before.html` / `blog-after.html` | typeset | ブログ記事（長文） |
| `dashboard-before.html` / `dashboard-after.html` | typeset | 業務ダッシュボード |
| `clarify-settings-before.html` / `clarify-settings-after.html` | clarify | 設定画面のコピー |
| `clarify-errors-before.html` / `clarify-errors-after.html` | clarify | エラーメッセージ集 |

## 確認方法

```bash
# 比較ビューア（推奨）— 全ペアをタブで切り替え、並べて比較 / Before のみ / After のみ
open examples/compare.html

# 個別に開く
open examples/critique-saas-before.html
open examples/critique-saas-after.html
```

ブラウザで並べて見比べ、特に次の 3 点に注目してください。

1. **本文の読みやすさ** — 行間と字間の違いで、同じテキストでも「呼吸」が変わる
2. **見出しの重さ** — 700 の多用から 500 ＋ palt へ。日本語では 500 で十分な存在感が出る
3. **全体のリズム感** — 場当たりの余白からモジュラースケール＋8 の倍数へ。値の根拠が揃う
