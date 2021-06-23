# 创建tasks

## 打开实验文件

单击右方的[input form of weekly tasks](https://codepen.io/quanbinn/pen/dyvEvOo), 浏览器里会打开一个新的页面，里面有下面的两段代码段，如下图所示。

```html
<ul id="tasksTodo">
  <li>
  	<div>攀绳+引体向上</div>
  </li>
  <li>
  	<div>手持哑铃片</div>
  </li>  
</ul>

<div class="header">
  <input type="text" id="newTask" placeholder="输入新锻炼项目">
  <span onclick="createANewTask()" class="addTaskBtn">添加</span>
</div>
```

```javascript
function createANewTask() {
  const inputValue = document.getElementById("newTask").value;

  const li = document.createElement("li");
  const div = document.createElement("div");  

  li.appendChild(div);  
  div.appendChild(document.createTextNode(inputValue));

  if (inputValue === '') {
    alert("请输入你的新锻炼项目");
  } else {
    document.getElementById("tasksTodo").appendChild(li);
  }
  document.getElementById("newTask").value = "";
}
```

```CSS
/* Style the list items */
ul div {
  font-size: 18px;
  border: 1px solid lightgray;
  width:200px;height:30px;  
}

/* Style the header */
.header {
  color: black;
  text-align: center;
}

/* Style the input */
input {
  width: 75%;
  font-size: 20px;
}

/* Style the "Add" button */
.addTaskBtn {
  width: 25%;
  background: #d9d9d9;
  color: #555;
  text-align: center;
  font-size: 20px;
}
```

## 参考文献及资料

1. 维基百科
	- [Document Object Model](https://en.wikipedia.org/wiki/Document_Object_Modelt) 

2. [Calculate Your Body Mass Index from U.S. Department of Health & Human Services](https://www.nhlbi.nih.gov/health/educational/lose_wt/BMI/bmicalc.htm) 