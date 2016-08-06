========================================
Bootstrap
========================================
.. highlight:: html

ひな型
-----------
::

  <!doctype html>
  <html lang="ja">
  <head>
    <meta charset="utf-8">
    <title>test</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.4/css/bootstrap.min.css" rel="stylesheet" media="screen">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.4/js/bootstrap.min.js"></script>
    <style>
      body {
        font-family: Verdana, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
      }
      h1,
      h2,
      h3 {
        font-family: Times, serif;
        line-height: 1.5em;
        border-bottom: 1px solid #ccc;
      }
    </style>
  </head>
  <body>
  </body>
  </html>

bodyのひな型
-----------------
- containerで囲む
- col-md-X で列分割(rowで囲んでおく): ``grid system``
- header は navbar

例::

  <div class="container">
    <!-- navbar -->
    <div class="row">
      <nav class="navbar navbar-default navbar-fixed-top">
      <div class="navbar-header">
        <a href="" class="navbar-brand">Home</a>
      </div>
      <ul class="nav navbar-nav">
        <li class="active"><a href="">menu1</a></li>
        <li><a href="">menu2</a></li>
        <li><a href="">menu3</a></li>
        <li><a href="">menu4</a></li>
      </ul>
      </nav>
    </div>
    <!-- content -->
    <div class="row" style="padding:60px 0 0 0">
      <div class="col-md-3" align="center">left</div>
      <div class="col-md-9" align="center">center</div>
    </div>
    <!-- footer -->
    <hr>
    <p>&copy; Masahiro Rikiso</p>
  </div>

その他
-----------------
table::

  <table class="table table-striped table-boarderd table-hover">
    <thead>
      <tr><th>ID</th><th>Score</th></tr>
    </thead>
    <tbody>
      <tr><tb>python</tb><tb>100</tb></tr>
    </tbody>
  </table>

.. note::

  class="table table-striped table-boarderd table-hover"で囲む

form::

  <form>
    <div class="form-group">
      <label class="control-label" for="email">Email</label>
      <input type="text" id="email" class="form-control" placeholder="email">
    </div>
    <div class="form-group">
      <input type="submit" value="submit" class="btn btn-primary">
    </div>
  </form>

.. note::

  class="form-group"で囲む。
  input textは "form-control"、
  input submitは "btn btn-primary"、
