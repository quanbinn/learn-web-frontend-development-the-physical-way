# 渲染出Mock的[obj1,obj2,...objN]数据

## 调试Sandbox项目：
单击右方的[React渲染出Mock的[obj1,obj2,...objN]数据](https://codesandbox.io/s/reactxuanranchumockdeobj1obj2objnshuju-u25iu)，浏览器里会打开一个新的页面，里面有下面的代码段，如下图所示。

### index.js
```javascript
import React from 'react'
import ReactDOM from 'react-dom'

const user = [
	{name: '夏彬'},
	{name: 'yhx'},
	{name: 'ynw'}
]

const element = React.createElement('ol', null, 
	user.map((userObject) => (
		 	React.createElement('li', {key: userObject.name}, userObject.name)
		)
	)
)

console.log(element)

ReactDOM.render(
	element,
	document.getElementById('root')
)
```

### 使用Javascript XML语法改写上面的Sandbox里面的index.js
```javascript
import React from 'react'
import ReactDOM from 'react-dom'

const user = [
	{name: '夏彬'},
	{name: 'yhx'},
	{name: 'ynw'}
]

const element = <ol>
	{user.map((userObject) => (
			<li key={userObject.name}>{userObject.name}</li>
		)
      )
	}
</ol>

/*
const element = (<ol>
	{user.map((userObject) => (
			<li key={userObject.name}>{userObject.name}</li>
		)
      )
	}
</ol>)
*/

console.log(element)

ReactDOM.render(
	element,
	document.getElementById('root')
)
```

### 继续使用Javascript XML语法改写上面的Sandbox里面的index.js
```javascript
import React from 'react'
import ReactDOM from 'react-dom'

class UserList extends React.Component{
	render() {
		const user = [
			{name: '夏彬'},
			{name: 'yhx'},
			{name: 'ynw'}
		]

		return <ol>
			{user.map((userObject) => (
				<li key={userObject.name}>{userObject.name}</li>
				)
      		)
		}
		</ol>
	}
}

ReactDOM.render(
	<UserList />,
	document.getElementById('root')
)
```

## 参考文献及资料

1. 维基百科
	- [React (JavaScript library):JSX](https://en.wikipedia.org/wiki/React_(JavaScript_library)#JSX)
2. [JSX 简介](https://react.docschina.org/docs/introducing-jsx.html)
3. [Introducing JSX](https://reactjs.org/docs/introducing-jsx.html)

