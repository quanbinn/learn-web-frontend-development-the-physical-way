# 使用prototype对象实现构造函数的继承

单击右方的[在线代码段Url网址](http://www.pythontutor.com/live.html#code=class%20Car%20%7B%0A%20%20%20%20constructor%28numEngines%29%7B%0A%20%20%20%20%20%20%20%20this.numEngines%20%3D%20numEngines%3B%0A%20%20%20%20%20%20%20%20this.enginesActive%20%3D%20false%3B%20%20%20%20%20%20%20%20%0A%20%20%20%20%7D%0A%0A%20%20%20%20startEngines%28%29%20%7B%0A%20%20%20%20%20%20%20%20console.log%28'starting%20engines%20...'%29%3B%0A%20%20%20%20%20%20%20%20this.enginesActive%20%3D%20true%3B%0A%20%20%20%20%7D%0A%7D%0A%0Aconst%20binxiasCar%20%3D%20new%20Car%282%29%3B%0AbinxiasCar.startEngines%28%29%3B%0A%0Aconst%20yuhangxiasCar%20%3D%20new%20Car%284%29%3B%0AyuhangxiasCar.startEngines%28%29%3B%0A%0A//%20function%20Car%28numEngines%29%20%7B%0A//%20%20%20%20%20this.numEngines%20%3D%20numEngines%3B%0A//%20%20%20%20%20this.enginesActive%20%3D%20false%3B%0A//%20%7D%0A%0A//%20Car.prototype.startEngines%20%3D%20function%28%29%20%7B%0A//%20%20%20%20%20console.log%28'starting%20engines%20...'%29%3B%0A//%20%20%20%20%20this.enginesActive%20%3D%20true%3B%0A//%20%7D%3B%0A%0A//%20const%20binxiasCar%20%3D%20new%20Car%282%29%3B%0A//%20binxiasCar.startEngines%28%29%3B%0A%0A//%20const%20yuhangxiasCar%20%3D%20new%20Car%284%29%3B%0A//%20yuhangxiasCar.startEngines%28%29%3B&cumulative=false&curInstr=16&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```javascript
function Car(numEngines) {
	this.numEngines = numEngines;
	this.enginesActive = false;
}

Car.prototype.startEngines = function() {
	console.log('starting engines ...');
	this.enginesActive = true;
};

const binxiasCar = new Car(2);
binxiasCar.startEngines();

const yuhangxiasCar = new Car(4);
yuhangxiasCar.startEngines();
```

单击右方的[在线代码段Url网址](http://www.pythontutor.com/live.html#code=function%20Animal%20%28name%29%20%7B%0A%20%20this.name%20%3D%20name%3B%0A%7D%0A%0AAnimal.prototype.walk%20%3D%20function%20%28%29%20%7B%0A%20%20console.log%28%60%24%7Bthis.name%7D%20walks!%60%29%3B%0A%7D%3B%0A%0Afunction%20Cat%20%28name%29%20%7B%0A%20%20Animal.call%28this,%20name%29%3B%0A%20%20this.lives%20%3D%209%3B%0A%7D%0A%0ACat.prototype%20%3D%20Object.create%28Animal.prototype%29%3B%0A%0ACat.prototype.constructor%20%3D%20Cat%3B%0A%0ACat.prototype.meow%20%3D%20function%20%28%29%20%7B%0A%20%20console.log%28'Meow!'%29%3B%0A%7D%3B%0A%0Aconst%20bambi%20%3D%20new%20Cat%28'Bambi'%29%3B%0A%0Abambi.meow%28%29%3B%0Abambi.walk%28%29%3B%0A%0Abambi.name%3B&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```javascript
function Animal (name) {
  this.name = name;
}

Animal.prototype.walk = function () {
  console.log(`${this.name} walks!`);
};

function Cat (name) {
  Animal.call(this, name);
  this.lives = 9;
}

Cat.prototype = Object.create(Animal.prototype);

Cat.prototype.constructor = Cat;

Cat.prototype.meow = function () {
  console.log('Meow!');
};

const bambi = new Cat('Bambi');

bambi.meow();
bambi.walk();

bambi.name;
```

## 参考文献及资料

1. [**ES6** from Udacity.com](https://classroom.udacity.com/courses/ud356/lessons/3925704a-be38-4b70-8c8b-a4a812b6a309/concepts/93153a84-fbee-4200-8ec6-6a41830e419f)



