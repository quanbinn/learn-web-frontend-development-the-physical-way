# 在Chrome控制台里查看JSX语法被编译后生成的DOM元素

## 下载并打开实验文件
找到下载的[**“\react-demos\demo03\”**](https://github.com/ruanyf/react-demos)文件夹中的index.html，右键选择用Google Chrome浏览器打开，随后在控制台里会找到相应的代码段，如下图所示。

![](/images/React/在Chrome控制台里查看JSX语法被编译后生成的DOM元素/1.png)

![](/images/React/在Chrome控制台里查看JSX语法被编译后生成的DOM元素/2.png)

![](/images/React/在Chrome控制台里查看JSX语法被编译后生成的DOM元素/3.png)

![](/images/React/在Chrome控制台里查看JSX语法被编译后生成的DOM元素/4.png)

### index.html
```javascript
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <script src="../build/react.development.js"></script>
    <script src="../build/react-dom.development.js"></script>
    <script src="../build/babel.min.js"></script>
  </head>
  <body>
    <div id="example"></div>
    <script type="text/babel">
      var arr = [
        <h1 key="1">Hello world!</h1>,
        <h2 key="2">React is awesome</h2>,
      ];
      ReactDOM.render(
        <div>{arr}</div>,
        document.getElementById('example')
      );
    </script>
  </body>
</html>
```

### JSX语法被编译后的javascript代码
```javascript
<script>"use strict";

var arr = [React.createElement(
  "h1",
  { key: "1" },
  "Hello world!"
), React.createElement(
  "h2",
  { key: "2" },
  "React is awesome"
)];
ReactDOM.render(React.createElement(
  "div",
  null,
  arr
), document.getElementById('example'));
//# sourceMappingURL=data:application/json;base64,eyJ2ZXJzaW9uIjozLCJzb3VyY2VzIjpbIklubGluZSBCYWJlbCBzY3JpcHQiXSwibmFtZXMiOlsiYXJyIiwiUmVhY3RET00iLCJyZW5kZXIiLCJkb2N1bWVudCIsImdldEVsZW1lbnRCeUlkIl0sIm1hcHBpbmdzIjoiOztBQUNNLElBQUlBLE1BQU0sQ0FDUjtBQUFBO0FBQUEsSUFBSSxLQUFJLEdBQVI7QUFBQTtBQUFBLENBRFEsRUFFUjtBQUFBO0FBQUEsSUFBSSxLQUFJLEdBQVI7QUFBQTtBQUFBLENBRlEsQ0FBVjtBQUlBQyxTQUFTQyxNQUFULENBQ0U7QUFBQTtBQUFBO0FBQU1GO0FBQU4sQ0FERixFQUVFRyxTQUFTQyxjQUFULENBQXdCLFNBQXhCLENBRkYiLCJmaWxlIjoiSW5saW5lIEJhYmVsIHNjcmlwdCIsInNvdXJjZXNDb250ZW50IjpbIlxuICAgICAgdmFyIGFyciA9IFtcbiAgICAgICAgPGgxIGtleT1cIjFcIj5IZWxsbyB3b3JsZCE8L2gxPixcbiAgICAgICAgPGgyIGtleT1cIjJcIj5SZWFjdCBpcyBhd2Vzb21lPC9oMj4sXG4gICAgICBdO1xuICAgICAgUmVhY3RET00ucmVuZGVyKFxuICAgICAgICA8ZGl2PnthcnJ9PC9kaXY+LFxuICAgICAgICBkb2N1bWVudC5nZXRFbGVtZW50QnlJZCgnZXhhbXBsZScpXG4gICAgICApO1xuICAgICJdfQ==
</script>
```

## Reference

1. [React 入门实例教程 - 阮一峰的网络日志](https://ruanyifeng.com/blog/2015/03/react.html) 