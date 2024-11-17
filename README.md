# 概要

facebook上のグループ "脆弱性対応研究会" の資料を配置ししています。

# 目的

オープンなサイバーセキュリティの勉強会をしたく、**脆弱性対応研究会** というグループを作りました。
**脆弱性対応研究会** の成果発表等の体裁で、 **脆弱性対応勉強会** を開催しています。

- [脆弱性対応研究会](https://www.facebook.com/groups/zeijyakuseitaioukenkyukai/)
- [脆弱性対応勉強会](https://zeijyakuseitaioukenkyukai.connpass.com/)
  - 研究会主催の勉強会なので、脆弱性対応勉強会、です。
  - Twitterハッシュタグ "#vulnstudy" を利用しています。
  - 同勉強会の告知として [connpassのグループ](https://zeijyakuseitaioukenkyukai.connpass.com/) を利用しています。

取り扱う範囲は、セキュリティ全般になります。

- 脆弱性それ自体の理解や、対応方法について
- マルウェアでの攻撃やそれの検知、防ぎ方について
- セキュリティに関連する情報の取り扱い（OSINT等含む）について
- etc

## 参加ルール

チャタムハウスルール、TLP2.0を適用します。
- 参加者に関しては、チャタムハウスルールに従う
  - 登壇者に関しては、登壇者の意向に従う（所属の公開可否等）
- TLPは、基本的にTLP2.0の TLP:CLEAR(共有範囲:全世界が対象) とし、登壇者等が意図的に制限する場合はそれに従う

### チャタムハウスルール

概要は以下の通りです。
- 会議において、以下を守りましょう
  - 参加者は会議中に得た情報を自由に使用できる
  - 但し、以下を守ること
    - 情報発信者や所属を特定する事をしない
    - 他の参加者を特定する


詳細は以下を確認ください。
- 日本シーサート協議会の[チャタムハウスルール（Chatham House Rule）](https://www.nca.gr.jp/activity/#:~:text=%E3%83%81%E3%83%A3%E3%82%BF%E3%83%A0%E3%83%8F%E3%82%A6%E3%82%B9%E3%83%AB%E3%83%BC%E3%83%AB%E3%81%A8%E3%81%AF,%E3%83%AB%E3%83%BC%E3%83%AB%E3%81%A8%E3%81%AA%E3%81%A3%E3%81%A6%E3%81%84%E3%81%BE%E3%81%99%E3%80%82) を参照
- 本勉強会での追加事項である「登壇者の例外」については、登壇者が認める範囲で公開可能

### TLP 2.0

基本的に TLP:CLEAR 相当とし、登壇者等により意図的に公開範囲が支持された場合は、それに従ってください。

詳細は以下の通り
- 原文としては FIRSTの[FIRST StandardsDefinitions and Usage Guidance -Version2.0日本語版](https://www.first.org/tlp/docs/v2/tlp-v2_ja.pdf)を参照してください
- 分かりやすい解説としては、JPCERT/CCのblog [TLP v2の日本語版が公開されました](https://blogs.jpcert.or.jp/ja/2022/09/tlp-v2.html)を参照してください

## 配置 

用途ごとにディレクトリを切っています。

- document
  - 脆弱性対応研究会/勉強会に関するドキュメント
  - 汎用的に使える情報、等（を置く予定）
- project
  - 継続的な検討をするプロジェクトを配置する
- report
  - 時折作成する、IPA等のレポートを確認したサマリなどを配置
- studySession
  - 勉強会で利用した資料等を配置
- x-in-preparation
  - 準備中のコンテンツ
    - 次回実施の資料とか計画とかを配置
    - 長期計画の場合、可能ならここで議論結果を更新する
  - ディレクトリ一覧の最後にする/実験的な意味合いなので "x-" を付けた
- releasenote.md
  - 更新履歴的な何か
- README.md
  - 本テキスト

## 僕ら（"ら"？）は怪しくない！

出張版脆弱性対応勉強会において、おまえ誰よ？怪しくないの？壺を買わせる気では！、のような心配があるかもしれません。
一応、まともな勉強会（但し独り実施）であるため、それを示すエビデンスを提示します。

- Qiita
  - [サイバーセキュリティの草の根コミュニティ系勉強会](https://qiita.com/sonodam/items/2b3add928a7d1ae0f657)
  - 作成者は sonodam さんで、「全国」扱いになっています…
- NISC
  - [2023年サイバーセキュリティ月間の関連行事](https://security-portal.nisc.go.jp/cybersecuritymonth/2023/events/index.html#tokyo)
  - [2024年サイバーセキュリティ月間の関連行事](https://security-portal.nisc.go.jp/cybersecuritymonth/2024/events/index.html)


# その他

- 知見のある方からのPull Requestをお待ちしています！
- 今の所 hogehuga 独りで運営しています。
  - 「手伝う」ではなくて、「こういうのやりたい」という方を募集しています。
- 開場の提供を募集しております。
  - 毎回自腹でレンタルオフィス借りるのはツラすぎる
  - 同じ会社様ばかり利用させて頂くのは心苦しい
  - セキュリティにちょっと関心があるよ、という感じで非IT業の会社様でも問題ありません。
  - 毎回、土曜日10:00-12:00頃を標準でやっています。ハンズオンの場合は10:00-16:00などもあります。

よろしくお願いします。

---

# 過去の開催履歴

## 脆弱性対応勉強会

基本的には関東で開催する現地開催の勉強会

- 2018/12/08 [第00回 脆弱性対応勉強会（脆弱性対応について体験しよう）](https://zeijyakuseitaioukenkyukai.connpass.com/event/109946/)
- 2019/01/26 [第01回 脆弱性対応勉強会（脆弱性対応について体験しよう/再）](https://zeijyakuseitaioukenkyukai.connpass.com/event/113847/)
- 2019/03/30 [第02回 脆弱性対応勉強会（勝手にIPAテクニカルウオッチ ハンズオン）](https://zeijyakuseitaioukenkyukai.connpass.com/event/123143/)
- 2019/04/20 [第03回 脆弱性対応勉強会（IPAの「中小企業の情報セキュリティ対策ガイドライン第3版」を読もう）](https://zeijyakuseitaioukenkyukai.connpass.com/event/127635/)
- 2019/06/01 [第04回 脆弱性対応勉強会（ログ分析の初歩：ハンズオン）](https://zeijyakuseitaioukenkyukai.connpass.com/event/131007/)
- 2019/06/29 [第05回 脆弱性対応勉強会（ログ管理と分析の初歩）](https://zeijyakuseitaioukenkyukai.connpass.com/event/137131/)
- 2019/08/24 [第06回 脆弱性対応勉強会（日機能要求グレード2018読合せ）](https://zeijyakuseitaioukenkyukai.connpass.com/event/141424/)
- 2019/11/23 [第07回 脆弱性対応勉強会（実験会：AppGoat体験会）](https://zeijyakuseitaioukenkyukai.connpass.com/event/156511/)
- 2020/01/11 [第08回 脆弱性対応勉強会（WordPress Pluginの脆弱性ハンズオン）](https://zeijyakuseitaioukenkyukai.connpass.com/event/160949/)
- 2020/07/31 [第09回 脆弱性対応勉強会（脆弱性管理製品を知る）](https://zeijyakuseitaioukenkyukai.connpass.com/event/182959/)
- 2022/12/03 [第10回 脆弱性対応勉強会（X.1060の概要と使い所）](https://zeijyakuseitaioukenkyukai.connpass.com/event/266469/)
- 2023/03/04 [第11回 脆弱性対応勉強会（X.1060で考えるサイバーセキュリティ）](https://zeijyakuseitaioukenkyukai.connpass.com/event/269837/)
- 2023/09/02 [第12回 脆弱性対応勉強会（政策研究大学院大学のインシデント報告書を読もう）](https://zeijyakuseitaioukenkyukai.connpass.com/event/294430/)
- 2024/03/23 [第13回 脆弱性対応勉強会（NTT西日本の顧客情報不正持出しのレポートを読もう）](https://zeijyakuseitaioukenkyukai.connpass.com/event/312278/)

## Expansion

スピーカーをお呼びして、お話をして頂く勉強会

- 2020/09/18 [脆弱性対応勉強会Expansion 第01回（脆弱性診断研究会）](https://zeijyakuseitaioukenkyukai.connpass.com/event/187890/)
- 2021/02/22 [脆弱性対応勉強会Expansion 第02回（脆弱性診断研究会）](https://zeijyakuseitaioukenkyukai.connpass.com/event/203607/)
- 2021/09/24 [脆弱性対応勉強会Expansion 第03回（脆弱性診断研究会）](https://zeijyakuseitaioukenkyukai.connpass.com/event/224525/)
- 2021/10/22 [脆弱性対応勉強会Expansion 第04回（アジャイルセキュリティ）](https://zeijyakuseitaioukenkyukai.connpass.com/event/226862/)
- 2021/11/19 [脆弱性対応勉強会Expansion 第05回（OWASP ZAP&EC-CUBE）](https://zeijyakuseitaioukenkyukai.connpass.com/event/229038/)
- 2022/09/20 [脆弱性対応勉強会Expansion 第06回（脆弱性診断研究会）](https://zeijyakuseitaioukenkyukai.connpass.com/event/254807/)
- 2022/01/18 [脆弱性対応勉強会Expansion 第07回（VDPを学ぶ）](https://zeijyakuseitaioukenkyukai.connpass.com/event/305932/)

## 出張版

関東以外で開催する現地開催の勉強会

- 2022/04/01 [出張版 脆弱性対応勉強会 #01（札幌）](https://zeijyakuseitaioukenkyukai.connpass.com/event/242948/)
- 2022/07/08 [出張版 脆弱性対応勉強会 #02（大阪）](https://zeijyakuseitaioukenkyukai.connpass.com/event/253265/)
- 2023/03/15 [出張版 脆弱性対応勉強会 #03（長崎）](https://zeijyakuseitaioukenkyukai.connpass.com/event/275421/)
- 2023/06/01 [出張版 脆弱性対応勉強会 #04（大阪）](https://zeijyakuseitaioukenkyukai.connpass.com/event/285245/)
- 2024/02/09 [出張版 脆弱性対応勉強会 #05（名古屋）](https://zeijyakuseitaioukenkyukai.connpass.com/event/306261/)


## VR

youtube向けの、アバターを使った配信

- 2023/09/21 第01回 脆弱性対応勉強会VR（EPSSについて理解しよう）: connpassイベント公開なし
  - https://youtu.be/DgcLOJ59ZZ8
- 2023/09/21 [第02回 脆弱性対応勉強会VR（EPSSについて理解しよう）](https://zeijyakuseitaioukenkyukai.connpass.com/event/331547/)
  - https://youtu.be/-yDE03dd_YU


## 他の勉強会等

脆弱性対応勉強会以外の勉強会での講演等、思い出したら追加します

- yyyy-mm-dd [塩尻サイバーセキュリティ勉強会/ほぼ毎回](https://shiojiri-cyber.connpass.com/)
- 2022-08-10 [総関西サイバーセキュリティLT大会（34回）/基調講演](https://sec-kansai.connpass.com/event/253980/)
- 2024-02-04 [OWASP Nagoya Chapterミーティング第33回 OWASP 758 Day/Speaker](https://owaspnagoya.connpass.com/event/305686/)
- 2024-05-15 [総関西サイバーセキュリティLT大会（41回）/LT](https://sec-kansai.connpass.com/event/316351/)
- 2024-11-19 [Security.any #01 セキュリティあるあるLT](https://security-any.connpass.com/event/333680/)
