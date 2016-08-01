========================================
Atom
========================================
.. highlight:: bash

Proxy環境下での設定方法

Linux
-----------
@160506::

  $ apm config set http-proxy http://<ip>:<port>
  $ apm config set https-proxy https://<ip>:<port>
  $ apm config set strict-ssl false
  $ export ATOM_NODE_URL=http://gh-contractor-zcbenz.s3.amazonaws.com/atom-shell/dist


Windows
------------
@160623::

  # 1) $HOME/.atom/下に、.apmrcファイルを作成し、環境変数を追加する
  http-proxy=http://<ip>:<port>
  https-proxy=https://<ip>:<port>
  strict-ssl=false
  # 2) 管理者権限でコマンドプロンプトを開き、以下のコマンドを実行する。
  $ setx ATOM_NODE_URL http://gh-contractor-zcbenz.s3.amazonaws.com/atom-shell/dist /M
  # 3) コマンドプロンプトからこれも打つみたい
  $ apm config set http-proxy http://<ip>:<port>
  $ apm config set https-proxy http://<ip>:<port>
  $ apm config set strict-ssl false
