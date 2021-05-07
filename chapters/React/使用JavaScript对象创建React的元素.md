# 使用JavaScript对象创建React的元素

## 调试Sandbox项目：
单击右方的[React-render-element-onto-the-DOMNode-root](https://codesandbox.io/s/react-render-element-onto-the-domnode-root-810s1?file=/src/index.js)，浏览器里会打开一个新的页面，里面有下面的代码段，如下图所示。

### index.js
```javascript
import React from 'react'
import ReactDOM from 'react-dom'

const element = React.createElement('div',
	{className: 'welcome-message'}, 'hello world')

ReactDOM.render(
	element,
	document.getElementById('root')
)
```

```javascript
React.createElement( /* type */, /* props */, /* content */ );
```

```javascript
const element = React.createElement('div', null,
 React.createElement('strong', null, 'Hello world!')
);
```

## 参考文献及资料

1. 维基百科
	- [Function composition (computer science)](https://en.wikipedia.org/wiki/Function_composition_(computer_science))

