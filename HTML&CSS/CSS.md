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
  background-image: url('pizza.png'); 
  background-repeat: no-repeat; // 배경이미지는 반복해서 나타나는 것이 기본 설정. 반복되지 않도록 바꾸기
  background-position: center;
  background-size: cover; // 꽉 차게 나타나도록 설정
```

---



