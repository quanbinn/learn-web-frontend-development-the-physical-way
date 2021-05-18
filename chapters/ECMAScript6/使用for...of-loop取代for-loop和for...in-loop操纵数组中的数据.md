# 使用for...of loop取代for loop和for...in loop操纵数组中的数据

单击右方的[在线代码段Url网址](http://www.pythontutor.com/live.html#code=const%20days%20%3D%20%5B'sunday',%20'monday',%20'tuesday',%20'wednesday',%20'thursday',%20'friday',%20'saturday'%5D%3B%0A%0Afor%20%28const%20day%20of%20days%29%20%7B%0A%20%20let%20upperDay%20%3D%20day.substring%280,1%29.toUpperCase%28%29%2Bday.substring%281%29%3B%0A%20%20console.log%28upperDay%29%3B%0A%7D%0A%0A//%20for%20%28const%20day%20of%20days%29%20%7B%0A//%20%20%20var%20upperDay%20%3D%20day.charAt%280%29.toUpperCase%28%29%20%2B%20day.slice%281%29%3B%0A//%20%20%20console.log%28upperDay%29%3B%0A//%20%7D%0A%0A/*%0Aconst%20digits%20%3D%20%5B0,%201,%202,%203,%204,%205,%206,%207,%208,%209%5D%3B%0A%0Afor%20%28const%20digit%20of%20digits%29%20%7B%0A%20%20console.log%28digit%29%3B%0A%7D%0A*/%0A%0A/*%0Aconst%20digits%20%3D%20%5B0,%201,%202,%203,%204,%205,%206,%207,%208,%209%5D%3B%0A%0Afor%20%28const%20digit%20of%20digits%29%20%7B%0A%20%20if%20%28digit%20%25%202%20%3D%3D%3D%200%29%20%7B%0A%20%20%20%20continue%3B%0A%20%20%7D%0A%20%20console.log%28digit%29%3B%0A%7D%0A*/%0A%0A/*%0AArray.prototype.decimalfy%20%3D%20function%28%29%20%7B%0A%20%20for%20%28i%20%3D%200%3B%20i%20%3C%20this.length%3B%20i%2B%2B%29%20%7B%0A%20%20%20%20this%5Bi%5D%20%3D%20this%5Bi%5D.toFixed%282%29%3B%0A%20%20%7D%0A%7D%3B%0A%0Aconst%20digits%20%3D%20%5B0,%201,%202,%203,%204,%205,%206,%207,%208,%209%5D%3B%0A%0Afor%20%28const%20digit%20of%20digits%29%20%7B%0A%20%20console.log%28digit%29%3B%0A%7D%0A*/&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```javascript
const days = ['sunday', 'monday', 'tuesday', 'wednesday', 'thursday', 'friday', 'saturday'];

for (const day of days) {
  let upperDay = day.substring(0,1).toUpperCase()+day.substring(1);
  console.log(upperDay);
}

// for (const day of days) {
//   var upperDay = day.charAt(0).toUpperCase() + day.slice(1);
//   console.log(upperDay);
// }

/*
const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (const digit of digits) {
  console.log(digit);
}
*/

/*
const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (const digit of digits) {
  if (digit % 2 === 0) {
    continue;
  }
  console.log(digit);
}
*/

/*
Array.prototype.decimalfy = function() {
  for (i = 0; i < this.length; i++) {
    this[i] = this[i].toFixed(2);
  }
};

const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (const digit of digits) {
  console.log(digit);
}
*/
```
单击右方的[在线代码段Url网址](http://www.pythontutor.com/live.html#code=const%20digits%20%3D%20%5B0,%201,%202,%203,%204,%205,%206,%207,%208,%209%5D%3B%0A%0Afor%20%28let%20i%20%3D%200%3B%20i%20%3C%20digits.length%3B%20i%2B%2B%29%20%7B%0A%20%20console.log%28digits%5Bi%5D%29%3B%0A%7D&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```javascript
const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (let i = 0; i < digits.length; i++) {
  console.log(digits[i]);
}
```

单击右方的[在线代码段Url网址](http://www.pythontutor.com/live.html#code=Array.prototype.decimalfy%20%3D%20function%28%29%20%7B%0A%20%20for%20%28let%20i%20%3D%200%3B%20i%20%3C%20this.length%3B%20i%2B%2B%29%20%7B%0A%20%20%20%20this%5Bi%5D%20%3D%20this%5Bi%5D.toFixed%282%29%3B%0A%20%20%7D%0A%7D%3B%0A%0Aconst%20digits%20%3D%20%5B0,%201,%202,%203,%204,%205,%206,%207,%208,%209%5D%3B%0A%0Afor%20%28const%20index%20in%20digits%29%20%7B%0A%20%20console.log%28digits%5Bindex%5D%29%3B%0A%7D%0A%0A/*%0Aconst%20digits%20%3D%20%5B0,%201,%202,%203,%204,%205,%206,%207,%208,%209%5D%3B%0A%0Afor%20%28const%20index%20in%20digits%29%20%7B%0A%20%20console.log%28digits%5Bindex%5D%29%3B%0A%7D%0A*/&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```javascript
Array.prototype.decimalfy = function() {
  for (let i = 0; i < this.length; i++) {
    this[i] = this[i].toFixed(2);
  }
};

const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (const index in digits) {
  console.log(digits[index]);
}

/*
const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (const index in digits) {
  console.log(digits[index]);
}
*/
```

## 参考文献及资料

1. [**ES6** from Udacity.com](https://classroom.udacity.com/courses/ud356/lessons/42383e89-ac6a-491a-b7d0-198851287bbe/concepts/f1955923-744a-4906-8f64-1ddcb34c6da2)

