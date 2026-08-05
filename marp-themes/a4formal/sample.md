---
marp: true
theme: a4formal
header: a4formal sample / report header
footer: Sample report — 2026-08-05
paginate: true
---

<!-- _class: title tlp-clear -->

# A4 Formal Theme
## Marpで作る印刷・配布用A4レポート

氏名 役職
所属・組織名
2026-08-05

---

<!-- _class: lead -->

# 1. テーマの設計
## スライドではなく、複数ページの報告書として読みやすい情報密度と階層を設定しています。
### Chapter 1 / Overview

1. **テーマの設計**
2. 通常ページ
3. 高密度ページ
4. TLP・反転表示

---

<!-- _class: tlp-green -->

# 通常ページの例

## 基本設計

`a4formal` は、A4縦向きのPDFレポートをMarp for VS Codeから出力するためのテーマです。本文は10.5pt、ページ余白は左右18mmを基準とし、一般的な業務報告書に近い情報量を収容します。

### 主な機能

- `title`: 報告書の表紙
- `lead`: 章扉兼サマリー
- `small`: 文字量や表が多いページ向けの高密度表示
- `invert`: 注意喚起や別紙の区切り
- `tlp-red` / `tlp-amber` / `tlp-green` / `tlp-clear`: TLP 2.0ラベル

> ページ分割は `---` で明示します。通常のMarkdown文書のような自動改ページは行われないため、プレビューで各ページの収まりを確認してください。

---

<!-- _class: compact-meta -->

# 1枚資料の例

> **調査基準日** 2026年07月27日　｜　**対象期間** 2017年～2026年07月　｜　**調査方法** 公開情報調査

## 総括

通常ページの `#` は、複数ページの報告書だけでなく1枚資料でも本文領域を確保できるよう20ptとしています。調査条件は、この例のように見出し直下のメタ情報帯へまとめると、3行の箇条書きより縦方向を節約できます。

## 運用

- ページに `<!-- _class: compact-meta -->` を指定します。
- `#` の直後に引用記法 `>` で調査条件を1行に記載します。
- 項目が多い場合は無理に詰めず、2行までを目安とします。

---

<!-- _class: small -->

# `small` クラスの例

`<!-- _class: small -->` を指定したページでは、本文を10.5ptから9ptへ縮小します。通常ページではわずかに収まらない場合や、比較表を1ページに維持したい場合に限定して使用する想定です。

| 項目 | 通常 | small | 備考 |
|:--|:--|:--|:--|
| 本文 | 10.5pt | 9pt | 行間も1.55から1.45へ縮小 |
| H1 | 20pt | 18.5pt | ページタイトル |
| H2 | 14pt | 13pt | 節見出し |
| H3 | 11.5pt | 10.5pt | 小見出し |
| 表 | 9pt | 8pt | セル余白は共通 |

## クラスの併用

クラスは空白区切りで併用できます。たとえば `<!-- _class: small tlp-amber -->` は、高密度ページにTLP:AMBERを表示します。

### 運用上の注意

- 可読性を保つため、まず図表や文章の整理を検討し、必要なページだけ `small` を指定します。
- PDF出力後は100%表示と印刷の両方で可読性を確認します。
- 日本語フォントはOS上で利用可能なフォントへ順番にフォールバックします。

---

<!-- _class: invert tlp-amber -->

# 反転表示とTLP

`invert` とTLPクラスは併用できます。このページでは `invert tlp-amber` を指定しています。

## TLPラベル

TLPラベルはheader要素上にCSSテキストとして描画されるため、外部画像を必要としません。

- `tlp-red`: TLP:RED
- `tlp-amber`: TLP:AMBER
- `tlp-green`: TLP:GREEN
- `tlp-clear`: TLP:CLEAR
- `tlp-none`: 非表示

詳細は [FIRST Traffic Light Protocol (TLP) 2.0](https://www.first.org/tlp/) を参照してください。
