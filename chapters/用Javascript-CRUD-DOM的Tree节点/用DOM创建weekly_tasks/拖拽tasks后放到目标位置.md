# 拖拽tasks后放到目标位置

## 打开实验文件

单击右方的[drag and drop - 把div拖放到另一个div中](https://codepen.io/quanbinn/pen/mdWYKgz), 浏览器里会打开一个新的页面，里面有下面的两段代码段，如下图所示。

```html
<div id="div1" ondrop="drop(event)" ondragover="allowDrop(event)"></div>
<div id="drag1" draggable="true" ondragstart="drag(event)">
  <p>攀绳+引体向上</p>
</div>
```

```javascript
function allowDrop(ev) {
  ev.preventDefault();
}

function drag(ev) {
  ev.dataTransfer.setData("Text", ev.target.id);
}

function drop(ev) {
  var data = ev.dataTransfer.getData("Text");
  ev.target.appendChild(document.getElementById(data));
  ev.preventDefault();
}
```

```CSS
#div1 {width:350px;height:70px;border:1px solid #aaaaaa;}

#drag1 {width:120px;height:50px;border:1px solid #aaaaaa;}
```

单击右方的[drag and drop - 把 div拖放到table的data cell中](https://codepen.io/quanbinn/pen/eYvwJdj), 浏览器里会打开一个新的页面，里面有下面的两段代码段，如下图所示。

```html
<table>
	<tr>
		<th>时间段</th>
		<th>锻炼内容</th>
	</tr>
	<tr>
		<td>星期1下午3:00-4:00</td>
    <td id="td1" ondrop="drop(event)" ondragover="allowDrop(event)"></td>
	</tr>
</table>

<div id="drag1" draggable="true" ondragstart="drag(event)">
  <p>攀绳+引体向上</p>
</div>

<div id="drag2" draggable="true" ondragstart="drag(event)">
  <p>手持哑铃片</p>
</div>
```

```javascript
function allowDrop(ev) {
  ev.preventDefault();
}

function drag(ev) {
  ev.dataTransfer.setData("Text", ev.target.id);
}

function drop(ev) {
  var data = ev.dataTransfer.getData("Text");
  ev.target.appendChild(document.getElementById(data));
  ev.preventDefault();
}
```

```CSS
#div1 {width:350px;height:70px;border:1px solid #aaaaaa;}

#td1 {
  width:200px;height:150px;border:1px solid red;}

#drag1, #drag2 {width:120px;height:50px;border:1px solid #aaaaaa;}
```


## 参考文献及资料

1. [**HTML draggable Attribute** from w3schools.com](https://www.w3schools.com/TAGS/att_draggable.asp)
2. [**HTML Drag and Drop API** from w3schools.com](https://www.w3schools.com/HTML/html5_draganddrop.asp)
3. [**How TO - Create a Draggable HTML Element** from w3schools.com](https://www.w3schools.com/howto/howto_js_draggable.asp)
2. [HTML Drag and Drop API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API) 
2. [HTML5原生拖拽/拖放(drag & drop)详解](https://www.cnblogs.com/weiqinl/p/7886049.html) 

