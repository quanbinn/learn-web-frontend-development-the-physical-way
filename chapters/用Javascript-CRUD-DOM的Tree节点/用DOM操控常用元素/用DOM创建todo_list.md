# 用DOM创建todo list

## 打开实验文件

单击右方的[todo_list_revised](https://codepen.io/quanbinn/pen/QWpzeJw), 浏览器里会打开一个新的页面，里面有下面的两段代码段，如下图所示。

```html
<div class="header">
  <h2>我的未完成任务列表</h2>
  <input type="text" id="newTask" placeholder="输入新任务">
  <span onclick="createANewTask()" class="addTaskBtn">添加</span>
</div>

<ul id="tasksTodo">
  <li>上午上班打卡</li>
  <li class="checked">下午3:00回家接hanghang</li>
</ul>
```

```javascript
// Create a "close" button and append it to each list item
const myNodelist = document.getElementsByTagName("LI");
for (let i = 0; i < myNodelist.length; i++) {
    const span = document.createElement("SPAN");
    span.appendChild(document.createTextNode("\u00D7"));
    span.className = "close";
    myNodelist[i].appendChild(span);
}

// Click on a close button to hide the current list item
var close = document.getElementsByClassName("close");
console.log(close);
for (let i = 0; i < close.length; i++) {
  close[i].onclick = function() {
    const parentNode = this.parentElement;
    parentNode.style.display = "none";
  }
}

// Add a "checked" symbol when clicking on a list item
const list = document.querySelector('ul');
console.log(list);
list.addEventListener('click', function(ev) {
  if (ev.target.tagName === 'LI') {
    ev.target.classList.toggle('checked');
  }
}, false);

// Create a new list item when clicking on the "Add" button
function createANewTask() {
  const li = document.createElement("li");
  const inputValue = document.getElementById("newTask").value;
  li.appendChild(document.createTextNode(inputValue));
  if (inputValue === '') {
    alert("请输入你的新任务");
  } else {
    document.getElementById("tasksTodo").appendChild(li);
  }
  document.getElementById("newTask").value = "";

  const span = document.createElement("SPAN");
  span.appendChild(document.createTextNode("\u00D7"));
  span.className = "close";
  li.appendChild(span);
}
```

```CSS
/* Style the list items */
ul li {
  cursor: pointer;
  position: relative;
  padding: 12px 8px 12px 40px;
  list-style-type: none;
  background: #eee;
  font-size: 18px;
  transition: all 0.2s ease 0s;
}

/* When clicked on, add a background color and strike out text */
ul li.checked {
  background: #888;
  color: #fff;
  text-decoration: line-through;
}

/* Style the close button */
.close {
  position: absolute;
  right: 0;
  top: 0;
  padding: 12px 16px 12px 16px;
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
