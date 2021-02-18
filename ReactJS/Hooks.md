# React Hooks

- useInput

  - `input` : value change 이벤트, validation 테스트 실행

  ```jsx
  import React, { useState } from "react";
  import ReactDOM from "react-dom";

  import "./styles.css";

  const useInput = (initialValue, validation) => {
    const [value, setValue] = useState(initialValue);
    const onChange = (event) => {
      const {
        target: { value },
      } = event;
      let willUpdate = true;
      if (typeof validation === "function") {
        willUpdate = validation(value);
      }
      if (willUpdate) {
        setValue(value);
      }
    };
    return { value, onChange };
  };

  const App = () => {
    const test = (value) => !value.includes("@");
    const name = useInput("Mr. ", test);
    return (
      <div className="App">
        <h1>UseInput</h1>
        <input placeholder="name" {...name} />
      </div>
    );
  };

  const rootElement = document.getElementById("root");
  ReactDOM.render(<App />, rootElement);
  ```

- useState

  - `버튼` : 버튼 생성 후, onClick 이벤트 실행
  - content.tab에 해당하는 text를 담은 button을 map을 이용해 생성하고,
  - 버튼을 클릭했을 때 content.content의 text를 보여준다.

  ```jsx
  import React, { useState } from "react";
  import ReactDOM from "react-dom";
  import "./styles.css";

  const content = [
    {
      tab: "Section 1",
      content: "I'm the content of the Section 1",
    },
    {
      tab: "Section 2",
      content: "I'm the content of the Section 2",
    },
  ];

  const useTabs = (initialTab, allTabs) => {
    if (!allTabs || !Array.isArray(allTabs)) {
      return;
    }
    const [currentIndex, setCurrentIndex] = useState(initialTab);
    return {
      currentItem: allTabs[currentIndex],
      changeItem: setCurrentIndex,
    };
  };

  const App = () => {
    const { currentItem, changeItem } = useTabs(0, content);
    return (
      <div className="App">
        {content.map((section, index) => (
          <button onClick={() => changeItem(index)}>{section.tab}</button>
        ))}
        {currentItem.content}
      </div>
    );
  };

  const rootElement = document.getElementById("root");
  ReactDOM.render(<App />, rootElement);
  ```
