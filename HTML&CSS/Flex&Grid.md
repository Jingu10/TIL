# Flex

* inline-flex
  * 기본적으로 flex와 동일한 기능이나, flexbox자체가 inline 속성을 가지는 것.
  * flex-container는 기본적으로 한 줄을 다 차지하나, inline-flex는 content 크기 만큼만 공간을 가짐
 
* align-items vs align-content
  * align-items: flex-container 안에서 전체 item의 배치를 어떻게 할 것이냐에 대한 속성
  * align-content: flex-conttainer 안에서 item의 줄 간격을 어떻게 배치할 것이냐에 대한 속성 (wrap된 상태에서만 의미가 있다.) 
  * [그림으로 비교](https://www.inflearn.com/questions/752797/align-items-vs-align-content)
  * align-items: center // 각 줄에서 item들이 교차축 중앙으로 정렬됨
  * align-content: center // 모든 줄이 교차축 중앙으로 정렬됨


* [basis, grow, shrink](https://studiomeal.com/archives/197)

* flex-basis
   * 기본값 auto : 해당 아이템의 width값을 사용 (width를 따로 설정하지 않으면 컨텐츠의 크기)
   * 0 : 공간을 점유하지 않아.
   * px : 고정값을 줄 수 있음. 원래 100px 아래였으면 늘어나고, 100px 넘는건 줄어들지 않고 그대로 유지
   * 주의) flex-basis: 100px vs width: 100px // width는 강제 고정이라, 100px 넘는 것도 100px로 맞춰진다. 


* flex-grow
   * 숫자값이 들어간다. 기본값은 0
   * flex-basis를 제외한 여백 부분을 flex-grow에 지정된 숫자의 비율로 나눠가진다. (여백의 비율)
   * flex-grow로 늘어날 수 있는 한계는 내 부모의 width (너를 넘지 못해)

* flex-shrink
   * 기본값은 1. 따로 세팅하지 않아도 아이템이 flex-basis보다 작아질 수 있음.
   * flex-shrink: 0; // 컨테이너가 작아져도 크기가 줄어들지 않게 한다. 줄어들 때 고정폭을 가지게끔!


* flex // grow shrink basis 순인데, basis는 생략하면 기본값인 auto가 아니라 0이 들어간다.
   * flex: 1; /* flex-grow:1; flex-shrink: 1; flex-basis: 0% */
