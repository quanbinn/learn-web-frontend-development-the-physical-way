# 使用super和extends的语法糖实现构造函数的继承

单击右方的[在线代码段Url网址](http://www.pythontutor.com/live.html#code=class%20Tree%20%7B%0A%20%20constructor%28size%20%3D%20'10',%20leaves%20%3D%20%7Bspring%3A%20'green',%20summer%3A%20'green',%20fall%3A%20'orange',%20winter%3A%20null%7D%29%20%7B%0A%20%20%20%20this.size%20%3D%20size%3B%0A%20%20%20%20this.leaves%20%3D%20leaves%3B%0A%20%20%20%20this.leafColor%20%3D%20null%3B%0A%20%20%7D%0A%0A%20%20changeSeason%28season%29%20%7B%0A%20%20%20%20this.leafColor%20%3D%20this.leaves%5Bseason%5D%3B%0A%20%20%20%20if%20%28season%20%3D%3D%3D%20'spring'%29%20%7B%0A%20%20%20%20%20%20this.size%20%2B%3D%201%3B%0A%20%20%20%20%7D%0A%20%20%7D%0A%7D%0A%0Aclass%20Maple%20extends%20Tree%20%7B%0A%20%20constructor%28syrupQty%20%3D%2015,%20size,%20leaves%29%20%7B%0A%20%20%20%20super%28size,%20leaves%29%3B%0A%20%20%20%20this.syrupQty%20%3D%20syrupQty%3B%0A%20%20%7D%0A%0A%20%20changeSeason%28season%29%20%7B%0A%20%20%20%20super.changeSeason%28season%29%3B%0A%20%20%20%20if%20%28season%20%3D%3D%3D%20'spring'%29%20%7B%0A%20%20%20%20%20%20this.syrupQty%20%2B%3D%201%3B%0A%20%20%20%20%7D%0A%20%20%7D%0A%0A%20%20gatherSyrup%28%29%20%7B%0A%20%20%20%20this.syrupQty%20-%3D%203%3B%0A%20%20%7D%0A%7D%0A%0Aconst%20myMaple%20%3D%20new%20Maple%2815,%205%29%3B%0AmyMaple.changeSeason%28'fall'%29%3B%0AmyMaple.gatherSyrup%28%29%3B%0AmyMaple.changeSeason%28'spring'%29%3B&cumulative=false&curInstr=27&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```javascript
class Tree {
  constructor(size = '10', leaves = {spring: 'green', summer: 'green', fall: 'orange', winter: null}) {
    this.size = size;
    this.leaves = leaves;
    this.leafColor = null;
  }

  changeSeason(season) {
    this.leafColor = this.leaves[season];
    if (season === 'spring') {
      this.size += 1;
    }
  }
}

class Maple extends Tree {
  constructor(syrupQty = 15, size, leaves) {
    super(size, leaves);
    this.syrupQty = syrupQty;
  }

  changeSeason(season) {
    super.changeSeason(season);
    if (season === 'spring') {
      this.syrupQty += 1;
    }
  }

  gatherSyrup() {
    this.syrupQty -= 3;
  }
}

const myMaple = new Maple(15, 5);
myMaple.changeSeason('fall');
myMaple.gatherSyrup();
myMaple.changeSeason('spring');
```

单击右方的[在线代码段Url网址](http://www.pythontutor.com/live.html#code=function%20Tree%28size,%20leaves%29%20%7B%0A%20%20this.size%20%3D%20size%20%7C%7C%2010%3B%0A%20%20this.leaves%20%3D%20leaves%20%7C%7C%20%7Bspring%3A%20'green',%20summer%3A%20'green',%20fall%3A%20'orange',%20winter%3A%20null%7D%3B%0A%20%20this.leafColor%20%3D%20null%3B%0A%7D%0A%0ATree.prototype.changeSeason%20%3D%20function%28season%29%20%7B%0A%20%20this.leafColor%20%3D%20this.leaves%5Bseason%5D%3B%0A%20%20if%20%28season%20%3D%3D%3D%20'spring'%29%20%7B%0A%20%20%20%20this.size%20%2B%3D%201%3B%0A%20%20%7D%20%0A%7D%3B%0A%0Afunction%20Maple%28syrupQty,%20size,%20barkColor,%20leaves%29%20%7B%0A%20%20Tree.call%28this,%20size,%20barkColor,%20leaves%29%3B%0A%20%20this.syrupQty%20%3D%20%28typeof%20syrupQty%20!%3D%3D%20'undefined'%29%3B%0A%7D%0A%0AMaple.prototype%20%3D%20Object.create%28Tree.prototype%29%3B%0AMaple.prototype.constructor%20%3D%20Maple%3B%0A%0AMaple.prototype.changeSeason%20%3D%20function%20%28season%29%20%7B%0A%20%20Tree.prototype.changeSeason.call%28this,%20season%29%3B%0A%20%20if%20%28season%20%3D%3D%3D%20'spring'%29%7B%0A%20%20%20%20this.syrupQty%20%2B%3D%201%3B%0A%20%20%7D%0A%7D%3B%0A%0AMaple.prototype.gatherSyrup%20%3D%20function%20%28%29%20%7B%0A%20%20this.syrupQty%20-%3D3%3B%0A%7D%3B%0A%0Avar%20myMaple%20%3D%20new%20Maple%2815,%205%29%3B%0Aconsole.log%28myMaple%29%3B%0A%0AmyMaple.changeSeason%28'fall'%29%3B%0Aconsole.log%28myMaple%29%3B%0A%0AmyMaple.gatherSyrup%28%29%3B&cumulative=false&curInstr=25&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```javascript
function Tree(size, leaves) {
  this.size = size || 10;
  this.leaves = leaves || {spring: 'green', summer: 'green', fall: 'orange', winter: null};
  this.leafColor = null;
}

Tree.prototype.changeSeason = function(season) {
  this.leafColor = this.leaves[season];
  if (season === 'spring') {
    this.size += 1;
  } 
};

function Maple(syrupQty, size, barkColor, leaves) {
  Tree.call(this, size, barkColor, leaves);
  this.syrupQty = (typeof syrupQty !== 'undefined');
}

Maple.prototype = Object.create(Tree.prototype);
Maple.prototype.constructor = Maple;

Maple.prototype.changeSeason = function (season) {
  Tree.prototype.changeSeason.call(this, season);
  if (season === 'spring'){
    this.syrupQty += 1;
  }
};

Maple.prototype.gatherSyrup = function () {
  this.syrupQty -=3;
};

var myMaple = new Maple(15, 5);
console.log(myMaple);

myMaple.changeSeason('fall');
console.log(myMaple);

myMaple.gatherSyrup();
```

## 参考文献及资料

1. [Super and Extends from **ES6** of Udacity.com](https://classroom.udacity.com/courses/ud356/lessons/3925704a-be38-4b70-8c8b-a4a812b6a309/concepts/6b91f1d9-e0e0-43b7-815f-1a9a47b78a1d)
2. [Extending Classes from ES5 to ES6 from **ES6** of Udacity.com](https://classroom.udacity.com/courses/ud356/lessons/3925704a-be38-4b70-8c8b-a4a812b6a309/concepts/358ada89-6344-4eda-bdec-3ffe27918773)





