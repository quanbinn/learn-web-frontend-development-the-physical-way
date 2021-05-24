# this关键字的三种常用指向

单击右方的[在线代码段Url网址](http://www.pythontutor.com/live.html#code=function%20Cat%28name%29%20%7B%0A%20this.name%20%3D%20name%3B%0A%20this.sayName%20%3D%20function%20%28%29%20%7B%0A%20%20%20console.log%28%60Meow!%20My%20name%20is%20%24%7Bthis%7D%60%29%3B%0A%20%20%20//%20console.log%28%60Meow!%20My%20name%20is%20%24%7Bthis.name%7D%60%29%3B%0A%20%7D%3B%0A%7D%0A%0Aconst%20bailey%20%3D%20new%20Cat%28'Bailey'%29%3B%0Abailey.sayName%28%29%3B&cumulative=false&curInstr=7&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```javascript
function Cat(name) {
 this.name = name;
 this.sayName = function () {
   console.log(`Meow! My name is ${this}`);
   // console.log(`Meow! My name is ${this.name}`);
 };
}

const bailey = new Cat('Bailey');
bailey.sayName();
```

单击右方的[在线代码段Url网址](http://www.pythontutor.com/live.html#code=const%20dog%20%3D%20%7B%0A%20%20bark%3A%20function%20%28%29%20%7B%0A%20%20%20%20console.log%28'Woof!'%29%3B%0A%20%20%7D,%0A%20%20barkTwice%3A%20function%20%28%29%20%7B%0A%20%20%20%20this.bark%28%29%3B%0A%20%20%20%20this.bark%28%29%3B%0A%20%20%7D%0A%7D%3B%0A%0Adog.bark%28%29%3B%0A//%20Woof!%0A%0Adog.barkTwice%28%29%3B%0A//%20Woof!%0A//%20Woof!&cumulative=false&curInstr=12&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```javascript
const dog = {
  bark: function () {
    console.log('Woof!');
  },
  barkTwice: function () {
    this.bark();
    this.bark();
  }
};

dog.bark();
// Woof!

dog.barkTwice();
// Woof!
// Woof!
```

单击右方的[在线代码段Url网址](http://www.pythontutor.com/live.html#code=function%20funFunction%28%29%20%7B%0A%20%20return%20this%3B%0A%7D%0A%0AfunFunction%28%29%3B%0A//%20%28returns%20the%20global%20object,%20%60window%60%29&cumulative=false&curInstr=3&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```javascript
function funFunction() {
  return this;
}

funFunction();
// (returns the global object, `window`)
```

```javascript
console.log(this);
```


## 参考文献及资料

1. [**The `this` Keyword**](https://classroom.udacity.com/nanodegrees/nd032/parts/d4ff6b6c-2074-41d9-ab2a-440bf6e8c623/modules/a82d8fc9-9509-4717-b419-cd117cd6ce4a/lessons/7a95cd0f-752d-422e-b5a4-af8ddeaca0aa/concepts/b10c05b1-bf7b-48bc-83ba-8269540622ed)



