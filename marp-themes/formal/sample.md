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
# theme: formal のサンプル
## レイアウト・TLP・クラス併用の例

氏名
所属
会社
2026-05-11

---
<!-- _class: invert -->

# 本サンプルの設定

ヘッダー/フッター、ページ番号、ロゴを以下のように指定しています。

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
```

`sample.md` を処理して `sample.pdf` として配置しています。

---

# 使い方

## Marp for VS Code の設定

`Markdown > Marp: Themes` に以下のURLを追加します。

```
https://raw.githubusercontent.com/hogehuga/vulnRespStudyGroup/refs/heads/master/marp-themes/formal/formal.css
```

## ファイル配置

ロゴを表示する場合、対象の `.md` ファイルと同じ階層にロゴ画像 (例: `logo.png`) を配置してください。TLPラベルはCSSにSVG data URLとして埋め込まれているため、別途画像を配置する必要はありません。

---

# スライドの種類 (レイアウト)

状況に合わせて以下のクラスを使い分けてください。

| 用途 | class |
|:--|:--|
| タイトルスライド | `title` |
| セクション区切り/扉 | `lead` |
| 通常スライド | (指定なし) |
| 反転カラー | `invert` |

各レイアウトでの `#` / `##` / `###` の扱いを以降のスライドで例示します。

---
<!-- _class: lead -->

# [lead] 章などの見出し利用
## leadは章のタイトルなどに使うレイアウトです
### 所要時間 5分

- 1: 初めに
- **2: 章などの見出し利用**
- 3: 通常スライド・invert・TLPの例
- 4: クラスの組み合わせ
- 5: まとめ

---

# (指定なし) 通常スライド

`#` (H1) はスライドタイトル。teal の下線がつきます。

## H2 — スライド内の大見出し

`##` (H2) は teal で、細い下線つき。スライド内のセクション区切りに使います。

### H3 — スライド内の中見出し

`###` (H3) はグレーで下線なし。`##` のサブカテゴリとして使う想定です。

本文・リストはフォントサイズ40px、左右80px・上70px・下80pxの余白で表示されます。

- 箇条書きは行間をやや詰めて表示
- リストの中身は左寄せが基本

---
<!-- _class: invert -->

# Class: invert (反転カラー)

ダークグレー背景に反転します。要素の構造は通常スライドと同じです。

## 用途

重要な警告、話題転換のアクセント、章タイトル前のフックなどに使います。

### 注意

- 図表を貼る場合は背景色との相性に注意
- コードブロックは通常スライドと同様に表示されます

---
<!-- _class: tlp-red -->

# TLP切替: TLP:RED の例

`<!-- _class: tlp-red -->` で左上にTLPラベルが表示されます。

TLP 2.0準拠で以下の4種類が利用可能です。

- `tlp-red` — Not for disclosure, restricted to participants only
- `tlp-amber` — Limited disclosure, restricted to participants' organization
- `tlp-green` — Limited disclosure, restricted to the community
- `tlp-clear` — Recipients can spread this to the world

`tlp-none` または何も指定しない場合はラベルは表示されません。

詳細は <https://www.first.org/tlp/> を参照してください。

---
<!-- _class: invert tlp-amber -->

# クラスの組み合わせ

スペース区切りで複数のクラスを指定できます。このスライドは `invert tlp-amber` を指定しています。

```
<!-- _class: invert tlp-amber -->
```

組み合わせ可能な例:

- `title tlp-red`
- `lead tlp-amber`
- `invert tlp-green`
- `tlp-clear` のみ (通常スライド + TLP)

レイアウト系の `title` / `lead` / `invert` は構造が異なるため、これら同士の組み合わせは想定していません。TLPクラスはどのレイアウトとも組み合わせ可能です。

---
<!-- _class: lead -->

# 以上
## ご利用ありがとうございます
### —

- フィードバックは GitHub Issues へ
- TLP 2.0 定義: https://www.first.org/tlp/
