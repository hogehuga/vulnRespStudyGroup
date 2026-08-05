# Marp Theme: A4 Formal

Version 0.3.0 (2026-08-05)

`formal` テーマのデザインと操作体系を引き継ぎ、印刷・PDF配布用のA4縦向きレポートに最適化した Marp for VS Code 用テーマです。表紙、章扉、通常ページ、高密度ページ、反転表示、TLP 2.0ラベル、header/footer、ページ番号に対応します。

## 基本設定

`a4formal.css` をMarpのカスタムテーマとして登録し、Markdownのfront matterで指定します。

```markdown
---
marp: true
theme: a4formal
header: レポート名
footer: 組織名 — 2026-08-05
paginate: true
---
```

VS Codeでは、設定項目 `Markdown > Marp: Themes` にローカルの `a4formal.css` または公開後のraw URLを追加します。

```text
https://raw.githubusercontent.com/hogehuga/vulnRespStudyGroup/refs/heads/master/marp-themes/a4formal/a4formal.css
```

## ページ仕様

| 項目 | 設定 |
|:--|:--|
| 用紙 | A4縦、210 × 297mm |
| 本文 | 10.5pt、行間1.55 |
| 余白 | 上17mm、左右18mm、下16mm |
| `small` 本文 | 9pt、行間1.45 |
| 背景 | `formal` と同じクリーム色 |

Marpでは `---` で区切られた各sectionが1ページになります。ワープロのような自動改ページは行われないため、ページごとに内容を調整してください。

## TLP 2.0

指定方法は `formal` と同じです。デフォルトではTLPラベルを表示しません。

| クラス | 表示 |
|:--|:--|
| `tlp-red` | TLP:RED |
| `tlp-amber` | TLP:AMBER |
| `tlp-green` | TLP:GREEN |
| `tlp-clear` | TLP:CLEAR |
| `tlp-none` | 非表示 |

```markdown
<!-- class: tlp-green -->
```

アンダースコアなしの `class` は以降の全ページに適用します。次のように `_class` を指定すると、そのページだけに適用します。

```markdown
<!-- _class: tlp-red -->
```

色と共有範囲の定義は [FIRST TLP 2.0](https://www.first.org/tlp/) を参照してください。

TLPラベルは、front matterの `header` により生成されるheader要素上へCSSテキストとして表示します。このため、TLPを使用する文書では `header:` を設定してください。SVGやPNG等の画像ファイルは必要ありません。ラベル文字列は各TLPクラスのCSSへ直接記述しており、`content` 内のCSS変数には依存しません。

TLPラベルはページ上端のheader帯の左端へ配置されます。本文の `#` 見出し下にある罫線とは別の層で描画されるため、罫線の下へ隠れる配置ではありません。

## ページクラス

| 用途 | クラス | 想定 |
|:--|:--|:--|
| 表紙 | `title` | 文書名、副題、作成者情報 |
| 章扉兼サマリー | `lead` | 章名、要旨、章内構成 |
| 通常ページ | 指定なし | 本文、見出し、表、引用、コード |
| 高密度ページ | `small` | 表や文字量がわずかに多いページ |
| 1枚資料のメタ情報 | `compact-meta` | 調査基準日、対象期間、調査方法等 |
| 反転表示 | `invert` | 注意喚起、別紙、強い区切り |

### `title` — 表紙

`#` は文書名、`##` は副題、本文段落は右下の作成者情報として配置されます。

```markdown
<!-- _class: title tlp-clear -->

# 脆弱性管理に関する調査報告書
## 2026年度上期版

氏名
所属
2026-08-05
```

### `lead` — 章扉兼サマリー

A4レポートでは、プレゼンテーションのアジェンダスライドに相当する機能を、章の要旨と章内構成を示すページとして扱います。`#` は章名、`##` は要旨、`###` は章番号や分類、リストは章内構成です。

```markdown
<!-- _class: lead -->

# 1. 調査の概要
## 本章では、調査目的、対象範囲および評価方法を示します。
### Chapter 1 / Overview

1. **調査の概要**
2. 調査対象
3. 評価方法
```

### `compact-meta` — 1枚資料のメタ情報

ページに `compact-meta` を指定し、`#` の直後へ引用記法で調査条件を置くと、1行のメタ情報帯になります。

```markdown
<!-- _class: compact-meta -->

# 調査報告書：抜粋

> **調査基準日** 2026年7月27日　｜　**対象期間** 2017年～2026年7月　｜　**調査方法** 公開情報調査
```

### `small` — 高密度ページ

通常ページより本文、見出し、表を一段階だけ小さくします。クラスは他の指定と併用できます。

```markdown
<!-- _class: small -->
```

```markdown
<!-- _class: small tlp-amber -->
```

`small` はページへ内容を無制限に詰め込むための機能ではありません。PDFを印刷して利用する場合は、9ptで十分な可読性が得られるか確認してください。

### `invert` — 反転表示

ダークグレーの背景に切り替えます。構造は通常ページと同じです。

```markdown
<!-- _class: invert tlp-red -->
```

## クラスの適用範囲

- `<!-- class: ... -->`: その位置以降の全ページ
- `<!-- _class: ... -->`: そのページのみ
- 複数クラス: `<!-- _class: small tlp-amber -->` のように空白区切り

レイアウト系の `title`、`lead`、`invert` を相互に組み合わせることは想定していません。TLPクラスと `small` は必要に応じて併用できます。

## ファイル

- `a4formal.css`: テーマ本体
- `sample.md`: 各レイアウトとクラスのサンプル
- `README.md`: 導入・利用方法

## 参考

- [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)
- [Marpit theme CSS](https://marpit.marp.app/theme-css)
- [FIRST TLP 2.0](https://www.first.org/tlp/)
