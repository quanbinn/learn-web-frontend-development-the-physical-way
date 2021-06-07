# 在render()里的html元素的class标签需要写成className

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

## 调试Sandbox项目：
单击右方的[在组合多个组件的过程中使用props传入Mock的[obj1,obj2,...objN]数据](https://codesandbox.io/s/zaizuheduogezujiandeguochengzhongchuanrumockdeobj1obj2objnshuju-sw1p2?file=/src/index.js)，浏览器里会打开一个新的页面，里面有下面的代码段，如下图所示。

### index.js
```javascript
import {Component} from 'react';
import ReactDOM from 'react-dom';

class UserList extends Component{
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

class App extends Component {
	render() {
		return (
			<div className = 'App'>
				<UserList />
				<UserList />
				<UserList />				
			</div>	
		)
	}
}

ReactDOM.render(<App />, document.getElementById('root'));
```

### 调用组件进行渲染时传入Mock的[obj1,obj2,...objN]数据
```javascript
import {Component} from 'react';
import ReactDOM from 'react-dom';

class UserList extends Component{
	render() {
		const user  = this.props.users

		return <ol>
			{user.map((userObject) => (
				<li key={userObject.name}>{userObject.name}</li>
				)
      )
		}
		</ol>
	}
}

class App extends Component {
	render() {
		return (
			<div className = 'App'>
				<UserList users={[
					{name: '夏彬'},
					{name: 'yhx'},
					{name: 'ynw'}
				]}/>
				<UserList users={[
					{name: '刘涛'},
					{name: 'sonOfLiutao'},
					{name: 'daughterOfLiutao'}
				]}/>
				<UserList users={[
					{name: '王伟'},
					{name: 'sonOfLiutao'},
					{name: 'daughterOfLiutao'}
				]}/>				
			</div>	
		)
	}
}

ReactDOM.render(<App />, document.getElementById('root'));
```

