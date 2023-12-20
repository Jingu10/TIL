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
  
  
