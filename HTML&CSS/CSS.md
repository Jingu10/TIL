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
