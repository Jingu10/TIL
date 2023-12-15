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

* 배열 메소드
```
1. forEach

const numbers = [1, 2, 3];

numbers.forEach((element, index, array) => {
  console.log(element); // 순서대로 콘솔에 1, 2, 3이 한 줄씩 출력됨.
});


2. map: 첫번째 아규먼트로 전달하는 콜백 함수가 매번 리턴하는 값들을 모아서 새로운 배열을 만들어 리턴한다.

const numbers = [1, 2, 3];
const twiceNumbers = numbers.map((element, index, array) => {
  return element * 2;
});

console.log(twiceNumbers); // (3) [2, 4, 6]

/*
forEach와 map 반복 도중 요소가 늘어날 경우, 처음 가지고 있던 요소만큼만 반복.
but, 줄어들 경우 현재 가지고 있는 요소만큼만 반복.
*/


3. filter: 조건과 일치하는 요소만 모아서 새로운 "배열"을 리턴
일치하는 요소가 한 개 이더라도, 배열을 리턴하기 때문에 값으로 쓰기 위해선 스프레드 구문을 활용해야함.

const devices = [
  {name: 'GalaxyNote', brand: 'Samsung'},
  {name: 'MacbookPro', brand: 'Apple'},
  {name: 'Gram', brand: 'LG'},
  {name: 'SurfacePro', brand: 'Microsoft'},
  {name: 'ZenBook', brand: 'Asus'},
  {name: 'MacbookAir', brand: 'Apple'},
];

const apples = devices.filter((element, index, array) => {
  return element.brand === 'Apple';
});

console.log(apples); // (2) [{name: "MacbookPro", brand: "Apple"}, {name: "MacbookAir", brand: "Apple"}]


4. find: 조건과 일치하는 가장 첫번째 요소를 리턴하고 반복을 종료

const myLaptop = devices.find((element, index, array) => {
  console.log(index); // 콘솔에는 0, 1, 2까지만 출력됨.
  return element.name === 'Gram';
});

console.log(myLaptop); // {name: "Gram", brand: "LG"}


5. some, every

const numbers = [1, 3, 5, 7, 9];

// some: 조건을 만족하는 요소가 1개 이상 있는지
const someReturn = numbers.some((element, index, array) => {
  console.log(index); // 콘솔에는 0, 1, 2, 3까지만 출력됨.
  return element > 5;
});

console.log(someReturn); // true;

// every: 조건을 만족하지 않는 요소가 1개 이상 있는지
const everyReturn = numbers.every((element, index, array) => {
  console.log(index); // 콘솔에는 0까지만 출력됨.
  return element > 5;
});

console.log(everyReturn); // false;


6. reduce: 누적값을 계산할 때 활용.
두 개의 파라미터를 활용.
첫 번째 파라미터는 반복동작할 콜백함수.
매번 실행되는 콜백함수의 리턴값이 다음에 동작할 콜백함수의 첫번째 파라미터로 전달.
결과적으로 마지막 콜백함수가 리턴하는 값이 reduce 메소드의 최종 리턴값이 된다.
두 번 째 파라미터는 초기값. 첫번째로 실행될 콜백함수의 가장 첫 번째 파라미터로 전달.

const numbers = [1, 2, 3, 4];

// reduce
const sumAll = numbers.reduce((accumulator, element, index, array) => {
  return accumulator + element;
}, 0);

console.log(sumAll); // 10


7. sort

const numbers = [1, 10, 4, 21, 36000];

// 오름차순 정렬
numbers.sort();
console.log(numbers); // (5) [1, 4, 10, 21, 36000]

// 내림차순 정렬
numbers.sort((a, b) => b - a);
console.log(numbers); // (5) [36000, 21, 10, 4, 1]


8. reverse

numbers.reverse();
console.log(numbers); // [36000, 21, 4, 10, 1];

```

* Map
  * 이름이 있는 데이터를 저장한다는 점에서 객체와 비슷.
  * 일반 객체는 할당연산자를 통해 값을 추가하고 점 표기법이나 대괄호 표기법으로 접근.
  * Map은 메소드를 통해서 값을 다룸.
  * const map = new Map();
  * map.set(key, value): key를 이용해 value를 추가하는 메소드.
  * map.get(key): key에 해당하는 값을 얻는 메소드. key가 존재하지 않으면 undefined를 반환.
  * map.has(key): key가 존재하면 true, 존재하지 않으면 false를 반환하는 메소드.
  * map.delete(key): key에 해당하는 값을 삭제하는 메소드.
  * map.clear(): Map 안의 모든 요소를 제거하는 메소드.
  * map.size: 요소의 개수를 반환하는 프로퍼티. (메소드가 아닌 점 주의! 배열의 length 프로퍼티와 같은 역할)
 
* Set
  * set.add(value): 값을 추가하는 메소드. (메소드를 호출한 자리에는 추가된 값을 가진 Set 자신을 반환.)
  * set.has(value): Set 안에 값이 존재하면 true, 아니면 false를 반환하는 메소드.
  * set.delete(value): 값을 제거하는 메소드. (메소드를 호출한 자리에는 셋 내에 값이 있어서 제거에 성공하면 true, 아니면 false를 반환.)
  * set.clear(): Set 안의 모든 요소를 제거하는 메소드.
  * set.size: 요소의 개수를 반환하는 프로퍼티. (메소드가 아닌 점 주의! 배열의 length 프로퍼티와 같은 역할
  * Set은 개별 값에 바로 접근하는 방법이 없다. for of 등을 활용하여 하나씩 접
  * 처음 Set을 생성할 때 아규먼트로 배열을 전달할 수 있다.
  ```
  const numbers = [1, 3, 4, 3, 3, 3, 2, 1, 1, 1, 5, 5, 3, 2, 1, 4];
  const uniqNumbers = new Set(numbers);

  console.log(uniqNumbers); // Set(5) {1, 3, 4, 2, 5}
  ```

* 모듈: 자바스크립트 파일 하나. 
  * 모듈 스코프
    * 모듈 파일 안에서 선언한 변수는 외부에서 접근할 수 없도록 막아야 한다.
    * 즉, 파일 안에서 모듈 파일만의 독립적인 스코프를 가지고 있어야 한다.
    * HTML파일에서 자바스크립트 파일을 불러올 때 모듈 스코프를 갖게 하려면 script 태그에 type 속성을 module 이라는 값으로 지정해주어야 한다.
    ```
    <body>
  	<script type="module" src="index.js"></script> // 모든 파일을 다 쓰는 게 아니라, 진입점이 되는 자바스크립트 파일만 써주면 된다.
    </body>
    ```

```
// 선언문 export
export const title = 'Module';


// 선언된 변수나 함수를 코드 블록으로 묶어서 export
const printer = (value) => {
  console.log(value);
};

const arrPrinter = (arr) => {
  arr.forEach((el, i) => {
    console.log(`${i + 1}. ${el}`);
  })
};

export { printer, arrPrinter }; // 객체를 export 한 게 아님!


// as 키워드를 통해 이름을 변경해서 export
export { printer as namedPrinter, arrPrinter };


// default 키워드를 통해 표현식을 export
const title = 'Module';
export default title;


// 값을 바로 export도 가능하다
export default 'Module'


// 여러 대상을 객체 값으로 모아 default로 내보내는 방식도 가능
export default { title, printer, arrPrinter }; // {title: title, printer: printer, arrPrinter: arrPrinter} 이라는 객체가 export 된 거임!


// 선택적 import
import { title, data } from './modules.js';


// 이름 바꿔 import
import { title as moduleTitle, data } from './modules.js';


// 모두 불러오기
import * as modules from './modules.js';


// default export 된 대상을 import 할 때는 as를 써야 한다.
import { defult as modules } from './modules.js';

// 축약형으로 불러올 수도 있다. (위 코드와 같은 동작 default만 가능)
import modules from './modules.js';

```


* 이벤트 핸들링
  * 이벤트가 발생했을 때 특정한 동작을 하도록 다루는 것
  * 자바스크립트를 통해 이벤트를 다루는 일
* 이벤트 핸들러 (이벤트 리스너)
  * 이벤트가 발생했을 때 일어나야하는 구체적인 동작들을 표현한 코드.

* window 객체
  * 브라우저 창을 대변
  * 자바스크립트에서 최상단에 존재하는 객체
  * 자바스크립트 코드 어느 곳에서나 접근 가능. = 전역 객체

* DOM(Document Object Model)
  * 웹 페이지에 나타나는 HTML 문서 전체를 객체로 표현한 것
 
* 요소노드: 태그를 표현하는 노드
* 텍스트노드: 요소 노드의 자식 노드가 되고, 자식 노드를 가질 수 없다.
