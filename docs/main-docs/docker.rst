========================================
Docker
========================================
.. highlight:: bash

Docker使い方メモ
==================

基本コメンド::

  $ docker images
  $ docker run --name NAME -i -t (-d)\ # -d:バックグラウンド実行
      -v HOST-DIR:CONTAINER-DIR \
      -p HOST-PORT:CONTAINER-PORT \
      IMAGE /bin/bash
  $ docker rmi IMAGE
  $ docker ps (-a)
  $ docker start CONTAINER
  $ docker stop CONTAINER
  $ docker attach CONTAINER #バックグラウンド実行のコンテナに接続
  $ docker rm CONTAINER

Build::

  $ mkdir mydockerbuild
  $ cd mydockerbuild
  $ touch Dockerfile
  $ atom Dockerfile
    .. FROM docker/whalesay:latest
    .. MAINTAINER Masahiro Rikiso <mshrrks@gmail.com>
    .. RUN apt-get -y update && apt-get install -y fortunes
    .. ADD ..
    .. ENV ..
    .. EXPOSE 80
    .. CMD /usr/games/fortune -a | cowsay
  $ docker build -t <image-name> .

Commit::

  $ docker commit <container-id> <image-name>

Tag & Push::

  $ docker tag <image-id> msrks/<image-name>
  $ docker login --username=msrks --email=mshrrks@gmail.com
  $ docker push msrks/<image-name>

ファイル出力::

  $ docker save IMAGE > i-name.tar
  $ docker load < i-name.tar
  $ docker export CONTAINER > c-name.tar

コンテナ内のファイルをホストにコピーする::

  $ docker cp CONTAINER:filename ./

差分::

  $ docker diff CONTAINER

お世話になってるコンテナたちの導入方法
======================================

初めて導入するとき
------------------------
`gitbucket <https://github.com/takezoe/gitbucket-docker>`_ ::

  $ docker run --name gitbucket-8001 -d -p 8001:8080 takezoe/gitbucket

tensorflow::

  $ docker run --name jupyter-8002 -d -p 8002:8888 gcr.io/tensorflow/tensorflow

caffe::

  $ docker run --name jupyter-8003 -d -t -p 8003:8888 msrks/caffe-demo \
  /usr/local/bin/jupyter notebook --notebook-dir=/opt/caffe/examples/ --ip=0.0.0.0

caffe-webdemo::

  $ docker run --name webdemo-8004 -d -t -p 8004:5000 msrks/caffe-demo \
  /usr/bin/python /opt/caffe/examples/web_demo/app.py

２回目以降
------------
コンテナ名を確かめる::

  $ docker ps -a

コンテナを起動する::

  $ docker start <container-id>
