# 使用无状态函数组件的props传入Mock的[obj1,obj2,...objN]数据

## 调试Sandbox项目：
单击右方的[使用无状态函数组件的props传入Mock的[obj1,obj2,...objN]数据](https://codesandbox.io/s/shiyongwuzhuangtaihanshuzujiandepropschuanrumockdeobj1obj2objnshuju-tpt6s?file=/src/MovieCard.js)，浏览器里会打开一个新的页面，里面有下面的代码段，如下图所示。

### index.js
```javascript
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

const App = () => {
  return (
    <div>
      <h1>How Popular is Your Favorite Movie?</h1>
      <MovieCardsList profiles={profiles} movies={movies} users={users} />
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById("root"));
```

### MovieCardsList.js
```javascript
import MovieCard from "./MovieCard";

const MovieCardsList = (props) => {
  const { profiles, users, movies } = props;
  const usersByMovie = {};

  profiles.forEach((profile) => {
    const movieID = profile.favoriteMovieID;

    if (usersByMovie[movieID]) {
      usersByMovie[movieID].push(profile.userID);
    } else {
      usersByMovie[movieID] = [profile.userID];
    }
  });

  const movieCards = Object.keys(movies).map((id) => (
    <MovieCard
      key={id}
      users={users}
      usersWhoLikedMovie={usersByMovie[id]}
      movieInfo={movies[id]}
    />
  ));

  return <ul>{movieCards}</ul>;
};

export default MovieCardsList;
```

### MovieCard.js
```javascript
const MovieCard = (props) => {

  const { users, usersWhoLikedMovie, movieInfo } = props;

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
};

export default MovieCard;
```
## 参考文献及资料

1. [使用 State Hook](https://zh-hans.reactjs.org/docs/hooks-state.html)

