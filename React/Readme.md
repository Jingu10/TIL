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
  console.log(element); // Object 출력. 즉, element는 리액트 오브젝트이다.

  function Hello() {
    return <h1>안녕 리액트</h1>
  }
  // 리액트 컴포넌트
  // 함수 이름이 대문자로 시작하고, 반드시 jsx 문법으로 만든 리액트 오브젝트를 반환해야 한다.

  const element = {
    <>
      <Hello />
      <Hello />
      <Hello />
    </>
  }

  // element를 render 하면 안녕 리액트가 세 번 출력된다.
  ```

  
  
