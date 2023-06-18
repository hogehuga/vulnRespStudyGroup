# CISA Cybersecurity Derectives翻訳

Last update: 2023/06/18 JST

CISAの[Cybersecurity Directives](https://www.cisa.gov/news-events/directives)で公開されている、Emergency DirectivesやBinding Operational Directivesを適当に翻訳します。

## 方針

- なるべく直訳の機械翻訳を基に、意味の分かる日本語になるように人力修正をする。
    - DeepLやLLMではHallucinationが発生する恐れがあるため
- 出来るところから順次実施

### 書式

#### list

> 1. hogehoge
> 2. hugahuga 
>    a. hogehoge
>    b. hugahuga 

の場合、Markdownの仕様上、以下に変換する
1. hogehoge
2. hugahuga
    1. hogehoge
    2. hugahuga

#### 文字

- 基本的に文章では全角括弧（`（`と`）`）を利用する。
- 機械翻訳時に、列挙内容が`、`で多数区切られる場合があるが、適宜`/`での分割にする
- 英字と日本語、日本語の区切りで半角空白は使わない（リモート コード、等にはしない）


## ライセンス

この翻訳文を搾取した営利活動は避けたい為、以下のライセンスとする
- Creative Commons 表示-改変禁止 4.0 国際（Attribution-NoDerivatives 4.0 Internal）
  - https://creativecommons.org/licenses/by-nd/4.0/legalcode
  - 対象は本翻訳文のみであり、自身でCISAのリリースを翻訳する場合は何ら関与しない
    - 自分で翻訳するのは面倒だから外部参照/コピペで参照する場合は、出展を明示してほしいというだけ
    - 脆弱性対応勉強会にある翻訳文、みたいに紹介してもらえればそれでいいです

CISAのリリース自体には、ライセンス表記は無いようだ。