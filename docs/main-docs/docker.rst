========================================
Docker
========================================
.. highlight:: bash

お世話になってるコンテナたちの導入方法

初めて導入するとき
------------------------
`gitbucket <https://github.com/takezoe/gitbucket-docker>`_ ::

  $ docker run --name gitbucket-8001 -d -p 8001:8080 takezoe/gitbucket

tensorflow::

  $ docker run --name jupyter-8002 -d -p 8002:8888 gcr.io/tensorflow/tensorflow

caffe::

  $ docker run --name jupyter-8003 -d -t -p 8003:8888 caffe-demo \
  /usr/local/bin/jupyter notebook --notebook-dir=/opt/caffe/examples/ --ip=0.0.0.0

caffe-webdemo::

  $ docker run --name webdemo-8004 -d -t -p 8004:5000 caffe-demo \
  /usr/bin/python /opt/caffe/examples/web_demo/app.py

２回目以降
------------
コンテナ名を確かめる::

  $ docker ps -a

コンテナを起動する::

  $ docker start <container-id>
