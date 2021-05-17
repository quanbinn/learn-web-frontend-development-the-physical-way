# 使用Template Literals制作多行字符串

单击右方的[在线代码段Url网址](http://www.pythontutor.com/live.html#code=const%20student%20%3D%20%7B%0A%20%20name%3A%20'Richard%20Kalehoff',%0A%20%20guardian%3A%20'Mr.%20Kalehoff'%0A%7D%3B%0A%0Aconst%20teacher%20%3D%20%7B%0A%20%20name%3A%20'Mrs.%20Wilson',%0A%20%20room%3A%20'N231'%0A%7D%0A%0Alet%20note%20%3D%20teacher.name%20%2B%20',%5Cn%5Cn'%20%2B%0A%20%20'Please%20excuse%20'%20%2B%20student.name%20%2B%20'.%5Cn'%20%2B%0A%20%20'He%20is%20recovering%20from%20the%20flu.%5Cn%5Cn'%20%2B%0A%20%20'Thank%20you,%5Cn'%20%2B%0A%20%20student.guardian%3B%0A%0A//%20let%20note%20%3D%20%60%24%7Bteacher.name%7D,%0A%0A//%20%20%20Please%20excuse%20%24%7Bstudent.name%7D.%0A//%20%20%20He%20is%20recovering%20from%20the%20flu.%0A%20%20%0A//%20%20%20Thank%20you,%0A//%20%20%20%24%7Bstudent.guardian%7D%60%3B%0A%20%20%0Aconsole.log%28note%29%3B&cumulative=false&curInstr=4&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```javascript
const student = {
  name: 'Richard Kalehoff',
  guardian: 'Mr. Kalehoff'
};

const teacher = {
  name: 'Mrs. Wilson',
  room: 'N231'
}

let note = teacher.name + ',\n\n' +
  'Please excuse ' + student.name + '.\n' +
  'He is recovering from the flu.\n\n' +
  'Thank you,\n' +
  student.guardian;

// let note = `${teacher.name},

//   Please excuse ${student.name}.
//   He is recovering from the flu.
  
//   Thank you,
//   ${student.guardian}`;
  
console.log(note);
```

## 参考文献及资料

1. [**ES6** from Udacity.com](https://classroom.udacity.com/courses/ud356)

