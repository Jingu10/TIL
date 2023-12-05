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
* head: 페이지에 대한 정보 
* body: 페이지에 대한 내용

---

* font-family에 속성을 여러 개 지정할 경우, 가능한 것을 순차적으로 적용
* link 태그: 외부데이터를 가져오는 태그, head 태그 안에 넣는다. // 구글 폰트에서 폰트에 맞는 link 태그를 복사해 내 코드에 적용 가능
* ### margin 0 auto: 세로 마진은 0, 가로 마진은 알아서 채우라는 의미!! (가운데정렬 느낌)

---

### p, div, span 비교
* div: 그냥 구역을 나눔. block 태그라서 가로줄 전체 차지, 너비 100%
* span: 텍스트에 색칠, 크기, 좌우간격 조절, 기본적으로 inline // ex) p 태그 안에서 특정 글자만 css 적용하고 싶을 때 spand 으로 감싸기
* p: 문단을 나눌 때 사용. div랑 거의 같은데, div는 세션 나누기가 목적이고, p는 글자 표현이 목적임. <br><strong> p태그 하위에는 인라인 요소만 올 수 있다!! (p는 div를 포함할 수 없음) </strong>
* Inline-level Element : 자기의 고유 영역이 없이 그저 자신이 둘러싸고 있는 내용들의 양에 따라 길이가 결정되어 지는 태그들
* 대표적인 inline 태그: a, img, input, span, textarea