---
marp: true
theme: a4report
paginate: true
header: header
footer: footer
---

<!-- class: title tlp-red -->

# report title
## sub title

hogehuga
Vulnerability Response Study Group
2026-04-20


---
<!-- class: tlp-green -->


# この資料について

プレゼンテーションではなく、レポート用に大量の文字を記載できるようにしています。

作成はAntropic Sonnet4.6 Adaptiveによるものです。

```
---
marp: true
theme: a4report
paginate: true
header: header
footer: footer
---

<!-- class: title tlp-red -->

# report title
## sub title

hogehuga
Vulnerability Response Study Group
2026-04-20


---

<!-- class: tlp-green -->

# この資料について

プレゼンテーションではなく、レポート用に大量の文字を記載できるようにしています。
```

通常は、以下の3点の設定で利用すると思います。

- `<!-- class: tlp-green -->` などの TLP2.0 の表示
- `header`, `footer` による、作成者や著作権表示
- `paginate` による、ページ数表示

利用方法としては、以下のようになると思います。

- タイトルを用意する
  - `<!-- _class: title tlp-xxx -->` で2つのclassを指定する
- 本文を書く
  - TLPは基本変わらないはずなので`<!-- class: tlp-xxx -->`で永続設定する
  - 必要に応じて`<!-- _class: tlp-xxx -->`で一時的にTLPを変える

---

# class: small

それほど小さくないような気はしますが、大量に書けるようにこれも小さい文字を用意しています。

- a
- b
- c
- d

---

<!-- _class: invert tlp-red -->

# class: invert

必要かは不明ですが、Marpのthemeでは実装されうることが多いので実装しています。

以上。