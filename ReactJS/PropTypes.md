# PropTypes

- 앱이 커짐에 따라 타입 확인을 하면 많은 버그를(bug) 잡을 수 있다.
- React에서 PropTypes를 사용해 타입을 확인한다.

```jsx
import PropTypes from "prop-types";

class Greeting extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}

Greeting.propTypes = {
  name: PropTypes.string,
};
```
<br/>


1. 초기 Prop 값

```jsx
class Greeting extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}

// props의 초깃값을 정의합니다.
Greeting.defaultProps = {
  name: "Stranger",
};

// "Hello, Stranger"를 랜더링 합니다.
ReactDOM.render(<Greeting />, document.getElementById("example"));
```

- defaultProps 프로퍼티를 할당함으로써 props의 초깃값을 정의할 수 있다.

<br/>

2. 하나의 자식만 요구하기

```jsx
import PropTypes from "prop-types";

class MyComponent extends React.Component {
  render() {
    // 이것은 반드시 하나의 엘리먼트여야 합니다. 아니라면, 경고(warn)가 일어날 것입니다.
    const children = this.props.children;
    return <div>{children}</div>;
  }
}

MyComponent.propTypes = {
  children: PropTypes.element.isRequired,
};
```

- PropTypes.element를 이용하여 컴포넌트의 자식들(Children)에 단 하나의 자식(Child)만이 전달될 수 있도록 명시할 수 있다.
<br/>


3. Function Components

```jsx
import PropTypes from "prop-types";

function HelloWorldComponent({ name }) {
  return <div>Hello, {name}</div>;
}

HelloWorldComponent.propTypes = {
  name: PropTypes.string,
};

export default HelloWorldComponent;
```

- 함수형 컴포넌트에 PropTypes 지정 하는 방법이다.
