* 리액트 프로젝트 생성: npm init react-app <폴더이름>
* cf) npm init react-app . // 현재 위치에 리액트 프로젝트 생성
* 개발 모드 실행: npm run start
* 개발 모드 종료: Ctrl + C

---
### jsx 문법
* 여러 단어의 조합은 카멜케이스로 작성
* html 태그 안 class 속성은 className 으로 작성
* html 태그 안 for 속성은 htmlFor 으로 작성
* onblur, onfocus, onmousedown 소문자로 작성했던 것들 카멜케이스로 작성하
* jsx에서 자바스크립트 사용: {표현식} 중괄호 안에 표현식을 넣을 수 있다. // 변수를 태그 안이나, 태그 속성에서 사용 가능
* jsx는 실행될 때는 자바스크립트로 변환 돼서 실행된다.
---

* 리액트 컴포넌트
  ```
  const element = <h1>안녕 리액트</h1>;
  console.log(element); // JSX 문법으로 작성된 요소는 결과적으로 자바스크립트 객체가 된다.
  // element는 자바스크립트 객체. 이런 객체를 리액트 엘리먼트 라고 부른다.

  function Hello() {
    return <h1>안녕 리액트</h1>
  }
  // 리액트 컴포넌트
  // 함수 이름이 대문자로 시작하고, 반드시 jsx 문법으로 만든 리액트 엘리멘트를 반환해야 한다.

  const element = {
    <>
      <Hello />
      <Hello />
      <Hello />
    </>
  }

  // element를 render 하면 안녕 리액트가 세 번 출력된다.
  ```

* children
  * props에 있는 특별한 프로퍼티 (prop)
  * JSX 문법으로 컴포넌트를 작성할 때 컴포넌트를 단일 태그가 아니라 여는 태그와 닫는 태그의 형태로 작성하면, 그 안에 작성된 코드가 childern 값에 담기게 된다.
  ```
  function Button({ children }) {
    return <button>{children}</button>;
  }

  export default Button;

  ///
  
  import Button from './Button';
  import Dice from './Dice';
  
  function App() {
    return (
      <div>
        <div>
          <Button>던지기</Button> // "던지기"가 Button의 childern 값에 담기게 된다.
          <Button>처음부터</Button>
        </div>
        <Dice color="red" num={2} />
      </div>
    );
  }
  
  export default App;


  ```
  
  
* useEffect
```
  useEffect(() => {
    handleLoad(order);
  }, [order]);

// useEffect는 아규먼트로 콜백함수와 의존배열(dependency list)을 받는다.
// 리액트는 콜백함수와 의존배열을 기억해놨다가 처음 렌더링 했을 때 콜백함수를 실행하고,
// 그 이후 렌더링 부터는 의존배열 안의 값들이 바뀌었을 때만 콜백함수를 실행한다.
// 그래서, 의존배열이 비어있으면 처음 mount 할 때만 콜백 함수를 실행 (의존 배열 값이 바뀌지 않을거니까)
```


* setState의 콜백함수에 대해서
```
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  const increment = () => {
    // 이전 상태 값에 의존하여 새로운 상태를 계산
    setCount(prevCount => prevCount + 1);
    // setCount(count + 1);
  };

  return (
    <div>
      <p>{count}</p>
      <button onClick={increment}>증가</button>
    </div>
  );
}

/*
콜백 함수를 전달하는 방식: setState((prevState) => newState)
새로운 상태 값이 이전 상태 값에 의존할 때 사용
여기서 prevState는 업데이트되기 전의 상태

만약 setCount(count + 1)과 같이 직접 상태 값을 참조하여 업데이트하는 방식을 사용한다면,
여러 상태 업데이트가 배치로 처리될 때 각 업데이트가 참조하는 상태 값이 예상과 다를 수 있다.
그러나 setCount(prevCount => prevCount + 1)와 같이 콜백 함수를 사용하면,
각 업데이트는 항상 정확한 이전 상태 값을 참조하여 계산됩니다.
*/
```
