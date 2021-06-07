# 在render()里使用(...html...)返回html语句

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

## 调试Sandbox项目：
单击右方的[在组合多个嵌套组件的过程中使用props传入Mock的[obj1,obj2,...objN]数据](https://codesandbox.io/s/zaizuheduogeqiantaozujiandeguochengzhongshiyongpropschuanrumockdeobj1obj2objnshuju-tdsww?file=/public/index.html)，浏览器里会打开一个新的页面，里面有下面的代码段，如下图所示。

### index.js
```javascript
import { Component } from "react";
import ReactDOM from "react-dom";
import MovieCardsList from "./MovieCardsList";

const profiles = [
  { id: 1, userID: "1", favoriteMovieID: "1" },
  { id: 2, userID: "2", favoriteMovieID: "1" },
  { id: 3, userID: "4", favoriteMovieID: "5" },
  { id: 4, userID: "5", favoriteMovieID: "2" },
  { id: 5, userID: "3", favoriteMovieID: "5" },
  { id: 6, userID: "6", favoriteMovieID: "4" }
];

const users = {
  1: { id: 1, name: "xiayuhang", userName: "coder" },
  2: { id: 2, name: "xiabin", userName: "mpage" },
  3: { id: 3, name: "wuyannan", userName: "user123" },
  4: { id: 3, name: "zhanglinzhuo", userName: "user123" },
  5: { id: 5, name: "zhangyong", userName: "user123" },
  6: { id: 6, name: "xiayuqiao", userName: "user123" }
};

const movies = {
  1: { id: 1, name: "勇敢的心" },
  2: { id: 2, name: "阿凡达" },
  3: { id: 3, name: "霸王别姬" },
  4: { id: 4, name: "美丽心灵" },
  5: { id: 5, name: "达芬奇们" }
};

class App extends Component {
  constructor(props) {
    super(props);

    this.usersByMovie = {};

    profiles.forEach((profile) => {
      const movieID = profile.favoriteMovieID;

      if (this.usersByMovie[movieID]) {
        this.usersByMovie[movieID].push(profile.userID);
      } else {
        this.usersByMovie[movieID] = [profile.userID];
      }
    });
  }

  render() {
    console.log(this);

    return (
      <div>
        <h2>你最喜欢的电影的流行度如何?</h2>
        <MovieCardsList
          profiles={profiles}
          movies={movies}
          users={users}
          usersByMovie={this.usersByMovie}
        />
      </div>
    );
  }
}

ReactDOM.render(<App />, document.getElementById("root"));
```

### MovieCardsList.js
```javascript
import { Component } from "react";
import MovieCard from "./MovieCard";

class MovieCardsList extends Component {
  render() {
    const { users, movies, usersByMovie } = this.props;
    console.log(this);

    const movieCards = Object.keys(movies).map((id) => (
      <MovieCard
        key={id}
        users={users}
        usersWhoLikedMovie={usersByMovie[id]}
        movieInfo={movies[id]}
      />
    ));

    return <ul>{movieCards}</ul>;
  }
}

export default MovieCardsList;
```

### MovieCard.js
```javascript
import { Component } from "react";
class MovieCard extends Component {
  render() {
    const { users, usersWhoLikedMovie, movieInfo } = this.props;
    console.log(this);

    return (
      <li key={movieInfo.id}>
        <h2>{movieInfo.name}</h2>
        <h3>Liked By:</h3>

        {!usersWhoLikedMovie || usersWhoLikedMovie.length === 0 ? (
          <p>None of the current users liked this movie.</p>
        ) : (
          <ul>
            {usersWhoLikedMovie &&
              usersWhoLikedMovie.map((userId) => {
                return (
                  <li key={userId}>
                    <p>{users[userId].name}</p>
                  </li>
                );
              })}
          </ul>
        )}
      </li>
    );
  }
}
export default MovieCard;
```




