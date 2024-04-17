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
