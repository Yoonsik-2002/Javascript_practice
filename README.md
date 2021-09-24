# Javascript 배운내용 정리 + 실습활동
**웹 페이지에서 자바스크립트의 역할**

웹 페이지는 HTML% 태그, CSS3스타일시트, 자바스크립트 프로그램의 
3 가지 코드가 결합되어 작성된다.

여기서, ___자바스크립트의___ 역할은 크게 5가지가 있다.


- 사용자의 입력 및 계산
  - 키나 마우스의 입력을 받고 계산하는 역할을 한다.
 
- 웹 페이지 내용 및 모양이 동적 제어
  - HTML 태그의 속성이나 콘텐츠, CSS 프로퍼디의 값을 변경하여 웹 페이지에
    
    동적인 변화를 일으키는 역할을 한다.

- 브라우저 제어
  - 브라우저 윈도우의 크기나 모양 변경, 새 윈도우나 탭 열기, 다른 웹 사이트 접송, 브라우저의 히스토리 제어 등
    
    브라우저의 작동을 제어하는 데 활용된다.
    
- 웹 서버와의 통신
  - 웹 페이지가 웹 서버와 데이터를 주고받을 떄 활용된다.

- 웹 애플리케이션 작성
  - HTML5는 자바스크립트 언어로 활용할 수 있는 많은 기능(API)을 제공하므로, 다양한 웹 애플리케이션을 개발 할 수 있다.

**자바스크립트 코드의 위치**

- HTML 태그의 이벤트 리스너 속성
  - 이벤트(event)는 사용자의 입력 행위를 브라우저가 웹 페이지에 전달하는 수단이다. 
    사용자가 HTML 태그가 출력된 영역에 키를 입력하거나 마우스를 클릭하면 이벤트(event)가 발생한다. 이벤트의 종류는 click, change, mousemove등 많은 종류가 있다.
    
  - 이 이벤트를 처리하는 자바스크립트 코드를 이벤트 리스너(event listener)라고 한다.
    onclick, onchange, onmousemove와 같이 이벤트 앞에 'on'을 붙인 이름이 HTML 태그의 이벤트 리스너 속성으로 사용된다. 
- <script></script> 내에 작성
  - <script></script>는 <head></head>나 <body></body> 내 어디든 들어갈 수 있다.
  - 웹페이지 내에 <script></script>를 여러 번 작성할 수 있다.
- 자바스크립트 파일에 작성
  - 자바스크립트 코드를 확장가자 .js인 별도의 파일로 저장하고 다음과 같이 <script>태그의 src 속성으로 불러 사용할 수 있다.
  
  ```javascript
  <script src="파일이름.js">
    // HTML5부터 이곳에 자바스크립트 코드를 추가 작성하면 안됨
  </script>```

- URL 부분에 작성
  - <a> 태그의 href 속성에도 자바스크립트 코드를 작성할 수 있다.
  
  ```javascript
  <a href="javascript:자바스크립트 코드">링트</a>
  ```
  
**자바스크립트 다이얼로그 : 사용자 입력 및 메시지 출력**
- 프롬프트 다이얼로그, prompt("메시지", "디폴트 입력값")
  - prompt() 함수는 다이얼로그를 출력하고 사용자로부터 문자열을 입력받아 리턴한다.
  ```javascript
  var ret = prompt("이름을 입력하세요", 조윤식);
  if (ret == null) {
  // 취소 버튼이나 다이얼로그를 닫은 경우
  }
  else if (ret == "") {
  // 문자열 입력없이 확인 버튼을 누른 경우
  }
  else {
  // ret에는 사용자가 입력한 문자열
  }```
  
- 확인 다이얼로그, confirm("메시지")
  - cofirm() 함수는 '메시지'와 확인/취소(OK/CANCEL) 버튼을 가진 다이얼로그를 출력한다.
  ```javascript
  var ret = confirm("메세지를 전송할까요?")
  if (ret == true) {
  // 사용자가 "확인" 버튼을 누른 경우
  }
  else {
  // 취소버튼이나 다이얼로그를 닫은 경우
  }```
  
- 경고 다이얼로그, alert("메시지")
  - alert() 함수는 다이얼로그를 출력하여 단순히 메시지를 전달한다.
  ```javascript
  alert("클릭하였습니다.")
  ```
  
**변수 선언**
  
변수는 자바스크립트 코드가 실행중에 데이터를 저장하는 공간의 이름이다. C나 Java와는 달리, 자바스크립트는 변수에 데이터 타입을 정하지 않는다.

- var 키워드를 이용한 변수 선언
  ```javascript
  var score;               // 변수 score 선언
  var year, month, day;    // year, month, day의 3개의 변수 선언
  var address = "서울시";  // address 변수를 선언하고 "서울시"로 초기화
  ```

  ***자바스크립트에는 변수의 타입이 없으므로 다음과 같이 var와 변수 명만으로 선언한다.***   int, double X => var(유동적)
 
**지역변수와 전역변수**

변수는 사용범위(scope)에 따라 다음과 같이 전역변수(global)와 지역벼수(local)로 나뉜다.
  - 전역 변수 : **함수 밖에서 선언** 되거나 **함수 내에서 var키워드 없이 선언,** 프로그램 **전역** 에서 사용가능
  - 지역 변수 : **함수 안에서 var키워드로 선언,** 선언된 함수 내에서만 사용 
  
  ```javascript
  var x;          // 전역변수 x선언
  function f() {  // 함수 f() 코드
    var y;        // 지역변수 y 선언
    x = 10;       // 전역변수 x에 10 저장
    y = 10;       // 지역변수 y에 10 저장
    z = 10;       // 새로운 전역변수 z선언. 10으로 
  }
  ```
  
  **this로 전역 변수 접근**
  
  지역변수와 전역변수의 이름이 같을 떄, this를 이용하면 전역변수에 접근할 수 있다.
  
  함수 f() 내에서 변수 x를 언급하면 당연히 지역 변수 x를 뜻한다. this.x로 하면 전역변수 x에 접근할 수 있다.
  
  ```javascript
  var x;            // 전역변수 x 선언
  function f() {    // 함수 f() 코드
    var x;          // 지역변수 x 선언
    x = 1;          // 지역변수 x에 1 저장
    this.x = 100;   // 전역변수 x에 100 저장
  }
  ```
  
  **함수**
  함수는 데이터를 전달받아 처리한 후 결과를 돌려주는(리턴하는) 코드 블록이다.
  
  함수는 전달받는 데이터 없이 정해진 작업을 하기도 하고, 결과를 돌려주지 않기도 한다.
  
  - 함수의 구성
  ```javascript
  function adder (a, b) {
    var sum;
    sum = a + b;
    return sum;
  }
  ```
  
  
  
