# 使用JavaScript对象创建React的元素

## 调试Sandbox项目：
单击右方的[React-render-element-onto-the-DOMNode-root](https://codesandbox.io/s/react-render-element-onto-the-domnode-root-810s1?file=/src/index.js)，浏览器里会打开一个新的页面，里面有下面的代码段，如下图所示。

### index.js
```javascript
import React from 'react'
import ReactDOM from 'react-dom'

const element = React.createElement('div',
	{className: 'welcome-message'}, '夏彬你好!')

// const element = React.createElement('ol', null, 
// 	React.createElement('li', null, 'Binxia'),
// 	React.createElement('li', null, 'Yuhangxia'),
// 	React.createElement('li', null, 'Yannanwu'),	
// )

console.log(element)

ReactDOM.render(
	element,
	document.getElementById('root')
)
```

### createElement()的参量说明和示例
```javascript
React.createElement( /* type */, /* props */, /* content */ );
```

```javascript
const element = React.createElement('div', null,
 React.createElement('strong', null, '夏彬你好!')
);
```

```javascript
const element = React.createElement('ul', null,
 React.createElement('li', null, '夏彬你好!'),
 React.createElement('li', null, '夏彬你好!'),
 React.createElement('li', null, '夏彬你好!')
);
```

### 使用Javascript XML语法改写上面的Sandbox里面的index.js
```javascript
import React from 'react'
import ReactDOM from 'react-dom'

const element = <div className='welcome-message'>夏彬你好</div>

/*
// let name = '夏彬';
// const element = <div>{name}你好</div>
*/

// JSX标签里能够包含很多子元素
/*
let name = '夏彬';
const element = <ol>
	<li>{name}你好</li>
	<li>Yuhangxia</li>
	<li>Yannanwu</li>
</ol>
*/

console.log(element)

ReactDOM.render(
	element,
	document.getElementById('root')
)
```

### createElement()和Javascript XML语法的完全等效表达
```javascript
const element = <div className='welcome-message'>夏彬你好</div>

			===

// 在html代码前后加了一对大括号，和上面的语句在编译后的效果是一样的
const element = (<div className='welcome-message'>夏彬你好</div>)　

			===

const element = React.createElement('div',
	{className: 'welcome-message'}, '夏彬你好!')
```

## 参考文献及资料

1. 维基百科
	- [React (JavaScript library):JSX](https://en.wikipedia.org/wiki/React_(JavaScript_library)#JSX)
2. [JSX 简介](https://react.docschina.org/docs/introducing-jsx.html)
3. [Introducing JSX](https://reactjs.org/docs/introducing-jsx.html)

