# 在组合多个嵌套组件的过程中使用props传入Mock的[obj1,obj2,...objN]数据

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
  1: { id: 1, name: "夏宇杭", userName: "coder" },
  2: { id: 2, name: "夏彬", userName: "mpage" },
  3: { id: 3, name: "吴艳楠", userName: "user123" },
  4: { id: 3, name: "张林卓", userName: "user123" },
  5: { id: 5, name: "张勇", userName: "user123" },
  6: { id: 6, name: "夏宇乔", userName: "user123" }
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
## 参考文献及资料

1. [Components and Props](https://reactjs.org/docs/components-and-props.html)

