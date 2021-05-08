# 在组合多个组件的过程中使用props传入Mock的[obj1,obj2,...objN]数据

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

## 参考文献及资料

1. [Components and Props](https://reactjs.org/docs/components-and-props.html)

