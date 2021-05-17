# 使用let和const取代var

单击右方的[在线代码段Url网址](http://www.pythontutor.com/live.html#code=function%20getClothing%28isCold%29%20%7B%0A%20%20if%20%28isCold%29%20%7B%0A%20%20%20%20var%20freezing%20%3D%20'Grab%20a%20jacket!'%3B%0A%20%20%7D%20else%20%7B%0A%20%20%20%20var%20hot%20%3D%20'It%E2%80%99s%20a%20shorts%20kind%20of%20day.'%3B%0A%20%20%20%20console.log%28freezing%29%3B%0A%20%20%7D%0A%7D%0A%0AgetClothing%28false%29&cumulative=false&curInstr=5&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```javascript
function getClothing(isCold) {
  if (isCold) {
    var freezing = 'Grab a jacket!';
  } else {
    var hot = 'It’s a shorts kind of day.';
    console.log(freezing);
  }
}

getClothing(false)
```

```javascript
function getClothing(isCold) {
  if (isCold) {
    const freezing = 'Grab a jacket!';
  } else {
    const hot = 'It’s a shorts kind of day.';
    console.log(freezing);
  }
}

getClothing(false)
```

## 参考文献及资料

1. [**ES6** from Udacity.com](https://classroom.udacity.com/courses/ud356)

