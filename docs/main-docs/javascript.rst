========================================
Javascript
========================================
.. highlight:: html

D3JS
-----
`d3js <http://ja.d3js.node.ws>`_ ::

  <script src="http://d3js.org/d3.v3.min.js" charset="utf-8"></script>

要素の追加・指定::

  select, selectAll

設定、取得::

  text, attr, style, append, remove

起動時に何かしたい
-------------------
id=classifyfileのdisabled=trueにして、id=imagefileが変わった瞬間にformをsubmitする::

  <head>
  <script type="text/javascript">
    $(document).ready(
      function(){
        $('#classifyfile').attr('disabled',true);
        $('#imagefile').change(
          function(){
            if ($(this).val()){
              $('#formupload').submit();
            }
          }
        );
      }
    );
  </script>
  </head>
  <body>
    <form id="formupload" class="form-inline" role="form" action="classify_upload" method="post" enctype="multipart/form-data">
      <div class="form-group">
        <label for="imagefile">Or upload an image:</label>
        <input type="file" name="imagefile" id="imagefile">
      </div>
      <!--<input type="submit" class="btn btn-primary" value="Classify File" id="classifyfile"></input>-->
    </form>
  </body>
