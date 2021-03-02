# Redux 사용해 어플리케이션 만들기

1. Redux 사용하는 방법 2가지

   - Terminal에 `npm install —save redux` 로 redux 설치
   - 검색엔진에 `redux cdn` 을 검색해 나오는 페이지에서 url을 html script src에 입력해준다.

2. Redux 사용하는 과정(**with-redux.html**)
   1. store 생성
   2. state 생성(store만들면 자동으로 생성됨)
   3. reducer 함수를 만들고 store에 넣어준다.
      (reducer : 기존 state 값과, action값을 참조해 새로운 state를 생성하는 역할)
   4. action을 dispatch에 넣어주면 ruducer가 현재 state와 action을 이용해 새로운 state값을 생성하고, 리턴한다.
      (이때, state값을 바로 변경하는 것이 아니고 `Object.assign({},state)`을 이용해 기존 state값을 복제해 새로운 값으로 변경한다.)
   5. state값이 변경될 때마다 render함수를 호출해 UI를 변경해준다.
      (이를 위해 subscribe에 render를 등록해준다.)
