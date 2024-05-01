# Git 협업 과정 (순서를 꼭 지키자)

```txt


   - 팀원은 PC 에서 브랜치를 생성한다. !!!!!!
     git branch 아이디

   - 팀원은 PC 에서 브랜치로 이동한다.
      git switch 아이디

   - 리액트 프로젝트라서 js 소스들을 다운로드 및 설치 하셔야 해요
      npm i

   - 팀원은 PC 에서 작업하고
      git add .
      git commit
      git push 아이디

   - 팀원은 GitHub 에서 브랜치 확인 후 pull Request 요청한다.

   - 팀원은 대기한다.

   - 팀장은 pull Request 요청을 처리한다.

   - 팀장은 요청에 대해 처리후 feedback (슬랙) 준다.

   - 팀장이 소스 merge 끝났습니다. sync 받으셔요.

   - 팀원은 본인 깃허브 sync fork 클릭합니다.

   - 팀원은 작업 brach 제거한다.
     : git switch main
     : git branch -D 아이디

   - 팀원은 sync 이후에 소스를 다시 받는다.
     : git fetch
     : git merge origin/main
```

# js 12장

```txt
12. 함수
원시 데이터 ==⇒ 단일 값

복합 데이터 : 복잡한 속성, 메서드를 가진 객체 ==⇒ function, [ ], { }…

함수는 객체다

→ 함수는 객체의 문법을 따르는 값이다.

함수는 복합 데이터 형태의 값이다.

function 함수이름 (매개 변수) {

return 문장을 작성 (값을 반드시 출력: 표현식)

}

함수이름(인자) : 함수 호출, 함수 실행, 함수 콜…

리터럴?
: 할당된 값. ex) let a= 1; 1: 리터럴
→ js가 알아볼 수 있는 데이터 형태로 작성한 것.

const a =1; 숫자 리터럴

JS의 일급객체에 대해 말해보자.

1. 값처럼 변수에 할당할 수 있는가?
    1. const add = function( ) { }
2. 객체의 프로퍼티의 값으로 담을 수 있는가?
    1. const obj = { add : function ( ) }
3. 배열의 값으로 담을 수 있는가?
    1. const arr = [ 1, 2, 3, 4, 5, function( ) { }, { }, [ ] ]
4. 함수의 매개변수 값으로 전달할 수 있는가?
    1. function say ( 기능 ) {

        기능( );

        }


    const 안녕 = function( ) {

    console.log(”안녕하세요”)

    }

    say (안녕)

    say ( function( ) { console.log(”반가워요”) } )

- 함수가 객체를 생성하는 함수를 객체 생성자 함수라고 한다.
- JS의 함수에 전달되는 매개변수 목록을 arguments 라는 객체라고 한다.
- 함수의 매개변수로
    - 1. 원시 값을 인자로 전달하는 경우
    const age = 15;
    function grow ( _value ) {
       return _value + 5;
    }
    grow ( age );

    age는 변화가 없다. 값인 115가 전달된 것이지 age가 전달된 것이 아니기 때문.

    - 2. 함수의 객체를 인자로 전달하는 경우 (조심해야 하는 경우!)
    const person = { age : 10 }
    function growObj ( _who ) {
       _who.age = 150;
    }

    // 객체의 참조(주소) 값 전달
    growObj ( person );

    // 객체의 상태가 변경이 일어난다.

중첩 함수

function Outer ( ) {

function handelClick = ( ) ⇒ {

}

hanelClick ( );

return ( JSX 구문 )

;

콜백 함수

window.addEventListener ( “이벤트글자”, function( ) { } )

순수 함수

function add (a, b) {

return a + b;

}

비순수 함수

const age = 10;

function add (b) {

return age + b;

}
```

# js 13장

```txt
스코프(scope)란?

: 대상을 사용할 때 찾을 범위

대상? 함수, 변수, 클래스 등…

식별자를 검색할 때 사용하는 규칙

var 변수

let 변수 또는 const 변수의 차이가 크다.

// 설명으로 바깥쪽 (함수의 바깥쪽)을 통상 ‘전역(global) 스코프’라고 한다.

var age = 15;

function say( ) {

// 통상 ‘지역(local) 스코프'라고 한다.

console.log(age);

console.log(name); // undefiend

}

say( );  // ?

> 위 함수는 비순수 함수

—

var age = 15;

function say( ) {

var age = 100;

console.log(age);

}

say( );  // ?

> 위 함수는 순수 함수

앞으로 살펴볼 내용 예습!

let age = 1;

if (true) {

let age = 2;

if (true) {

let age = 3;

}

}

console.log(age);

let 을 사용하면 { } 중괄호 안은 다른 범위로 취급한다.

var age = 1;

if (true) {

var age = 2;

if (true) {

var age = 3;

}

}

console.log(age);

하지만 var를 사용하면 function을 사용하지 않으면 변수를 덮어쓴다.

렉시컬 환경 (실행과 작성위치)

JS는 렉시컬 스코프를 기본으로 한다.

: js는 대상이 코딩, 즉 작성할 때 스코프가 정해진다.

: 그때그때(실행할 때마다) 스코프가 달라지지 않는다.

```

# React 기초 1

```txt
0. 사전 준비
: node.js 설치(nvm을 통해서 버전 교체 가능)
: npm은 자동으로 설치된다.
: yarn은 직접 설치해야 한다.
: github에 repository 생성

1. 프로젝트 생성법
: 폴더명은 소문자로 (규칙)
: 리액트 프로젝트
`npx create-react-app ./ --template typescript`

2. 진행 순서
: public 폴더에 www 폴더 생성 후 퍼블리싱 작업 진행 및 테스트
: React js 버전으로 진행.  (CSR) 클라이언트 사이드 랜더링
: React ts 버전으로 진행.
: Next ts 버전으로 진행.  (SSR) 서버 사이드 랜더링

3. 프로젝트 내용 기본 파악하기
    1. node_modules

        : npm 또는 yarn으로 다운로드 받은 파일 보관 폴더

        : npm install 라이브러리명을 이용하여 다운로드 받고 활용

        : 만약 프로젝트가 라이브러리 등의 오류가 발생했다면
        - node_modules 폴더 삭제
        - package-lock.json 파일 삭제
        - 이후 `npm i` 재설치 (터미널)

        : 깃허브에 push 대상에서 제외하기 위해 .gitignore에 자동 입력된다.

    2. public 폴더
    - 꼭 기억하기. public 폴더는 압축 안 됨!!! Webpack에서 제외됨.

        : index.html

        - 최초 웹서비스 실행시 실행되는 파일명 (파일명 변경 불가)
        - lang=”ko” 수정
        - favicon 아이콘 수정
        - SEO 관련 내용 별도 추가 (네이버 검색, 구글 검색, GA4 적용 예정)
        - apple-touch-icon 아이콘 수정
        - title 내용 수정
        - manifest.json은 추후 내용 수정 필요

            https://web.dev/articles/add-manifest?hl=ko

        - id=”root”는 리액트 미리보기 및 결과물이 배치되는 장소

<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta name="theme-color" content="#000000" />
    <!-- SEO 적용 필요 : 네이버 검색 및 구글 검색 등록 예정, GA4 예정 -->
    <meta name="description" content="카카오 브레인 블로그 클론 코딩" />
    <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
    <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
    <title>카카오 브레인블로그</title>
  </head>
  <body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>
  </body>
</html>
```

: manifest.json

- https://web.dev/articles/add-manifest?hl=ko

```json
{
  "short_name": "카카오 브레인 블로그 클론코딩",
  "name": "카카오 브레인 블로그 클론코딩",
  "icons": [
    {
      "src": "favicon.ico",
      "sizes": "64x64 32x32 24x24 16x16",
      "type": "image/x-icon"
    },
    {
      "src": "logo192.png",
      "type": "image/png",
      "sizes": "192x192"
    },
    {
      "src": "logo512.png",
      "type": "image/png",
      "sizes": "512x512"
    }
  ],
  "start_url": ".",
  "display": "standalone",
  "theme_color": "#000000",
  "background_color": "#ffffff"
}
```

: robots.txt

- 검색엔진 로봇이 내용을 접근해서 보관하는 여부 설정
- 상세 경험은 네이버 및 구글 검색엔진 등록시 실습

  3.3 src 폴더

- webpack의 대상폴더
- index.js
  : 리액트 실행시 최초 실행되는 파일

  ```js
  import React from "react";
  import ReactDOM from "react-dom/client";
  import "./index.css";
  import App from "./App";
  // 아래 라이브러리는 구글의 웹 성능 리포트 기능
  // import reportWebVitals from './reportWebVitals';

  const root = ReactDOM.createRoot(document.getElementById("root"));
  root.render(
    // <React.StrictMode>
    <App />
    // </React.StrictMode>
  );

  // If you want to start measuring performance in your app, pass a function
  // to log results (for example: reportWebVitals(console.log))
  // or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
  // reportWebVitals();
  ```

- TDD 관련 파일 제거 (Test Driven Develop)
  : 테스트 주도 개발
  : App.test.js
  : setupTests.js

- 성능 측정 파일 제거
  : reportWebVitals.js

- App.js는 최초 화면에 보여지는 내용
  <br>

  3.4 .gitignore 파일

- 깃허브 파일 예외 사항 기재
- 폴더 및 파일 작성하면 제외된다.
- 추후 내용 작성 필요 (ex. 인증키)
  <br>

  3.5. package-lock.json

- node_modules 에서 사용된 라이브러리들의 버전 보관
  <br>

  3.6. package.json

- node.js 프로젝트 생성시 기초 정보 관리내용
- dependencies 항목이 중요하다.
  : 프로젝트에 실제 활용한 라이브러리 목록 (파악용도)
  : 개발 / 최종 빌드한 소스에 포함이 되는 라입러리들 목록
  : npm start 개발시 포함
  : npm build 배포시 포함
