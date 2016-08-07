========================================
Heroku
========================================
.. highlight:: bash

resource:

https://devcenter.heroku.com/articles/getting-started-with-python#introduction
https://github.com/heroku/python-getting-started

Basic
==================
deploy::

  $ mkdir heroku-app
  $ cd heroku-app
  $ pyenv virtualenv 2.7.10 venv
  $ pyenv local venv
  $ echo .python-version > .gitignore

  $ pip install gunicorn
  $ pip freeze > requirements.txt
  $ echo python-2.7.10 > runtime.txt
  $ echo web: gunicorn app:app --log-file=- > Procfile

  $ git init
  $ git add -A
  $ git commit -m "initial commit"

  #$ heroku local web

  $ heroku login
  $ heroku create <app-name>
  $ git push heroku master
  $ heroku ps:scale web=1
  $ heroku open

log::

  $ heroku logs --tail
