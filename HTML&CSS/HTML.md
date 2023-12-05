```html
<!DOCTYPE html>
<html>
    <head>
        <title>Weekly Codeit</title>
        <meta charset="utf-8">
    </head>
    <body>
        안녕 HTML!
    </body>
</html>
```

* title: 홈페이지 제목
* head: 페이지에 대한 정보. 웹 브라우저가 읽어서 처리하는 용도.
* body: 페이지에 대한 내용

---


### p, div, span 비교
* div: 그냥 구역을 나눔. block 태그라서 가로줄 전체 차지, 너비 100%
* span: 텍스트에 색칠, 크기, 좌우간격 조절, 기본적으로 inline // ex) p 태그 안에서 특정 글자만 css 적용하고 싶을 때 spand 으로 감싸기
* p: 문단을 나눌 때 사용. div랑 거의 같은데, div는 세션 나누기가 목적이고, p는 글자 표현이 목적임. <br><strong> p태그 하위에는 인라인 요소만 올 수 있다!! (p는 div를 포함할 수 없음) </strong>
* Inline-level Element : 자기의 고유 영역이 없이 그저 자신이 둘러싸고 있는 내용들의 양에 따라 길이가 결정되어 지는 태그들
* 대표적인 inline 태그: a, img, input, span, textarea
---
### URI 플래그먼트
    * 페이지의 특정 부분을 가리키는 주소
    * 원하는 곳에 id 속성을 지정해 두고, 링크 주소로 사용할 때는 #id
```
팀 버너스리는 "인터넷 사용 자체가 인권"<a href="#note-1">[1]</a>이라고 말했다. 
// [1]을 누르면 id가 note-1인 부분으로 이동하게 된다..!
...

<p id="note-1">[1] 서울디지털포럼 2013 기조연설</p>
```
---
### 알아두면 좋은 태그 정리 
  * em태그: <em>강조</em>
  * s태그: <s>취소</s>
  * pre태그: html에 적혀있는 그대로 보여주는 태그. 코드를 보여줄 때 사용.
---
### 인풋, 폼
[form 태그 정리](https://inpa.tistory.com/entry/HTML-%F0%9F%93%9A-%ED%8F%BCForm-%ED%83%9C%EA%B7%B8-%EC%A0%95%EB%A6%AC)
* label 태그로 input 태그를 감싸면 라벨을 클릭했을 때 인풋에 포커싱이 된다.
* label의 for 속성과 input이 id 속성을 일치시키면 라벨을 클릭했을 때 인풋에 포커싱이 된다.
* input의 name 속성은 전송했을 때 입력한 값에 매칭되는 이름이다. (?name값=입력값)
* button의 type 속성의 기본값은 submit 이고, reset값도 줄 수 있다. (reset이면 form에 작성한 내용을 모두 초기화)
* type="checkbox" // input 태그에 value 속성으로 값을 지정해 줄 경우, 선택된 항목의 지정된 값이 쓰인다. 
```
<label for="film">좋아하는 영화 장르</label>
<label>
  <input type="checkbox" name="film" value="action">
  액션
</label>
<label>
  <input type="checkbox" name="film" value="comedy">
  코미디
</label>
<label>
  <input type="checkbox" name="film" value="romance">
  로맨스
</label>

액션과 코디미를 선택하고, 폼을 전송했을 때 쿼리 문자열에서는 "&film=action&film=comedy"처럼 전송
```

* type="radio" // 동그란 선택 버튼. 여러 개 중 하나만 선택 가능.
```
<input id="very-bad" name="feeling" value="0" type="radio">
<label for="very-bad">아주 나쁨</label>
<input id="bad" name="feeling" value="1" type="radio">
<label for="bad">나쁨</label>
<input id="soso" name="feeling" value="2" type="radio">
<label for="soso">보통</label>
<input id="good" name="feeling" value="3" type="radio">
<label for="good">좋음</label>
<input id="very-good" name="feeling" value="4" type="radio">
<label for="very-good">아주 좋음</label>

value 속성과 같이 사용하면, 같은 name을 가진 <input> 태그들 중에, 선택한 <input>의 value 값을 입력하도록 할 수 있다.
예를 들어서 아래 코드에서 "좋음"을 선택하면 feeling의 값으로 3이라는 값이 들어간다.
```

* type="range" : 범위 안에서 선택 가능
* select 태그 : 미리 정해져 있는 여러 값들 중 하나를 선택 가능. (드롭다운)
```
select 태그 안에 option 태그를 value와 함께 사용.
ex) 드라마를 선택하면, genre의 값이 drama가 된다.


<label for="genre">장르</label>
<select id="genre" name="genre">
  <option value="korean">한국 영화</option>
  <option value="foreign">외국 영화</option>
  <option value="drama">드라마</option>
  <option value="documentary">다큐멘터리</option>
  <option value="vareity">예능</option>
</select>
```

* 반드시 입력해야 하는 값 required
    * required인 인풋의 값이 비어있다면, 전송 버튼을 눌러도 전송되지 않는다.
    * \<input name="email" type="email" required\>
* autocomplete 속성: 인풋창 눌렀을 때 예전에 입력한 값들을 보여주는 속성 (자동완성)
    * ex) \<input name="email" type="text" autocomplete="on"\>
    * on이라는 값을 지정해주어야 작동한다.
    * type이 email이라면 autocomplete="email" 이런식으로도 쓸 수 있다.

