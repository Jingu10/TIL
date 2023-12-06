* font-family에 속성을 여러 개 지정할 경우, 가능한 것을 순차적으로 적용
* link 태그: 외부데이터를 가져오는 태그, head 태그 안에 넣는다. // 구글 폰트에서 폰트에 맞는 link 태그를 복사해 내 코드에 적용 가능
* ### margin 0 auto: 세로 마진은 0, 가로 마진은 알아서 채우라는 의미!! (가운데정렬 느낌)
* 너비가 정해져 있어야 자동으로 채울 수 있다.

---

* RGBA: RGB 표기에 불투명도(Alpha)를 추가한 것
  * 불투명도는 0~1 사이의 소수점 숫자
  * ex) rgba(255, 0, 0, 1)은 빨간색 / rgba(255, 0, 0, 0)은 흰색

* 1em: 부모 태그의 font-size
* 1rem: 최상위(html태그) 태그의 font-size

* CSS에서의 주석은 /* */ 안에 작성

---

* 띄어쓰기가 있으면 ""로 감싸라
  ```
  #with-poppins {
    font-family: Poppins, "Noto Sans KR", sans-serif;
  }
  ```
---

* 줄 높이 line-height
  * line-height는 단위 없이 쓰는 글자 크기에 상대적인 값
  * ex) font-size가 16px 이고, line-height가 1.5면 줄 높이는 24px
 
* text-decoratioin (none, underline, line-through)

---

* 배경이미지
```
  // 순서 중요!! 반투명 gradient와 이미지를 겹쳐서 이미지 위 글씨가 잘 보이도록 만들 수 있다!!!
  background-image: 
    linear-gradient(90deg, rgba(0,0,0,1) 40%, rgba(0,0,0,0)), 
    url('pizza.png');

  background-repeat: no-repeat; // 배경이미지는 반복해서 나타나는 것이 기본 설정. 반복되지 않도록 바꾸기
  background-position: center;
  background-size: cover; // 꽉 차게 나타나도록 설정
```

* 배경이미지는 여러 개 넣을 수도 있다.
* 아래처럼 이미지를 배경으로 넣으면 a.png 아래에 b.png가 깔리고, 맨 밑에는 c.png가 깔린다.
```
background-image:
  url('a.png'), /* 제일 위에 보이는 이미지 */
  url('b.png'),
  url('c.png');
```
```
background-size: cover; /* 비율 유지하면서 꽉 차게. 이미지 잘릴 수 있음 */
background-size: contain; /* 비율 유지하면서 최대한 크게. 이미지 잘리지 않음 */
background-size: 40px 30px; /* 가로 40px 세로 30px */
```

---
* [line-gradient 생성](https://cssgradient.io/)
```
 background-image: linear-gradient(#000000, #ffffff); // 기본적으로 시작 색상과 종료 색상으로 사용
 background-image:
  linear-gradient(45deg, rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.2)); // 기본 방향 각도는 180도 (위->아래) 각도를 바꾸고 싶 다면 맨 앞에 각도를 써주기, 단위는 deg


```

* box-shadow generator도 존재
* box-shadow: 10px 15px 20px 5px rgba(0, 0, 0, 0.4) // 가로 세로 흐린정도(blur) 퍼지는정도



---
* opacity 속성(=불투명도): 요소 전체를 반투명하게 하고 싶을 때 사용 (0이 투명, 1이 불투명)
* 배경색만 반투명하게 하고 싶다면? rgba
---
* ### box-sizing: border-box; // border를 기준으로 너비 설정 (기본은 content를 기준으로 설정)
* overflow: auto // 넘치면 스크롤 (scroll은 항상 스크롤)
* overflow: scroll // 넘치는 내용을 가려주고, 스크롤 해서 볼 수 있도록 설정 해준다
* overflow: scroll; white-space: no-wrap <br>// 자동 줄바꿈되는 것을 안되게 바꾼 후 넘치는 내용을 스크롤로 처리 하면 가로로 스크롤 되게 해준다

---
* [마진상쇄원리] (https://velog.io/@raram2/CSS-%EB%A7%88%EC%A7%84-%EC%83%81%EC%87%84Margin-collapsing-%EC%9B%90%EB%A6%AC-%EC%99%84%EB%B2%BD-%EC%9D%B4%ED%95%B4) // 마진상쇄는 세로로만 적용
>마진이란 콘텐츠 간의 간격이고, 간격을 벌리기 위해서는 경계를 필요로 합니다. 브라우저는 부모 박스와 첫 번째(마지막) 자식 박스 간의 경계를 그 사이에 있는 border / padding / inline 콘텐츠 유무로 판단합니다.<br><br>따라서, 부모와 첫 번째(마지막) 자식 사이에 inline 콘텐츠(텍스트 등)가 없거나, 상단(하단)에 명시적으로 padding 또는 border 값을 주지 않았다면 마진이 겹치게 됩니다. 이때, 자식 요소의 마진이 더 크든 작든 상관없이 상쇄된 마진은 부모 박스의 바깥으로만 렌더링이 됩니다. 😨
* [마진상쇄해결] (https://velog.io/@ursr0706/%EB%A7%88%EC%A7%84margin)

---
* border-radius: 9999px; // 아주 큰 값을 지정하면 알약 형태가 된다.
* inline은 너비나 높이를 지정할 수 없고 (img태그는 예외), <strong>여백(패딩, 마진)은 가로로만 가능!!</strong> 글을 쓰는 방향으로 줄넘김되면서 배치된다.
* inline-block: 배치는 inline처럼, 블록처럼 크기를 지정할 수 있다.
* float: 요소를 페이지 왼쪽이나 오른쪽에 삽화처럼 배치하고, 그 주변으로 인라인 요소들을 배치가능
---
* 선택자 붙여 쓰기: 여러 조건을 동시에 만족하는 요소를 선택하고 싶을 때 쓴다
* ex).large.title // large 클래스이면서 title 클래스인 태그 선택


### 레이아웃
* position: relative
  * 원래 있어야 할 위치를 기준으로 배치
  * 요소의 원래 자리는 그대로 차지한다
    
* position: absolute
  * 가장 가까운 포지셔닝이 된 조상요소를 기준으로 배치.
  * 포지셔닝이 됐다는 건 position 속성을 지정했다는 뜻!
  * 요소의 원래 자리를 차지하지 않는다.
  * 주의) 너비를 지정하지 않을 경우, 원래 배치에서 완전히 빠지므로 block 처럼 작동하지 않는다.
  * 내용이 있는 경우, content만큼만 크기를 가진다.
  * left, right 의 크기를 모두 지정할 경우 너비 지정 하는 것처럼 할 수도 있음.
 
* inset: 0; // 모든 방향에 대해서 위치를 0

* position: fixed
  * 브라우저 화면을 기준으로 고정된 배치
  * 요소의 원래 자리는 차지하지 않는다.
  * nav바에 fixed를 적용하고, content와 겹치지 않게 하려면 margin을 주면 된다.
 
 * position: sticky
   * static 처럼 원래 위치에 배치돼 있다가, 정해진 위치에 브라우저가 스크롤되면 그때부터 fixed처럼 고정
   * 요소의 원래 자리를 차지


* [CSS 단위](https://webclub.tistory.com/356) // 뷰포트 관련 단위 기억하자자
