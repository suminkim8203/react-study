# css 최적화

# js Syntax 1장

1. Syntax(구문): 약속된 문법
2. Interpreter(번역): 갤럭시 AI/웹브라우저

3. 문법(구문)에 맞게 작성하면 인터프리터가 번역을 해준다
   프로그래밍은 요구사항을 분석하고 (개인별로 작성: 의사코드)
   Syntax를 이용해서
   적절한 자료구조 + 적절한 함수를 활용하고,
   흐름을 제어하여 요구사항을 만족시킨다.

# js Syntax 코드 위치

1. inline 방식

```html
<div class="wrap" onclick="alert('안녕');"></div>
```

2. 태그 방식

```html
<script>
  alert("반가워");
</script>
```

3. 외부파일 방식

```html
<script src="./js/script.js">
  alert("반가워"); // 외부 js파일이 덮어쓰기 때문에 '반가워'는 실행 안 됨
</script>
```

# Swiper Slide 적용해 보기 1.

- _Slide를 직접 코딩하지 마세요_
- 사용법을 배운다.
- [Swiper](https://swiperjs.com/), [Slick](https://kenwheeler.github.io/slick/), [BxSlider](https://bxslider.com/)가 있다.

- swiper 사용하는 이유
  : React 지원
  : 화면 터치 지원
  : 반응형 지원

## 1. Swiper 슬라이드 적용시 주의사항

- html 로드 완료 및 이미지 로드 완료 후 실행 권장.

```js
window.addEventListener("load", function () {
  // 실제 슬라이드 코드 배치하자.
});
```

# js 2장

```txt
publisher: 웹브라우저용 프로그래밍 언어 (html, css 다룸)

Frontend: node.js (웹브라우저용 프로그래밍 x pc용 프로그래밍 언어
서버 (dothome, db, html, css……)

자바스크립트의 문제? (였던 것…)

웹 브라우저 player 마다 다 다르다.

IE, Chrome, Opera, Safari… (Syntax가 모두 다 다르다.)
ex) 메뉴 하나를 만들어도 각 웹브라우저에 맞게 마이그레이션을 해야 했음

그래서 자바스크립트의 표준화가 이루어짐 (ES6 버전부터!)

렌더링? (목표는 html, css, js로 문서 만들기)

렌더링의 종류 2가지

SSR (Server Side Redering) 완성품을 만들어서 제공함
: php, spring(WAS), next.js

CSR (Client Side Redering) 소스를 가지고 와서 화면을 제작
: React, vue, Angular…

Ajax (아작스, 에이젝스…) : 데이터(json) 통신

: 비동기 (Request 요청 Response 회신)
(요청을 하고, 신호가 오기 전까지 다른 작업을 하고 있는 것.)

: 동기

두 가지를 구분할 수 있어야 한다!

: XML Http Request (XHR 통신)

jQuery

: vanila JS / pure JS (fetch/async await)

≤===⇒ jQuery (ajax)

Node.js 가능? = 서버(Express.js), DB(MongoDB, MySql) 가능한가요?

SPA: Single Page Application

CBD: Component based Developement

모듈? 코드 묶음 확장자는 js일수도 다른거일수도…….

객체 지향: 모든 코드의 시작은 객체로 설계하여 전개한다.

ex) 기획: xls로 제공
- 인터파크 상품(최상단 배치되는 제품의 정보를 노출)
상품의 기본 정보
- 할인율, 가격, 제목, 이미지 보여주자!
- 제품 상세 정보로 이동하는 경로를 제공

디자이너
-ui 및 ux 배치

BE 개발자
- 제품의 정보를 DB에 저장해둠. (일부만 Response)

FE 개발자


const Good = {
   ratio: 할인율,
   price: 가격,
   title: 제목,
   pic: 이미지주소,
   link: 제품주소
}

const 객체명 = {
   속성명 : 속성값,
   기능 : function() { 기능 }
}


중괄호{}를 열고 닫으면 전부 객체! (일단은…)

프로토타입 기반: 프로토타입(유전자)를 상속받아 덧댄다.

Babel? : 현재 최신 코드를 옛날 코드로 변환해 준다.

```

# Swiper Slide 적용해 보기 2.

- 데모사이트의 core 메뉴를 통해서 참조한다.
- 기본 css 와 js 파일은 CDN으로 참조한다.

```html
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css"
/>
```

- 기본형 코드를 작성해서 원하는 영역에 배치한다.
- 슬라이드 개수만큼 swiper-slide div를 만든다.

```html
<div class="swiper 원하는 이름">
  <div class="swiper-wrapper">
    <div class="swiper-slide">내용</div>
    <div class="swiper-slide">내용</div>
    <div class="swiper-slide">내용</div>
  </div>
</div>
```

- css로 `원하는이름`을 찾아서 width, height를 100% 주기.
- css로 `원하는이름`에 절대로 display 등을 넣으면 안됨.

# Swiper Slide 적용해 보기 3.

- 외부 데이터 연동(json)
- 데이터의 구조를 설계
- json이란 javaScript Object Notation입니다.

```json
[
  { "키": 값, "키": "값", "키": "값" },
  { "id": 2, "pic": "b2.png", "url": "#" },
  { "id": 3, "pic": "b3.png", "url": "#" },
  { "id": 4, "pic": "b4.png", "url": "#" }
]
```

# Swiper Slide 적용해 보기 4.

- 비동기 호출하기(vanila/pure js)
  : BE와 협업시 활용
- fetch를 활용 가능
- async await 활용 가능

# js 3장

```txt
# 자바스크립트 개발 환경과 실행 방법

브라우저와 Node.js는 용도가 다르다.

브라우저
: html, css, js를 실행해 웹페이지를 브라우저 화면에 렌더링 하는 것이 주 목적

Node.js
: 브라우저 외부에서 자바스크립트 실행 환경을 제공하는 것이 주 목적

브라우저에서 js 쓰는 이유

DOM(Document Object Model)
- html을 읽고, 수정 등등의 조작을 하는 함수 (DOM API)
document.querySelector(”.wrap”)

->위 사항을 제외한 나머지를 Node.js에서 다룬다.

클라이언트 사이드 API
DOM, BOM, Canvas, XMLHttpRequest, fetch, requestAnimationFrane, SVG, Web Storage, Web Component, Web Worker 등…

Node.js 설치하면 자동으로 npm(Node Package(js 소스) Manager) 설치

https://www.npmjs.com/

npm install 패키지명@버전

(yarn install 패키지명@버전)

node -v

mpm -v

nvm (Node.js 의 버전을 자유롭게 변경하고, 설치)
```

# Swiper Slide 적용해 보기 5.

- 외부 js 파일을 이용한다.

```html
<script src="./js/파일명.js"></script>
```

```js
window.addEventListener("load", function () {
  // 내용작성
});
```

- swiper에 보여줄 데이터를 외부 .json 파일로 연동한다.
  : 자료(데이터)를 만들어주는 동료 = BE
  : BE와 협의가 필요함. (협업의 기본)
  : 초기에는 가짜데이터(Dummy, Mockup)을 가지고 작업

```json
// json 기본구조
[
  {"키명": "키값"},
  {"키명": "문자열"},
  {"키명": 숫자},
  {"키명": true},
  {"키명": []},
  {"키명": {}},
]
```

```json
[
  {
    "id": 1,
    "pic": "b1.png",
    "url": "#",
    "title": "AI 헬스케어의 <br/> 마일스톤을 찍다"
  },
  {
    "id": 2,
    "pic": "b2.png",
    "url": "#",
    "title": "카카오브레인의 <br/> 연구문화"
  },
  {
    "id": 3,
    "pic": "b3.png",
    "url": "#",
    "title": "PathFinder 2기의 <br/> 언어모델 활용기"
  },
  {
    "id": 4,
    "pic": "b4.png",
    "url": "#",
    "title": "칼로리의 꿈 <br/> 시리즈 ③"
  }
]
```

- json 데이터를 이용해서 자료를 추출한다.

  - 외부 주소를 통해서 자료를 불러들이기 위해 fetch를 알고 적용한다.
  - 더불어서 크롬 개발자 도구(f12)의 NetWork 탭을 알아야 한다.
  - 옵션으로 Fetch/XHR을 선택할 수 있어야 한다.
  - request와 response를 구별하여 파악할 수 있어야 한다.

```js
fetch("주소").then().then().catch();
```

```js
fetch("주소")
  .then((결과) => {
    const 접속결과 = 결과.json();
    return 접속결과;
  })
  .then()
  .catch();
```

```js
fetch("주소")
  .then((결과) => {
    return 접속결과;
  })
  .then((최종자료)=>){
    // 하고 싶은 일 마음대로...
  }
  .catch();
```

```js
fetch("주소")
  .then((결과) => {
    return 접속결과;
  })
  .then((최종자료)=>){
    // 하고 싶은 일 마음대로...
    // 우리가 할 일을 진행한다.
  }
  .catch((오류) => {
    // 오류처리
  });
```

- 추출된 데이터로 html을 생성한다.
  : 백틱(``)을 적극적으로 사용한다.

```js
let slideTags = "";

for (let i = 0; i < result.length; i++) {
  const data = result[i];
  // 템플릿 문법 필요 (html 생성)
  const test = `<div class="swiper-slide">
          <a href="${data.url}" style="background: url('./images/${data.pic}') no-repeat center; background-size: cover;">
            <p class="slide-title">
              ${data.title}
            </p>
          </a>
        </div>`;
  slideTags += test;
}
```

: html을 배치한다.

```js
// 원하는 장소에 출력해보기
const whereTag = document.querySelector(".topslide .swiper-wrapper");
whereTag.innerHTML = slideTags;
```

- swiper를 작동시킨다.
  : html 완료 후 슬라이드 생성하자.

```js
// DOM 을 다루려고 하는 목적인 경우
window.addEventListener("load", function () {
  // 1. 외부에서 자료를 불러온다.
  const dataUrl = "./apis/topslide.json";

  fetch(dataUrl)
    .then((response) => {
      // Step 1. 자료 받아서 json 변경하기
      // 토큰을 js의 데이터로 변경하기
      const data = response.json();
      // 변환된 결과를 돌려주기
      return data;
    })
    .then((result) => {
      // Step 2. json 변경된 데이터 활용하기
      // 전체 글자 모음
      let slideTags = "";

      for (let i = 0; i < result.length; i++) {
        const data = result[i];
        // 템플릿 문법 필요 (html 생성)
        const test = `<div class="swiper-slide">
          <a href="${data.url}" style="background: url('./images/${data.pic}') no-repeat center; background-size: cover;">
            <p class="slide-title">
              ${data.title}
            </p>
          </a>
        </div>`;
        slideTags += test;
      }

      // 2. 자료를 이용해서 슬라이드에 배치할 html 을 만든다.
      // 원하는 장소에 출력해보기
      const whereTag = document.querySelector(".topslide .swiper-wrapper");
      whereTag.innerHTML = slideTags;

      // 3. html 완성후 swiper 를 생성한다.
      // 기본코드를 넣어보자.
      var topSlide = new Swiper(".topslide", {});
    })
    .catch((error) => {
      console.log(error);
    });
});
```

# Swiper Slide 적용해 보기 6.

- [옵션](https://swiperjs.com/demos)
  : loop
  : autoplay
  : effect
  : speed
  : [pagenation](https://swiperjs.com/demos#pagination)
  : 페이지네이션 디자인 수정하기 참조

```css
.bannerslide .swiper-pagination {
  bottom: 30px !important;
}
.bannerslide .swiper-pagination-bullet {
  width: 4px !important;
  height: 4px !important;
  background: #ffffff !important;
  opacity: 0.7 !important;
  border-radius: 4px !important;
  transition: width 0.3s;
  margin: 0 2px !important;
}
.bannerslide .swiper-pagination-bullet-active {
  background: #ffffff !important;
  opacity: 1 !important;
  width: 20px !important;
}
```

# js 4장

- var 변수명 = 변수값;
- let 변수명 = 변수값;
- const 변수명 = 변수값;

```txt
호이스팅(hoisting)
⇒변수 선언문이 코드의 선두로 끌어 올려진 것처럼 동작하는 자바스크립트 고유의 특징

: 변수, 함수를 선언하지 않았음에도 오류 없이 사용할 수 있다.
: 추후 코드에 오류 발생 가능성이 높음
: hoisting이 일어나지 않도록 주의 (var를 사용하지 말자.)
```

# css의 opacity와 position의 이해.

- opacity는 DOM의 내용까지 투명도가 적용된다.

- position
  : position 중에 absolute로 픽셀 위치 설정의 경우 주의할 것.
  : 반드시 position 코드가 바깥 영역에도 있어야 한다.
  : position 중에 fixed는 웹 브라우저를 기준으로 배치
  : fixed는 반드시 left, top, right, bottom을 주자
  : fixed는 보통 z-index를 준다.
  : fixed는 높이에 반영이 안 되므로 주의하자. (레이아웃 배치 문제)

```css
대상 {
  position: relative;
}
대상 {
  position: absolute;
}
대상 {
  position: fixed;
}
```

- 주의사항

```css
.box-wrap {
  position: relative;
  margin: 0 auto;
  width: 600px;
  height: 300px;
  background: orange;
}
.box {
  position: absolute;
  right: 80px;
  bottom: 20px;

  width: 200px;
  height: 200px;
  background: red;
}
```

# js 윈도우 스크롤의 위치 알아내기

```js
window.addEventListener("scroll", function () {
  // 하고 싶은 일
});
```

```js
window.addEventListener("scroll", function () {
  // 스크롤바의 위치
  const scY = window.scrollY;
});
```

# js로 css의 클래스 동적으로 활용하기

```js
// DOM 찾아서 변수로 레퍼런스 하기
const tags = document.querySelector(".클래스명");
// DOM을 이용해서 선택한 곳에 적용된 css 클래스 목록 추가
tags.classList.add("클래스명");
// DOM을 이용해서 선택한 곳에 적용된 css 클래스 목록 제거
tags.classList.remove("클래스명");
// DOM을 이용해서 선택한 곳에 적용된 css 클래스 목록 추가/제거
tags.classList.toggle("클래스명");
// DOM을 이용해서 선택한 곳에 적용된 css 클래스 목록 포함여부
tags.classList.contain("클래스명");
```

# js의 함수란? 1.

- 동일한 코드가 2번 이상 반복되면 함수를 만들려고 노력하자.
- 반복은 되지 않더라도 하나의 기능이 너무 복잡하면 함수를 만들려고 노력하자.
- 복잡하진 않지만 코드가 너무 길어지면 함수로 묶어주려고 노력하자.
- 실행의 결과가 그때그때 다른 경우에도 함수를 만들자.

```js
// 함수 선언 (함수 만들기)
function 적절한 이름_동사(){
  // 하고 싶은 일 작성
}
// 함수 호출 (함수 사용하기)
적절한 이름_동사();
// ex) 함수 체이닝
fetch().then().then().catch();
```

- 함수는 무조건 1개의 값을 리턴하도록 규정되어 있습니다.
- 리턴이라는 것은 함수 실행 후 값을 돌려주는 것을 말합니다.

```js
function 함수명() {
  // 정의하지 않으면 몰래 return undefined; 를 작성함!
}
함수명();
```

# JS 5장

```txt

표현식과 문

값(value)은 표현식이 평가된 결과

- 값?
  : 변수에 할당된 결과
  코딩에서 값이라고 할 수 있는 것은 변수에 할당(보관)된 결과를 말한다.
- 변수?
  : 컴퓨터 공간에 이름을 붙여둔 방 한 개
- 평가?
  : 식을 해석해서 값을 생성하고 참조하는 것

var sum = 10 + 20;
// 변수 sum에 할당되는 것은 10 + 20이 아니라, 결과값인 30이다.

리터럴 literal?

사람이 이해할 수 있는 문자 또는 약속된 기호를 사용해서 값을 생성하는 표기법

- 3은 단순한 아리비아 숫자 3이 아니라, 숫자 리터럴 3이라고 한다.

리터럴은 값을 평가해서 코드에 활용하기 위한 문법

표현식 expression

**리터럴 값으로 평가될 수 있는 문은 모두 표현식이다.**

메모리 할당 이전에 리터럴이 일어나고, 할당 이후에 expression 되었다고 한다.

문 (statement)
: 프로그램을 구성하는 최소 기본/최소 실행 단위

{} 범위, 영역

```

# js의 함수란? 2.

- 동일한 코드가 2번 이상 반복되면 함수를 만들려고 노력하자.
- 반복은 되지 않더라도 하나의 기능이 너무 복잡하면 함수를 만들려고 노력하자.
- 복잡하지는 않는데 코드가 너무 길어지면 함수로 묶어주려고 노력하자.
- 실행의 결과가 그때, 그때 다른 경우에도 함수를 만들자.
- 함수 정의 문

```js
function 함수이름() {
  // 할 일
}
```

- 함수 실행/호출(call) 문

```js
함수이름();
```

# js 함수의 매개변수란? 3번

- 초기 기능, 즉 함수를 정의하기 전에 기능상 자주 변하는 데이터를 고민한다.
- 기능은 스크롤시 특정 위치보다 커지면 css 추가하기
- 이전 코드는 좋지 않은 코드라고 생각이 든다.
- 함수는 스스로 지역, 즉 Local 영역(Scope)에서 처리되는 것이 좋다고 본다.
- **처리**라는 말은, 변수를 찾거나 잘못된 값이 전달되어서 오류가 나는 것을 방지하는 것을 말한다.

```js
// 홍길동에게 줄 함수
const a = 5;
const b = 0;

function 나누기(_num1, _num2) {
  if (_num2 === 0) {
    alert("나눗셈에서 0은 안 됩니다.");
  }
  return _num1 / _num2;
}
나누기(a, b);
```

# js 6장

```txt
데이터 타입(Data Type): 자료형

타입이라는 말 = 자료의 형태

불변성(immutable)
: 데이터 값이 변경될 수 없다.

- 데이터는 immutable 해야 한다.
- 상태(state)는 immutable 해야 한다.

가변성(mutable)
: 데이터 값이 변경될 수 있다.

원시데이터 6가지는 immutable 한 데이터 타입이다.

- number   1
- string   'a’
- undefined   undefined
- boolean   true, false
- null   null
- symbol   Symbol() 만들어진 값은 변경 불가

복합형 데이터 객체

객체는 원시데이터를 모아서 저장하고 관리하는 것.

JS의 리터럴로 처리될 수 있는 자료의 종류

타입 스크립트?
: 데이터 종류를 표현해주는 방식
: 자료의 형태를 설명하는 문법

표현식?
: 값을 만들어 담고 돌려주는것

undefined와 null의 차이

const a = undefined; // 값을 만들지 않음

const b = null; // 개발자가 값이 비어있음을 선언

Symbol은 중복되지 않는다고 보장하는 값 타입

**중요단어**

1. 데이터 타입: 자료(리터럴 값)의 종류
2. js에서는 값 리터럴에 따라 변수의 종류를 타입추론 한다.
3. 타입을 추측해서 프로그래머에게 물어보지 않고 타입을 변경한다. (암묵적 타입변경)

    let a = 1;

    a = “안녕”;


2, 3번은 언젠간 원하지 않는 결과가 실행된다.
의도하지 않은 오류를 일으킴.

TypeScript

let a:number = 1;

a = “안녕”; // 오류 발생

**코딩 가이드**

1. 꼭 필요한 경우인지 파악하고 변수를 만들자.
2. 변수 유효 범위는 좁게 (블록을 가능하면 쓰자) :스코프
3. 전역 변수는 가능하면 만들지 말자.
4. 변수는 상수를 사용하자. (가능하면 const로 만들자)
5. 변수는 의미 있는 이름을 짓자.
```

# 함수의 이해 7번

- 동일한 코드가 2번 이상 반복되면 함수를 만들려고 노력하자.
- 반복은 되지 않더라도 하나의 기능이 너무 복잡하면 함수를 만들려고 노력하자.
- 복잡하지는 않는데 코드가 너무 길어지면 함수로 묶어주려고 노력하자.
- 실행의 결과가 그때, 그때 다른 경우에도 함수를 만들자.

2. 왜 화살표 함수를 만들지?

- 트랜드를 쫓아가자.
- this 를 정확히 지정하기 위해서 활용하면
- 코드가 해석하기 더 어려워진다.

```js
function say() {
  console.log("안녕", this);
}
```

: step 1.

```js
say() => {
  console.log("안녕", this);
}
```

: step 2.

```js
const say = () => {
  console.log("안녕", this);
};
```

: 매개 변수가 있는 경우

```js
function say(_who) {
  console.log("안녕", _who, this);
}
```

: step 1.

```js
function say(_who) {
  console.log("안녕", _who, this);
}
```

: step 2.

```js
const say = (_who) => {
  console.log("안녕", _who, this);
};
```

- this 를 정확히 지정하기 위해서 활용된다.
  : 화살표 함수를 사용할 때 일반적으로 큰 고민없이 사용하면 되지만,
  : 함수 안에 this를 작성하면 상황이 달라진다.
  : 화살표 함수에서 this는 window를 가리킨다.
  : 결론. 화살표 함수에서 this를 사용한다면 console.log(this); 확인 필수!
  : 화살표 함수는 예전 일반 함수에서 window를 참조하지 못하는 문제를 해결한다.

```js
// this의 차이
const btWrap = document.querySelector(".bt-wrap");
// 일반 함수는 작성된 곳을 가리키고
btWrap.addEventListener("click", function () {
  console.log(this);
});
// 화살표 함수는 window를 가리킨다.
btWrap.addEventListener("click", () => {
  console.log(this);
});
```

# 배열의 이해

- [요소, 요소, 요소, 요소]
  : 요소로 담을 수 있는 자료형은 7가지.
- 배열의 속성(배열을 위한 특별한 변수)는 1개가 있다.
  : length 가 있다. (요소의 개수)
- 배열의 메소드(배열을 위한 특별한 함수)는 정말 많다.
- 상당히 많은 메소드(배열을 위한 함수)가 있다.
- 배열.forEach((요소)=>{}), 배열.map((요소)=>{}), 배열.filter((요소)=>{}), 배열.find((요소)=>{})
- 배열의 요소를 하나씩 접근해서 활용하기
- 카멜케이스를 사용해야 한다. ( 배열.forEach() )

```js
// html 을 제어하므로
window.addEventListener("load", function () {
  //할일
  const dataUrl = "./apis/news.json";
  fetch(dataUrl)
    .then((response) => {
      //   console.log(response);
      const result = response.json();
      return result;
    })
    .then((result) => {
      //   console.log(result);
      // 할일작성
      // 전체 html 저장용 일반 변수
      let allTag = "";
      const news = document.querySelector("#news");

      // for (let i = 0; i < result.length; i++) {
      //   const obj = result[i];
      //   const tag = `<a href=${obj.link} class="list-box">
      //     <div class="list-box-img br-20" style="background: url('./images/${obj.imgpath}') no-repeat center; background-size: cover"></div>
      //     <div class="list-box-cate">
      //       <img src="./images/icon/${obj.icon}" alt="${obj.category}" />
      //       <span style="color:${obj.txtcolor};">${obj.category}</span>
      //     </div>
      //     <p class="list-box-title">${obj.title}</p>
      //     <span class="list-box-day">${obj.day}</span>
      //   </a>`;

      //   allTag = allTag + tag;
      // }

      // 배열이라면 반복하자.
      result.forEach((item) => {
        const tag = `<a href=${item.link} class="list-box">
        <div class="list-box-img br-20" style="background: url('./images/${item.imgpath}') no-repeat center; background-size: cover"></div>
        <div class="list-box-cate">
          <img src="./images/icon/${item.icon}" alt="${item.category}" />
          <span style="color:${item.txtcolor};">${item.category}</span>
        </div>
        <p class="list-box-title">${item.title}</p>
        <span class="list-box-day">${item.day}</span>
        </a>`;
        allTag = allTag + tag;
      });

      news.innerHTML = allTag;
    })
    .catch((error) => {
      console.log(error);
    });
});
```
