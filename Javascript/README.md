* 문자열
  * "", '' 둘다 문자열로 취급한다.
  * 문자열 끼리의 덧셈은 문자열을 이어준다.
  * 문자열 안에 작은, 큰 따음표가 있으면 역슬래시를 활용하거나, 백틱으로 감싸기
  * 템플릿문자열: 백틱으로 감싸고, ${변수 또는 return되는 함수} 를 문자열 안에 넣을 수 있다.

 
* 함수
  * function 함수이름(인자) { 함수내용 }
  * 옵셔널 파라미터<br>ex) function 함수이름(인자1, 인자2 = 3) { 함수내용 }<br>이렇게 선언하면, 인자 하나만 넣어도 인자2는 기본으로 들어간다. // 기본값 할당시엔, 인자를 주지 않았을  기본값이 사용되기도 하지만 undefined를 인자로 주어도 기본값이 할당된다.
 
* 자료형 (String, Number, Boolean)
  * false: ''(빈문자열), 0, NaN, null, undefined (빈 객체는 true)
  * null: 값이 없다는 것을 의도적으로 표현할 때 사용 
  * undefined: 값이 없다는 것을 확인하는 값 (선언하고, 값이 할당 안됐을 때)
 
* 형변환
  * \+ 연산은 피연산자에 문자열이 있다면, 다른 것들도 문자열로 바꿔서 연산
  * 그 이외에는 Number로 바꿔서 연산
  * 관계 비교 연산도 숫자로 바꿔서 계산
  * === 는 일치 비교이고, 형변환이 일어나지 않는다.
  * == 는 동등 비교이고, 숫자로 형변환이 되어 비교한다.
  * null과 undefined를 == 로 비교하면 true, ===로 비교하면 false
 
* 상수(const)
  * 대문자로 작성하고 언더바 사용
  * 선언 시 할당해야 함.
  * 그냥 변수는 let
  * 근데, 보통 코드 짤 땐 const로 짠다. (진짜 상수는 대문자표기)
 

  ```
  {
    name: '여진구', // 왼쪽은 property(속성) 이고, String이다!!
    age: 27,
  }
  ```
* 객체
  * 객체 내부에 접근하는 법은 두가지
    * 점표기법: 객체.객체속성 
    * 대괄호표기법: 객체[객체속성] // 너는 대괄호 안에서 연산 가능, 변수도 가능

  * 없는 속성을 바로 추가할 수도 있다. ex) 객체.없는속성 = 값;
  * 속성제거: delete 객체.속성;
  * in 연산자: 속성이 객체에 존재하는지 판단하고, true or false 반
  * 객체 안에 함수 정의할 수도 있다.
    ```
    let greetings = {
      sayHello: function (name) {
        console.log(name);
      }
    }

    사용: greetings.sayHello('jingu'); 또는 greetings['sayHello']('jingu');
    ```

  * for in 주의점<br> 정수형 프로퍼티에 한해서 오름차순으로 정렬이 되고 나머지는 추가한 순서대로 정렬돼서 출력된다. (정수형 프로퍼티가 문자열이어도 마찬가지이다)


  * [Date 객체](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Date)// 필요할 때 봐라

* 배열
  * 배열의 값을 삭제하고 싶을 땐 splice 메서드 사용(삭제 뿐 아니라 추가, 수정 가능) splice(startInex, deleteCount, item...)
    * arr.splice(1) // 1번째 인덱스를 포함한 이후의 모든 요소를 삭제
    * arr.splice(1, 1) // 1번째 인덱스로 부터 1개의 요소를 삭제 (자바에서 list.remove(1)과 동일)
    * arr.splice(1, 1, 'hi', 'hello') // 1번 인덱스로부터 1개를 삭제하고 그 자리에 hi와 hello를 추가
   
    * arr.splice(1, 0, 'hi', 'hello') // 삭제를 안하고 첫번째 인덱스에 값을 추가

  * arr.shift(); // 배열의 첫 요소를 삭제
  * arr.pop(); // 배열의 마지막 요소를 삭제
  * arr.unshift(값); // 배열의 첫 요소로 값 추가
  * arr.push(값); // 배열의 마지막 요소로 값 추가
  * arr.indexOf(값); // 배열에 값이 포함돼 있는지 확인 가능. 있다면, 인덱스 반환. 없으면 -1 반환. 여러개면, 가장 앞에 있는 놈 반환
  * arr.includes(값); // 있으면 true
  * arr.reverse(); // 배열 뒤집기
  * 배열에선 for in 말고, for of 문을 써야 한다. (for in의 경우, 값이 아니라 인덱스가 빠져나오기 때문)
 
  * 배열복사 (자바에서 for문으로 바꾼 것처럼 for문으로 바꿔도 되지만, 다른 방법도 있음)
    * let arr2 = arr1.slice(); // slice에 인자를 안주면 모든 값을 반환하는 것을 활용
    * 이 경우, 내용만 복사하고 다른 배열이 된다.

* 숫자형
```
let myNumber = 0.3591;
console.log(myNumber.toFixed(7)) // 0.3591000 이 출력 된다. (문자열)
// 숫자로 표시하려면 Number로 형변환 해주거나, + 기호를 앞에 붙여주면 된다.

```

* typeof 주의점
 * typeof null; 은 null이 아니라 object가 반환된다.
 * typeof 함수이름; // 자바스크립트에서 함수는 객체 취급 되지만, function이 리턴된다.


* [null 병합 연산자](https://ko.javascript.info/nullish-coalescing-operator)

* AND 연산자
  * 무조건 boolean을 return 하는 것이 아니다!!
  * 왼쪽 피연산자가 falsy 값일 땐, 왼쪽 피연산자를 리턴
  * 왼쪽 피연산자가 truthy 값이면 오른쪽 피연산자를 리턴

* OR 연산자
  * 왼쪽 피연산자가 falsy 값일 땐, 오른쪽 피연산자를 리턴
  * 왼쪽 피연산자가 truthy 값이면 왼쪽 피연산자를 리턴

* 함수선언식
  * 선언전에 함수를 호출 가능 (호이스팅)

* 함수표현식
  * 변수에 할당하여 사용
  * 주의) 함수 내부에서 함수 자신을 사용하려고 하면 (재귀함수) 반드시 기명 함수 표현식을 사용해라
 
* 콜백함수: 다른 함수의 인자로 사용되는 함
* 고차함수: 함수를 리턴하는 함

* Parameter: 함수 선언부에서 소괄호 안에 작성되는 것
* Argument: 함수 호출할 때 Parameter로 전달하는 값

* arguments 객체
  * 함수 내부에서 사용할 수 있는 객체
  * 함수를 호출할 때 전달한 argument들이 배열 모양으로 담겨있다. but 배열은 아니다.
  * 인덱스를 통한 접근 가능, for-of문 사용 가능, length를 통해 길이 확인 가능
  * but, 배열의 메서드를 활용할 수 없다.
  * arguments 라는 이름이 정해져있으므로 함수 내부에서 해당 이름 변수를 재정의 하지 않도록 주
  
* Rest Parameter
  * 배열이기 때문에, 배열의 메서드를 활용할 수 있다. ex) splice
  * 변수 앞에 마침표 3개 붙여준다
  * 일반 parameter와 같이 사용 가능. but 마지막에 써야 한다.
  ```
  function func(first, second, ...args) {
 
  }
  ```

* Arrow Function
  * arguments를 포함하지 않는다. (Rest Parameter는 사용 가능)
  * 이름을 가지지 않는 익명함수이다.
  * this를 다루는 방식이 일반 함수와 다르다.
  * Arrow Function이 선언되기 직전 유효한 this값과 같다.
  * 따라서, 객체의 메소드를 만들 땐 Arrow Function 보다는 일반 함수가 좀 더 권장된다.
  ```
  // 일반적인 함수
  const getTwice = function(number) {
   return number * 2;
  };

  const getTwice = (number) => {
   return number * 2;
  };

  // return문만 있다면, 중괄호와 return 키워드 또한 생략 가능
  const getTwice = (number) => number * 2;
   
  ```

* this
  * this의 기본값은 window 객체
  * 함수를 호출한 객체가 this에 담긴다.

* 문장과 표현식 
  * 문장: 어떤 동작이 일어나도록 작성된 최소한의 코드 덩어리
  * 표현식: 결과적으로 하나의 값이 되는 모든 코드
  * 표현식은 그 자체로 문장일 수 있다. ex) 할당식, 함수호출
  * return 문의 값으로 쓸 수 있다면 표현식이다.
    
* Spread 구문
  * 각각의 개별값으로 펼쳐준다. 
  * 객체도 Spread 가능
```
const numbers = [1, 2, 3];
const numbers2 = [4, 5, 6];
console.log(...numbers); // 1 2 3 출력

const copy = [...numbers, 4]; // [1, 2, 3, 4];
const union = [...numbers, ...numbers2];

const members = ['진구', '여진', '윤구'];
const newObject = {...members }; // {0: "진구", 1: "여진", 2: "윤구"}
// 배열을 펼쳐서 객체에 담으면, 0번 부터 시작하는 배열의 인덱스가 Property Name이 된다.
```

* 모던한 프로퍼티 표기법
  * ES2015 이후부터는 변수나 함수를 활용해서 객체의 프로퍼티나 메소드를 만들 때, 변수나 함수의 이름이 프로퍼티 네임으로 사용할 이름과 같다면 중복해서 그 이름을 두 번 작성하지 않고, 하나만 작성해도 된다.
  
  * 객체 안에서 함수를 프로퍼티로 사용할 때, function키워드와 : 기호를 생략 가능
    * ex) getFullName : function() { 함수내용 } // 원래 쓰던 방식
    * getFullName() { 함수내용 } // 이렇게도 가능

  * 표현식을 대괄호로 감싸면, 프로퍼티 네임으로 사용 가능.
 
* 옵셔널 체이닝 (Optional Chaining)
  * 옵셔널 체이닝 연산자 (?.)
  * 만약 옵셔널 체이닝 연산자 왼편의 프로퍼티 값이 undefined 또는 null 이 아니라면 그 다음 프로퍼티 값을 리턴하고 그렇지 않은 경우에는 undefined르르 반환하는 문법
  * null 병합 연산자(??)와 함께 활용할 수 있다.
  * a ?? b // a가 null도 아니고 undefined도 아니면 a, 그 외의 경우는 b
  ```
  console.log(user.cat?.name ?? '함께 지내는 고양이가 없습니다.');
  // user.cat 이 존재하면, name 속성을 반환하고, 존재하지 않으면 undefined니까 문자열을 출력
  ```

* Destructing (구조 분해)
  * 배열 구조 분해는 대괄호로 감싸기
  * 객체 구조 분해는 중괄호로 감싸
```
// 1. Destructuring 문법을 활용해서 numbers 배열의 각 요소를 one, two, three라는 변수에 할당해보세요
const numbers = [1, 2, 3];
const [one, two, three] = numbers;



// 2. Destructuring 문법을 활용해서 TV는 livingRoom, 나머지 요소들(배열)은 kitchen 변수에 할당해 주세요
const products = ['TV', '식탁', '냉장고', '전기밥솥', '전자레인지', '오븐', '식기세척기'];
const [livingRoom, ...kitchen] = products;



// 3. Destructuring 문법을 활용해서 두 변수의 값을 서로 바꿔주세요
let firstName = 'Kang';
let lastName = 'Young';
[firstName, lastName] = [lastName, firstName];



// 테스트 코드
console.log(one);
console.log(two);
console.log(three);
console.log(livingRoom);
console.log(kitchen[1]);
console.log(firstName);
console.log(lastName);
```

```
// Destructuring 문법을 활용해서 myBestSong의 프로퍼티 중 title과 artist는 각각 songName과 singer라는 변수에, 나머지는 rest라는 변수에 객체로 할당해 주세요
const myBestSong = {
	title: '무릎',
	artist: '아이유(IU)',
	release: '2015.10.23.',
	lyrics: '모두 잠드는 밤에...'
};

// myBestSong의 title 프로퍼티 네임이 있다면, 그에 해당하는 값을 songName 변수에 저장해라.
const {title: songName, artist: singer, ...rest} = myBestSong;

console.log(songName);
console.log(singer);
```
