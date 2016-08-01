========================================
Local Server
========================================
.. highlight:: bash

認証なし
-----------
python2(port=8000)::

  $ python -m SimpleHTTPServer

python3(port=8000)::

  $ python -m http.server

認証あり
-----------
python2::

  $ wget https://gist.github.com/msrks/18125b9a57e69e0309c8f743c87904d6/raw/ff5a398ce7d828137869f91796446300b64c9941/server2.py
  $ python server2.py USER:PASS

python3::

  $ wget https://gist.github.com/msrks/3fe0e3287f548382f442a9c79d5f5ec9/raw/3416832d494feec0dda1b05b0190986f59878153/server3.py
  $ python server3.py USER:PASS
