# ログ解析の初歩

# apache2のログを確認する

## apache2のログ形式

設定ファイルの `LogFormat` で設定形式を変更可能。
httpd.confのデフォルト値は以下のようになっている。

```
LogFormat "%h %l %u %t ¥"%r¥" %>s %b ¥"%{Referer}i¥" ¥"%{User-Agent}i¥"" combined
LogFormat "%h %l %u %t ¥"%r¥" %>s %b" common
```

各フォーマット文字列の意味配下の通り（抜粋）

|フォーマット | 説明|
|:-----------:|:-------:|
|%h           | リモート ホスト|
|%l           | リモート ログ名(クライアントの識別子)|
|%u           | リモート ユーザ|
|%t           | リクエストを受け付けた時刻CLFの時刻書式|
|%r           | リクエストの最初の行|
|%>s          | 最後のステータス|
|%b           | レスポンスのバイト数。HTTPヘッダは除く。CLF書式。1バイトも送られなかったときは '-' になる。 |
|%{FOOBAR}i   | サーバに送られたリクエストのFoobar: ヘッダの内容|

- `%{FOOBAR}i`
  - `%{User-Agent}i` により、User-Agentヘッダの値を取得している
  - `%{Referer}i` により、Refererヘッダの値を取得している
- `\"%r\"`
  - `"` をエスケープするために `\` を入れている。出力が `"xxx"` のようにダブルコーテーションで囲まれる。
  - 同様に Referer, User-Agentも設定されている
- `%r`
  - POSTデータの内容が記録されないことに注意
  - 機密情報がログに残るのを避けるために、デフォルトでは記録されないようだ
  - mod_dumpioを入れることで、 `errorログ` にHTTPレスポンスのヘッダとボディの内容が記録される

see also

- [Apache モジュール mod_log_config](https://httpd.apache.org/docs/2.2/ja/mod/mod_log_config.html)
- [Apache モジュール mod_dumpio](https://httpd.apache.org/docs/2.4/ja/mod/mod_dumpio.html)

## 考慮すべき内容

インターネット向けの更改サーバの場合、リモートログ/リモートユーザ はほぼ無意味になることが多い。

- `%l` 及び `%u` は `- -` になることが多い。

デフォルトでは、リクエスト全てが記録されているわけではない。

- データ量やユーザが入力した情報（機密情報）を保存しないという意図と思われる。
- 記録する場合はデータ容量の増加にも注意が必要か。
- 複数行になる場合もあるので、必要に応じて相応のツールを利用する（logstash等）

LogFormatの変更は、稼動状態のシステムへは難しい場合がある

- 既にログを何らかのツールで見ている場合、フォーマット変更に伴い改修が必要になる
- 稼働状況にも依るが、高頻度にアクセスがあるサーバではログ出力による負荷画像化する場合がある

## ログの例
### GET

`xxx.xxx.xxx.xxx - - [06/May/2019:22:30:56 +0000] "GET / HTTP/1.0" 200 19296 "-" "masscan/1.0 (https://github.com/robertdavidgraham/masscan)"`

|項目|内容|
|:---|:---|
|remote host       |xxx.xxx.xxx.xxx|
|remote log        |-|
|remote user       |-|
|datetime          |[06/May/2019:22:30:56 +0000]|
|request           |"GET / HTTP/1.0"|
|last status       |200|
|response bytes    |19296|
|HEADER: Referer   |"-"|
|HEADER: User-Agent|"masscan/1.0 (https://github.com/robertdavidgraham/masscan)"|

備考

- massscan というツールでアクセスがされたようだ
  - User-Agentにツール名があるので、行儀の良いツールではある（"1ダイノマシンから毎秒1000万パケットを送信し、6分以内にインターネット全体をスキャンする"のが行儀が良いかは別）
  - `# masscan -p80,8000-8100 10.0.0.0/8` で 80,8000-8100 ポート宛に 10.0.0.0/8 をスキャンする

### POST
`xxx.xxx.xxx.xxx - - [06/May/2019:12:20:48 +0000] "POST /xmlrpc.php HTTP/1.1" 200 593 "-" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/63.0.3239.132 Safari/537.36"`

|項目|内容|
|:---|:---|
|remote host|xxx.xxx.xxx.xxx|
|remote log|-|
|remote user|-|
|datetime|[06/May/2019:12:20:48 +0000]|
|request|"POST /xmlrpc.php HTTP/1.1"|
|last status|200|
|response bytes|593|
|HEADER: Referer|"-"|
|HEADER: User-Agent|"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/63.0.3239.132 Safari/537.36"|

備考

- 悪意のあるアクセスである
  - WordPressサイトで、APIで投稿ができる機能を悪用した攻撃として、 `xmlrpc.php` に攻撃が来る場合が多い
  - 何故悪意があると断定できるか。私のサーバで、私は `xmlrpc.php` を使った投稿はしていないから。
  - というように、「どのように利用しているか」などの情報がないと、悪意のあるアクセス化を判断しづらい場合が多い。
- POSTと対象しか、記録がない
  - 前述の通り、デフォルトでは全てが記載されるわけではない
- User-Agentは、恐らく偽装されている
  - 悪意のあるルールの場合、 `ua.random()` などで無作為に選択されていることが多い。
  - UserAgent自体は、Windows10の64bit(Windows NT 10.0; Win64; x64)上で稼働する Chrome/63の可能性が高いようだ。

# ログを見ていく