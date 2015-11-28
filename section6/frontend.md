# 前端技术专题

### Ajax
XMLHttoRequest 对象

open(method, URL, async)

send(string)

```
<html>
<head>
<script type="text/javascript">
function loadXMLDoc()
{
var xmlhttp;
if (window.XMLHttpRequest)
  {// code for IE7+, Firefox, Chrome, Opera, Safari
  xmlhttp=new XMLHttpRequest();
  }
else
  {// code for IE6, IE5
  xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
  }
xmlhttp.onreadystatechange=function()
  {
  if (xmlhttp.readyState==4 && xmlhttp.status==200)
    {
    document.getElementById("myDiv").innerHTML=xmlhttp.responseText;
    }
  }
xmlhttp.open("GET","/ajax/demo_get2.asp?fname=Bill&lname=Gates",true);
xmlhttp.send();
}
</script>
</head>
<body>

<h2>AJAX</h2>
<button type="button" onclick="loadXMLDoc()">请求数据</button>
<div id="myDiv"></div>

</body>
</html>

```



当加载的 js 文件较多，且 js 文件之间依赖关系繁杂的时候，手动引入比较麻烦，因此需要模块化管理。require.js 可以实现 js 的异步加载，并管理依赖关系，可以参考[前段模块管理器简介 by 阮一峰](http://www.ruanyifeng.com/blog/2014/09/package-management.html)。但是 require.js 比较繁琐，用起来并不爽。Bwowserify.

前端包管理器

Bowe(和 npm 类似，npm 多用在后端而已).



