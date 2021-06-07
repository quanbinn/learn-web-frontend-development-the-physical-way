# User interact后调用组件的setState()改变组件的初始state

## 调试Sandbox项目：
单击右方的[User-interact后调用组件的setState()改变组件的初始state](https://codesandbox.io/s/user-inputhoudiaoyongzujiandesetstategaibianzujiandechushistate-qknid)，浏览器里会打开一个新的页面，里面有下面的代码段，如下图所示。

### index.js
```javascript
import { Component } from 'react';
import ReactDOM from "react-dom";
import Score from './Score';
import Game from './Game';

class App extends Component {
  state = {
    correctAnswer: 0,
    numQuestions: 0,
  };

  handleAnswer = answerWasCorrect => {
    if (answerWasCorrect) {
      this.setState(currState => ({
        correctAnswer: currState.correctAnswer + 1,
      }));
    }
    this.setState(currState => ({
      numQuestions: currState.numQuestions + 1,
    }));
  };

  render() {
    return (
      <div className="App">
        <div className="game">
          <h2>Mental Math</h2>
          <Game handleAnswer={this.handleAnswer} />
          <Score numCorrect={this.state.correctAnswer} numQuestions={this.state.numQuestions} />
        </div>
      </div>
    );
  }
}

ReactDOM.render(<App />, document.getElementById("root"));
```

### Game.js
```javascript
import { Component } from 'react';

class Game extends Component {

  constructor(props) {
    super(props);
    const valuesArray = this.makeNewQuestion();
    this.state = {
      value1: valuesArray[0],
      value2: valuesArray[1],
      value3: valuesArray[2],
      proposedAnswer: valuesArray[3],
    };
  }

  makeNewQuestion = () => {
    const value1 = Math.floor(Math.random() * 100);
    const value2 = Math.floor(Math.random() * 100);
    const value3 = Math.floor(Math.random() * 100);
    const proposedAnswer = Math.floor(Math.random() * 3) + (value1 + value2 + value3);
    return [value1, value2, value3, proposedAnswer];
  };

  updateState = newValuesArray => {
    this.setState(currState => ({
      value1: newValuesArray[0],
      value2: newValuesArray[1],
      value3: newValuesArray[2],
      proposedAnswer: newValuesArray[3],
    }));
  };

  handleAnswer = event => {
    const newValuesArray = this.makeNewQuestion();
    this.updateState(newValuesArray);
    const answerWasCorrect = this.evaluateAnswer(event.target.name);
    this.props.handleAnswer(answerWasCorrect);
  };

  evaluateAnswer(givenAnswer) {
    const { value1, value2, value3, proposedAnswer } = this.state;
    const corrAnswer = value1 + value2 + value3;

    return (
      (corrAnswer === proposedAnswer && givenAnswer === 'true') ||
      (corrAnswer !== proposedAnswer && givenAnswer === 'false')
    );
  }

  render() {
    const { value1, value2, value3, proposedAnswer } = this.state;
    return (
      // without this '(', JS will automatically put a ';' after 'return.'
      <div>
        <div className="equation">
          <p className="text">{`${value1} + ${value2} + ${value3} = ${proposedAnswer}`}</p>
        </div>
        <button onClick={this.handleAnswer} name="true">
          True
        </button>
        <button name="false" onClick={this.handleAnswer}>
          False
        </button>
      </div>
    );
  }
}

export default Game;
```

### Score.js
```javascript
const Score = props => {
  return (
    <p className="text">
      Your Score: {props.numCorrect}/{props.numQuestions}
    </p>
  );
};

export default Score;
```

## 参考文献及资料

1. [Components and Props](https://reactjs.org/docs/components-and-props.html)

