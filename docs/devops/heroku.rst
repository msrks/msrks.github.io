========================================
Heroku
========================================
.. highlight:: bash

resource:

* https://devcenter.heroku.com/articles/getting-started-with-python#introduction
* https://github.com/heroku/python-getting-started
* http://kennmyers.github.io/tutorial/2016/03/11/getting-flask-on-heroku.html

Basic
==================
installation

#. create account on heroku
#. download and instal heroku toolbelt
#. heroku login

deploy python app::

  $ mkdir heroku-app
  $ cd heroku-app
  $ pyenv virtualenv 2.7.10 venv
  $ pyenv local venv
  $ echo .python-version > .gitignore
  $ git init

  $ pip install gunicorn
  $ pip freeze > requirements.txt
  $ echo python-2.7.10 > runtime.txt
  $ echo web: gunicorn app:app --log-file=- > Procfile

  #$ heroku local web

  $ heroku create <app-name>
  $ heroku buildpacks:set heroku/python

  $ git add -A
  $ git commit -m "initial commit"
  $ git push heroku master
  $ heroku ps:scale web=1
  $ heroku open

log::

  $ heroku logs --tail
