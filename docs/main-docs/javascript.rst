========================================
Javascript
========================================
.. highlight:: html

D3JS
-----
`d3js <http://ja.d3js.node.ws>`_ の読み込み::

  <script src="http://d3js.org/d3.v3.min.js" charset="utf-8"></script>

DOM要素の追加・指定::

  select, selectAll

設定、取得::

  text, attr, style, append, remove

データの利用::

  data, enter, exit

データ利用の例::

  <body>
    <p>1</p>
    <p>2</p>
  <script>
    var dataset = [1,2,3]
    var p = d3.select("body").selectAll("p")
    var update = p.data(dataset)
    var enter = update.enter().append(p)
    //var exit　= update.exit()
  </script>
  </body>

svgの例::

  <body>
  <script>
    var dataset = [1,2,3,4,5]
    var svg = d3.select("body").append("svg")
                .attr("width", 500)
                .attr("height", 200);
  </script>
  </body>

animation::

  transition, delay, duration, ease,
  each("start",function(){}), each("end",function(){})

event::

  on("mouseover", function(){})
  on("mouseout", function(){})
  on("mousedown", function(){})
  on("mouseup", function(){})
  on("click", function(){})

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
