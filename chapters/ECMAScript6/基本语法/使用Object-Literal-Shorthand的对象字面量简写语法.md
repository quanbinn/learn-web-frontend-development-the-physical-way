# 使用Object-Literal-Shorthand的对象字面量简写语法

单击右方的[在线代码段Url网址](http://www.pythontutor.com/live.html#code=let%20type%20%3D%20'quartz'%3B%0Alet%20color%20%3D%20'rose'%3B%0Alet%20carat%20%3D%2021.29%3B%0A%0A//%20let%20gemstone%20%3D%20%7B%20type,%20color,%20carat%7D%0A%0Aconst%20gemstone%20%3D%20%7B%0A%20%20type%3A%20type,%0A%20%20color%3A%20color,%0A%20%20carat%3A%20carat%0A%7D%3B%0A%0Aconsole.log%28gemstone%29%3B&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```javascript
let type = 'quartz';
let color = 'rose';
let carat = 21.29;

// let gemstone = { type, color, carat}

const gemstone = {
  type: type,
  color: color,
  carat: carat
};

console.log(gemstone);
```

```javascript
let type = 'quartz';
let color = 'rose';
let carat = 21.29;

const gemstone = {
  type,
  color,
  carat,
  calculateWorth: function() {
    // will calculate worth of gemstone based on type, color, and carat
  }
};

let gemstone = {
  type,
  color,
  carat,
  calculateWorth() { ... }
};
```

## 参考文献及资料

1. [**ES6** from Udacity.com](https://classroom.udacity.com/courses/ud356/lessons/42383e89-ac6a-491a-b7d0-198851287bbe/concepts/3f34fe2c-c535-4d9d-bceb-89dcd8f50254)



