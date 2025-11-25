---
marp: true
theme: formal
header: formal-sample-header
footer: formal-sample-footer
paginate: true
---
<style>
:root {
  /* プレゼンファイルからの相対パスで指定 */
  --logo-image: url('./logo.png');
}
</style>
<!-- _class: title -->
# theme: formalのサンプル
## サンプルテキスト

氏名
所属
会社
2025-11-25

---
<!-- _class: invert-->
# 本sampleの設定

ヘッダーは以下の通りとし、タイトルページの前段に`<sytle>`でロゴを指定。
```
---
marp: true
theme: formal
header: formal-sample-header
footer: formal-sample-footer
paginate: true
---
<style>
:root {
  /* プレゼンファイルからの相対パスで指定 */
  --logo-image: url('./logo.png');
}
</style>
<!-- _class: title -->
# theme: formalのサンプル
## サンプルテキスト
...
```
`sample.md`を処理して`sample.pdf`として配置しました。

---

# 使い方

## Marp for vscodeの設定

- Marpのthemeに追加します。
  - `Markdown > Marp: Themes` に `https://raw.githubusercontent.com/hogehuga/vulnRespStudyGroup/refs/heads/master/marp-themes/formal/formal.css`を追加するだけ

## ファイル配置

- ロゴを置く場合は、対象の `.md` ファイルと同じ階層にロゴ画像を置いてください。

---

# スライドの種類 (レイアウト)

状況に合わせて以下のクラスを使い分けてください。

|用途|class|
|:--|:--|
|タイトルスライド|title|
|セクション区切り/扉|lead|
|通常スライド|(指定なし)|
|反転カラー|invert|
|本文小さい文字|small|

---
<!-- _class: lead -->
# [lead]章などの見出し利用
## leadは、章のタイトルなどを入れて使うものです
### 所要時間5分(セクション所要時間など)

- 1: 初めに
- **2: 章などの見出し利用**
- 3: このように、章タイトルを入れておくと参加者がわかりやすい
- 
---

# class指定のないコンテンツ

## 概要

`##` は、このようにスライド内でのまとめに使います。

### 要点1

`###` は上記 `##` のサブカテゴリ的に使う想定です。

---
<!-- _class: small -->

# Class: small

`small`は、通常のスライドより文字数が多くなるものに利用します。
h1-h3等は、通常のスライドと同じ動作をします。

---
<!-- _class: invert tlp-red -->

# classの組み合わせ

tlp指定は、smallやinvertと組み合わせることができます。スペースで区切ってください。
但し、small/invert/lead/title の組み合わせは確認していません。

```
---
<!-- _class: invert tlp-red -->　　＜＝＝ここのこと

# classの組み合わせ

tlp指定は、smallやinvertと組み合わせることができます。スペースで区切ってください。
但し、small/invert/lead/title の組み合わせは確認していません。
---
```

---
<!-- _class: lead -->
# 以上
## 今後、close用のclassを拡張するかもしれません。