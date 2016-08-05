========================================
Read the Docs
========================================
.. highlight:: bash

開発手順
----------
githubからrepoをclone::

  $ git clone <github.repo>
  $ cd <project>

build-dirは無視したい::

  $ touch .gitignore
  $ echo docs/_build > .gitignore

docを作る::

  $ mkdir docs
  $ cd docs
  $ sphinx-quickstart

conf.pyを修正::

  # default の綴り間違いに注意・・お恥ずかしい・・
  html_theme = "default" に修正

githubにpush::

  $ cd ..
  $ git add -A
  $ git commit -m "[add] docs"
  $ git push

`Read the Docs <https://readthedocs.org>`_ に登録して、<project>をimportしてbuild。
