# 使用ES6的class语法糖创建对象

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

```javascript
class Car {
	constructor(numEngines){
		this.numEngines = numEngines;
		this.enginesActive = false;		
	}

	startEngines() {
		console.log('starting engines ...');
		this.enginesActive = true;
	}
}

const binxiasCar = new Car(2);
binxiasCar.startEngines();

const yuhangxiasCar = new Car(4);
yuhangxiasCar.startEngines();
```

## 参考文献及资料

1. [**ES6** from Udacity.com](https://classroom.udacity.com/courses/ud356/lessons/3925704a-be38-4b70-8c8b-a4a812b6a309/concepts/93153a84-fbee-4200-8ec6-6a41830e419f)



