# PoC等を試す、Docker環境を用意する

## 目的

最近のPoCや脆弱性のトレーニング環境は、Dockerで作られることが多い。
その為、それらを動かすDocker環境の作り方について、本研究会として標準的な方法を用意することにした。

## 概要

現時点でのUbuntuのLTS安定版である、Ubuntu 18.04 LTS Desktop版を利用する。

- 日本語版ではなく、英語版のUbuntuを使う（キーボード等は設定すれば使える）
- Desktop版を使うことで、DockerへのブラウザアクセスなどをDocker環境内で完結させることができる。
- オープンで利用でき、セキュリティ的にも問題がなく、癖が少ない、Ubuntuを利用する。
- オーケストレーションまでは不要とし、docker及びdocker-composeが動くまでとする。
- Dockerサーバのkernelが共有されるため、kernelの脆弱性については対象としない。

他のディストリビューションを利用したい場合は、各自で準備すること。
本資料の目的は、Dockerにあまり慣れていない方が標準的に簡単に準備できること、を目的とする。

- Ubuntu18.04 LTS Desktop EN
  - 2048MBのメモリ
  - 300GBのHDD
  - vCPU等は任意

## 準備するもの

- 仮想環境
  - Windows上のVirtualBoxを想定
- Ubuntu 18.04 LTS Desktop (EN)のISOファイル
  - https://ubuntu.com/download/desktop からダウンロードする
  - 2020/01/06時点では、ubuntu-18.04.3-desktop-amd64.iso 等となる
  - 32bitや他のアーキテクチャの場合は、各自で用意する
- インターネット接続環境
  - インストール後のアップデートやdockerコマンド追加等で必要

## Docker環境を用意する

### VirtualBox上に、Ubuntuを導入する

1. VirtualBoxを起動する
2. "仮想マシン作成"画面で、以下の設定をする

  - 名前を任意で入れ
  - タイプを"Linux"
  - バージョンを"Ubuntu (64bit)"
  - メモリを"2048MB"

3. UbuntuのISOファイルを使い、インストールを進める

  - 日本語版ではないので、Welcomeから"日本語"を選択する
  - 言語に合わせてキーボードタイプも決定される

4. Ubuntuの調整をする

  - "不完全な言語サポート"ダイアログが出るので、"この操作を今すぐ実行する"を選択する（アップデート/インストールが実施される）
  - Guest Additions CDでツールを入れる
    - `$ sudo apt-get install linux-headers-generic gcc make perl`
    - "デバイス""Guest Additions CDイメージの挿入"をし、実行する
    - `$ gpasswd -a (利用するユーザ)` で(利用するユーザ)が /media/sf_xxx/ にアクセスできるようにする
  - 不要なものを削除する（任意で、不要なものを削除）
    - `$ sudo apt-get remove rhythmbox thunderbird ubuntu-software cheese libreoffice-core libreoffice-common `

### UbuntuにDockerを入れる

https://docs.docker.com/install/linux/docker-ce/ubuntu/#install-using-the-repository を参照する

1. 必要なパッケージを入れる

```
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

2. pgpキーの追加

```
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

3. DockerとDockerComposeのインストール

```
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
$ sudo curl -L "https://github.com/docker/compose/releases/download/1.25.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
$ sudo chmod +x /usr/local/bin/docker-compose
```

4. 導入確認

```
$ docker -v
Docker version 19.03.5, build 633a0ea838
$ docker-compose -v
docker-compose version 1.25.0, build 0a186604
$

```

おわり。
