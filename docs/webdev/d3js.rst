========================================
D3JS
========================================
.. highlight:: html

Setting
-----------
`d3js <http://ja.d3js.node.ws>`_ の読み込み::

  <script src="http://d3js.org/d3.v3.min.js" charset="utf-8"></script>

Tips
-----------

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
