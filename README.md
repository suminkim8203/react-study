# 리액트 컴포넌트

## 1.0. 컴포넌트를 왜 생성하는가?

- 프로젝트 규모에 따라 협업이 필요로 함.
- 기능별로 html, css, js 가 별도로 관리 필요.

## 1.1. 컴포넌트에 배치되는 내용

- JSX 가 배치된다. (리액트용 HTML 태그 class => className)
- css 가 배치된다. ( background: url(경로문제) )
- js 를 배치된다.

## 1.2. 이미지를 배치하는 2가지 경우(주의사항)

- 태그에 이미지를 배치한 경우
  : public/images 폴더를 참조합니다.

```html
<img src="./images/etc/logo-kakao.png" />
```

- css 배경으로 이미지를 배치한 경우
  : src/images 폴더를 참조합니다.
  : css 파일을 js 컴포넌트에서 사용하면 webpack 이 압축한다.

```css
background: url("../images/icon/icon-search.png");
```

## 1.3. js를 React로 마이그레이션 진행

### 1.3.1. load 가 useEffect로 변경

```js
window.addEventListener("load", function () {});

useEffect(() => {
  return () => {};
}, []);
```

### 1.3.2. querySelector가 useRef(null)로 변경

```js
const tag = document.querySelector(".bt");

const tag = useRef(null);

useEffect(() => {
  // tag.current로 접근
  return () => {};
}, []);

<div ref={tag}> </div>;
```

# JS 14 장

```txt
// var : 값을 담을 공간을 마련해줘.....
  // var 이름 : 값을 담은 공간에 꼬리표를 붙여줘.
  var age = 15;
  var nickName = "hong";
  function go(){
  }
  console.log(age)
  console.log(window.age)

  모듈(기능별 파일코드)은 import/export 문법을 써서 변수 범위를 설정한다.

 class 장을 보아야 해요.

  외부에서 변수 및 함수에 접근할 수 있는 권한
  public    : 외부 어떤 곳에서도 사용할 수 있다.
  private   : 외부에서 절대로 사용할 수 없다.
  protected : 허용한 대상만 사용할 수 있다.
```

# js 15장

```txt
let, const 키워드와 블록 레벨 스코프

var 사용하지 말자!

const 사용할 때 오해의 소지가 있는 경우

ex)

const는 절대로 값이 변하지 않기 때문에,

값을 변경하려고 하면 에러가 난다.

const age = 15;

age = 100;  // error

const 객체 ={ } 오해의 소지가 발생한다.

const member = { } // 이미 주소는 고정이 되어 버렸다.

member = “안녕” // 주소를 바꾸는 것이기 때문에 const에 위배된다. 에러.

// 하지만 아래는 주소를 교체하는 것이 아니고, 안쪽의 연결된 내용을 수정한다.

member.age = 100;

member[”nicName”] = “kdhong”;

변수를 만들 때

const로 만들고 난 후, 오류가 발생하면 let으로 변경해서 만든다.

const 변수이름 : 값을 고정시키겠다.

let 변수이름 : 값이 수시로 바뀐다.
```

# 실 업무에서 알아야 하는 상식

- nvm (node Version Manager) 설치 및 활용
  : https://github.com/coreybutler/nvm-windows/releases
  : nvm-setup.exe 설치
  : 설치 버전 확인 `nvm -v`
  : 설치 가능한 버전 목록 `nvm list available`
  : 설치하기 `nvm install 버전`
  : 현재 사용중인 Node 버전 확인하기 `node -v`
  : 현재 설치된 Node 목록 확인 `nvm ls`
  : 사용할 Node 버전 선택하기 `nvm use 버전`
  : Node 설치된 경로 알아보기 `which node`
  : 설치된 Node 삭제하기 `nvm uninstall 버전`

- npm 보다는 yarn 선호
  : Node Package Manager (node_modules)
  : package.json의 dependencies 목록을 참조
  : npm이 가끔 다운로드 중 오류가 발생하고, 소스가 깨지는 현상 존재.
  : ex. 네이버 Toast UI 등
  : npm 보다 안정적인 package 관리를 위해서 yarn을 활용.
  : `npm install -g yarn`
  : `yarn --version`

- favicon 만들기(디자이너 담당)
  : https://realfavicongenerator.net/

- ::before, ::after 샘플
  : css로 내용 만들기

```html
<body>
  <style>
    .wrap {
      position: relative;
      width: 100%;
      height: 400px;
      background: skyblue;
      margin: 100px auto;
      padding: 50px;
    }
    .box {
      width: 100px;
      height: 100px;
      margin: 0 auto;
      background: pink;
      text-align: center;
    }
    .box span::before {
      display: inline-block;
      content: "";
      width: 10px;
      height: 10px;
      background-color: red;
    }
    .box span::after {
      display: inline-block;
      content: "";
      width: 10px;
      height: 10px;
      background-color: blue;
    }
  </style>
  <div class="wrap">
    <div class="box">
      <span>안녕</span>
    </div>
  </div>
</body>
```

# js 16장

```txt
- Property Attribute (get, set, 불변객체(freeze))


const Obj = {}

Obj.[[prototype]] // 이렇게 정의는 되어도 우리는 사용할 수 없다.
Obj.__proto__     // 이렇게 접근이 가능하도록 개방됨.



const Person = {
	age: 10
}
Person.nickName = "홍길동";

console.log(Person.age); // 개발자가 활용
console.log(Person.nickName); // 개발자가 활용

Person.age // [[value]] ===> true,

Person.job = "학생";
Person.age // [[writable]] ===> true,

// 반복을 통해서 요소들을 출력할 수 있다.
Person.age // [[enumarable]] ===> true,

Person.age = 10000;
Person.age // [[configurable]] ===> true,



const who = {} // const 적용시 불안정하다
who = "안녕" // 변경 불가

who.age = 100; // 막을 방법이 없다.


객체 변경 금지 (완벽하기 막을 수 없기 때문)

: 객체를 복사해서 사용

: lodash 라이브러리 활용 (https://lodash.com/docs/#cloneDeep)

객체 만드는 방법

: 객체 리터럴 {}
: 함수로 객체 만드는 방법 (4가지)
```

# React useState 정리

```txt
1. 리액트용 변수(useState)는 재렌더링시 표현된다.
2. useState는 컴포넌트에서만 작성할 수 있다.
3. useState는 비동기이므로 즉시 참조할 수 없다.
4. useState에 직접 값을 변경할 수 없다.


const [age, setAge] = useState(0);
age = 100; (이런 식으로 접근은 불가능)


5. useState에서 현재값을 참조하고 즉시 갱신을 하려면 함수를 활용하여 업데이트 한다.


const [age, setAge] = useState(0);
setAge(age++); // 1이 되지 않는다. 즉, 즉시 갱신되지 않는다.
console.log(age);
// 우리는 1 증가한 값을 기대함. 하지만 값은 예전의 것 유지




setIsOpen((이전값) => {return 새로운값;});


6. useState에서 기존값 참조 후 직접 값 갱신 리턴 받아서 바로 사용하고 싶을 때.

const [age, setAge] = useState(0);
setAge(age++); // 기존 방식 (새로운 값 안 나옴)
setAge( 이전값 => { return 새로운 값 } ) // 함수 방식(새로운 값 나옴)
setAge( prev => { return prev+1 } ) // 함수 방식(새로운 값 나옴)
```

# js 17장

```txt
17. 생성자 함수에 의한 객체 생성
- 객체?

    : 객체를 만든다는 말은, 데이터를 설계하는 것.

    : ex. 유아제품을 판매하는 서비스에서 제품을 표현한다면?

    : 여러 개의 데이터와 여러 개의 기능을 묶어서
      마치 데이터 종류처럼 사용할 수 있다는 장점



하나의 이름으로 {
	데이터,
	데이터,
	데이터,
	데이터,
	기능,
	기능...
	...
}


const Person = {
	age: 10,
	nickName: "홍길동"
}

Person의 데이터 타입(종류)
- 객체: Person ===> {age: number, nickName: string}


객체는 다양한 자료를 묶어서 이름 한 개로 표현이 가능하다는 점에서 좋다.

만드는 방법 → 2가지 형태(리터럴, 함수)를 띈다

1. **객체 리터럴**
const Obj = { name: “물잔”, count: 10 }
const Good_1 = { name: “물잔”, count: 10, descript: “df” }
const Good_2 = { name: “물잔”, count: 10, descript: “df” }
…
*만약 제품이 100개라면 객체를 100개 만들어 주어야 한다.*
    1. 장점: 가독성, 관리
    2. 단점: CRUD

2. **객체 생성자(constructor) 함수(Object) 사용**

    Object() : 함수 call
    new Object()
    : new 함수 call.
    : new는 문법 Object() 객체 생성

    2-1. 관례

    : 개발자가 함수의 모양만 봐도 객체생성함수/일반함수의 구별이 가능하다.

    Swiper()
    Axios()

    : 일반적으로 call 하는 게 아니다를 표현한다면

    new Swiper()
    new Axios()

    2-2. 함수 안쪽의 this는 call 방식에 따라서 this의 값이 다르다


    function Foo(){
    	// this
    	goto: function () {
    					this
    					}
    }
    Foo(); // this는 window

    new Foo(); // this는 만들어질 객체 (인스턴스: 앞으로 보관될 것)

    const go = new Food()
    go.goto(); // 여기서 this는 . 앞의 것. 즉 go를 가리킨다.



2-3. 반드시 용도를 구분!
함수 call과 new 객체 생성자 함수를 구분해서 리턴해야 한다.

: 일반 함수는 자유롭게 return 값;

: 객체 생성용 함수는 return 적지 말 것.

2-4. constructor 함수 /  none-constructor 함수

: 모든 함수는 형태는 어디에 작성을 하건 new 사용가능 (constructor)

: but, ES6 도입 후 new 사용 못하는 함수
(화살표 함수, 축약 메소드 함수, none-constructor)

2-5. new로 생성된 객체(인스턴스)의 원본확인 연산자 instanceof

3. **클래스 함수 사용**
```

```txt
매개변수이름은 관례상 props라고 작성

`<Header clickMbbt = {clickMbbt} age = {10}></Header>`

참조법 1

const MbHeader = (props) => {
	// 참조가능, 함수
	props.clickMbbt()
	// 참조가능, 숫자
	props.age()
	retrun(...)
}


참조법 2

const MbHeader = (props) => {
	const clickMbbt = props.clickMbbt;
	// 참조가능, 함수.
	clickMbbt();
	retrun(...)
}


참조법 3 <추천!>

const MbHeader = ({clickMbbt, age}) => {
	// 참조가능, 함수.
	clickMbbt();
	// 참조가능, 숫자
	age;

	retrun(...)
}


1. 리액트용 변수 useState 이해

    : 컴포넌트에 새로고침을 진행하도록 한다. (useEffect를 강제 실행)


- useEffect 용도?

    : 컴포넌트가 생성될 때 실행하고 싶은 것


    useEffect( () => {
    	// 한 번만 실행
    }, []); // []에 아무것도 작성하지 않는다면.


    : 컴포넌트가 제거될 때 실행하고 싶은 것


    useEffect( () => {
    	return () => {
    		// 제거될 때 한 번만 실행한다.
    	}
    }, []);


    : 컴포넌트가 업데이트 될 때 실행하고 싶은 것


    useEffect( () => {
    }, [ 리액트변수 ]); // 작성시, 해당 상태가 내용이 바뀌면 화면 고정



: 리액트 변수 만들기


const [get이름, set이름] = useState(초기값);
 const [mbMenuOpen, setMbMenuOpen] = useState(false);


: 리액트 변수 값 고치기

- 이러면 안 됨.


get이름 = 값을 직접 입력은 반영안됨.
mbMenuOpen = true;  // 이렇게 하면 반영이 안 됨.


- 함수가 종료되어야 업데이트 된 결과를 참조할 수 있다.
- 2가지 방식


set 이름 (새로운 값);
set 이름 ( (현재값) => {
			return 새로운 값;
			}
}


예제 1


const clickMbbt = () => {
	setMbMenuOpen(새로운값);
};


예제 2

const clickMbbt = () => {
	setMbMenuOpen( (기존값) => { return 새로운값 } );
};

// 활용 예시
const clickMbbt = () => {
	setMbMenuOpen( (prev) => {
		return !prev;
		});
};
```

# js 18장

```txt
함수와 일급 객체
- 일급객체?
    - 익명 리터럴로 생성이 가능해야 인정
    - 데이터 자료로 저장이 가능한지

    const go = function () {}
    const obj = {}


    - 함수(매개변수) 및 리턴 가능한지

    function say ( _val ){}
    say(go)
    say(obj)



유사 배열 객체

이터러블 (순회. 즉, 반복이 가능한)

매개변수에 … 찍어서 배열로 만들 수 있다.

**→ Rest 파라미터**

교재 225p 예제 18-8 참조

- _ _ proto_ _

: 객체의 prototype 요소에 접근할 때 작성

- Prototype

: 상속 (extension)을 구현하기 위해 활용

: 객체 생성자 함수로 호출할 수 있는 함수객체만이 가지고 있는 속성이다.

: 객체 생성자 함수를 호출하면 인스턴스 변수를 만든다

`const slide = new Swiper();`

slide에는 prototype이라는 객체를 만들어 준다.
```

# js 19장

```txt
프로토타입

*: 추후 유명한 소스를 분석해야 할 때가 오기 때문에 문법을 알아야 한다!*

1. _ _ proto_ _

JS에서 객체의 기본 속성을 알고 싶을 때

_ _ proto_ _로 접근한다. (사용 권장 x)

1. prototype

JS에서 직접 기본 속성을 만들고 싶다.

만든다는 의미: 함수

함수는 객체를 생성하는 객체 생성자 함수를 말한다.

이때 나는 객체의 기본 속성을 만들고 싶다면

`prototype.속성명 = 값;`

1. class

객체를 생성하는 문법 중 하나.

ES6에서 도입

1. 객체 지향 프로그래밍 (OOP_Oriented Object Programming)

    : 실세계에 존재하는 대상에 대해서 특징과 성질, 행동을 코드로 표현하겠다.

    : pg에서 활용할 특징, 행동만 별도로 뽑아서 설계를 추상화한다.

    : 특징 혹은 성질을 Properties, Attribute

    : 행동을 Behavior, Method

    : 객체는 Property, Method를 가진 데이터



const Circle = {
	radius: 3, // 속성명: 속성값. 상태
	getArea: function(){}, // method: method기능
	getArea()=>{} // method: method기능
}


1. 상속

    : 하나의 객체의 속성, 메소드를 다른 객체가 사용할 수 있도록 허용한다.

    : 그래서 똑같은 기능/속성을 다시 만들지 않아도 된다.


- 아래 예제는 new 실행시 불필요하게 say 메서드가 만들어진다.


function 말해봐(단어) {
	this.word = 단어;
	this.say = function(){
		console.log(this.word)
	}
}

const 홍길동 = new 말해봐 ("밥 먹었니?")
const 둘리 = new 말해봐("뿡뿡")



function 말해봐(단어) {
	this.word = 단어;
}

말해봐.prototype.say = function(){
		console.log(this.word)
}

const 홍길동 = new 말해봐 ("밥 먹었니?")
const 둘리 = new 말해봐("뿡뿡")

홍길동.say();
둘리.say();


1. _ _proto_ _

    : JS의 모든 객체가 가진 기본값


1. prototype

    : 오로지 함수 객체에서만 존재하는 것.

    : 그래서 우리는 new를 통해서 생성하므로 적극적으로 활용을 해 진행한다.


1. 오버라이딩

    : prototype 기능 덮어쓰기

    : 똑같은 이름으로 정의한다.

2. instanceof

    : 여기서 instance란?
    - new로 만들어진 변수

    : instance of 어떤 객체

    : 인스턴스변수 instanceof 객체생성자함수

    ex)

    홍길동 instanceof 사람 ==⇒ true

    홍길동 instanceof 동물 ==⇒ true

    홍길동 instanceof 개 ==⇒ false

3. 정적인 property / method

    : 정적 (static)

    : 정적이라는 말은 객체생성자 함수에 고정시킨 속성과 메소드


    ex)

    function Dog (name) {
    	this.name = name;
    }
    Dog.prototype.cry = function(){console.log("멍멍")}

    // 정적인 속성(property)
    Dog.eye = 2;

    new 댕댕이 = new Dog("돌돌이")
    댕댕이.cry(); // "멍멍"
    댕댕이.eye; // undefined
    Dog.eye; // 정적인 static 속성

    댕댕이 instanceof Dog; // true


    1. in 연산자

        : 프로퍼티(키명) 있니?

    2. **for … in 문**

        : `for (변수명 in 객체) {...}`

        : 배열인 경우만 조심해서 사용하자

        - 배열도 객체이기 때문

        - 배열인 경우는 for … in 말고 forEach를 사용하자.


    1. for … of 문

        : 앞으로 자주 사용하자. 가능하면 반복문에서
```

# 리액트 프로젝트 셋팅

- 모든 프로젝트에서 공통 적용

## 1. 단계

### 1.1 소문자 프로젝트 폴더 생성

`npx create-react-app ./ --template typescript`

### 1.2 GitHub 생성

### 1.3 프로젝트 폴더와 깃허브 연결

### 1.4 개발환경 세팅

- eslint 설정
  : js 문법을 안내해 준다.
  : 오류에 대해 설명해 준다.
  : 미리 문제발생할 소지가 있는 부분을 안내해 준다.
  : 즉, 코딩에 도움을 주는 도구이다.
  : 프로젝트에서 전체 세팅을 하는 것이 관례.
  : 아래의 순서를 준수한다.
  : `npm i`
  : `npm install eslint-plugin-react@latest --save-dev`
  : `npm install eslint@8 --save-dev`
  : `npx eslint --init`

- prettier 설정
  : 문서포맷 정리
  : 들여쓰기, 따옴표, 세미콜론 등등등.
  : `npm install --save-dev --exact prettier`
  : 환경 설정 파일을 / 에 만든다
  : 파일명은 약속이 되어 있다.
  : `.prettierrc.json`

  ```json
  {
    "singleQuote": false,
    "semi": true,
    "useTabs": false,
    "tabWidth": 2,
    "trailingComma": "all",
    "printWidth": 80,
    "arrowParens": "avoid",
    "endOfLine": "auto"
  }
  ```

- eslint & prettier 설정
  : eslint에서 prettier의 설정 안내해 주도록 연결
  `npm install eslint-config-prettier --save-dev`

- .eslintrc.js 수정으로 마무리

```js
module.exports = {
  env: {
    browser: true,
    es2021: true,
  },
  extends: ["eslint:recommended", "plugin:react/recommended", "prettier"],
  overrides: [
    {
      env: {
        node: true,
      },
      files: [".eslintrc.{js,cjs}"],
      parserOptions: {
        sourceType: "script",
      },
    },
  ],
  parserOptions: {
    ecmaVersion: "latest",
    sourceType: "module",
  },
  plugins: ["react"],
  rules: {},
};
```

### 1.5 관련 라이브러리 설치

- axios
- react router dom
- emotion

### 1.6 기본 퍼블리싱

- public/www 폴더 안에 작업 진행

### 1.7 기본 리액트 작업

# js 21장

```txt
빌트인 객체
빌트인 ( 미리 작성되어 있는 JS )

JS라면 가지고 있어야 하는 내용 (MS, Apple, Google… 개발자등이 작성…)

- 웹브라우저
- Node.js


const go = "안녕"; // 기본(원시)


. 찍고 접근하면 속성에 접근 (객체가 아닌데 어떻게?)


const go = new String("안녕");

go.length;
go["length"];


**활용도 높은 세 가지**

`isNaN`

`parseInt();`

`값.toString();`

- http
  - html로 해석하기로 약속한 프로토콜(약속)
- ftp
  - file을 주고 받기로 약속한 프로토콜
- smtp
  - simple male transper protocol

BE에서

패스(경로/주소)는 http://localhost:3000/docs/search 이용

- cate라는 변수에는 카테고리
- lang라는 변수에는 국가
- name라는 변수에는 단어를 보내주세요.

그러면 결과를 리턴해 주겠다.

http://localhost:3000/docs/search?cate=값&lang=값name=값

?앞은 패스

?뒤는 쿼리스트링

```

# js 22장

```txt
this

객체는 상태(프로퍼티와 메서드)를 가지고 있다.

객체는 독특한 데이터 종류이다.

메소드는

- 자기가 코딩된 객체의 property를 변경할 수 있다.
- 속성을 변경하려면 메소드는 자기가 속한 객체(this로 찾을 수 있다)를 알 수 있어야 한다.

**this는 함수 호출 방식에 따라 그때그때 결정이 된다.**

1. 호출 방식

3.1 일반 함수 호출


function Go(){
	// this?
}
Go(); // window


3.2 메소드 호출 방식


const obj = {
	gogo(){
		this?
	}
}
obj.gogo(); // obj


3.3 생성자 함수 호출 방식


function Go() {
	// this?
}
const who = new Go(); // who


3.4 간접적으로 접근해서 호출 (x)


Function.prototype.call();
Function.prototype.apply();
Function.prototype.bind();


1. 주의하자.

`setTimeout` : (시간이 지나면 함수 호출)

`setInterval` : (일정한 시간마다 지나면 함수 호출)


var value = 1;

const obj = {
	value: 100;
	foo () {
		console.log(this) // obj
		const gogo = this;

		// setTimeout(기능, 시간)
		setTimeout(funtion () {
				console.log(this) // 일반함수라서 window를 가리킨다.
				this.value;
			}, 1000)
	}
}

// 메소드로 호출했다.
// 지금까지의 얘기로는 this는 obj를 가리킨다고 알고 있었지만,
obj.foo(); // obj, window


- this는 코딩된 위치를 기준으로 바인딩(연결) 한다.

1. 결론
- 일반 함수 호출은 this가 window를 대상으로 한다.
- 객체를 가리키고 싶다면(참조한다면) 화살표 함수를 사용하자.
```

# js 23장

```txt
**실행 컨텍스트를 알면 좋은 점**

1. JS를 실행하는 플레이어라고 이해하자

    ex. mp4 영상이 있다면 플레이어 소프트웨어 실행 과정이 어떨까?

2. JS가 변수(식별자: 구분자)와 변수(식별자: 구분자)를 구분하고 어떻게 찾아서 사용하는가에 대한 이해를 돕는다.
3. 호이스팅의 과정을 알 수 있다. (var 또는 function 사용시)


1번줄 console.log(age) // 에러가 일어나지 않는다.
2번줄 go() // 에러가 일어나지 않는다.
...
...
100번줄 var age = 15;
130번줄 function go(){}


1. Closer에 대한 과정을 알 수 있다.

    함수가 종료되었는데 어떻게 지역변수(함수 안에 만든 변수)가 살아있는지

2. Task 큐 + 이벤트 핸들러의 작동방식 이해

---

**JS play를 할 수 있는 환경은 두 가지가 있다.**

- Web Browser
- Node.js

1. 소스 코드가 실행 시 player는 준비한다.
    1. 분류 (평가작업)
        1. 전역코드(공간 마련)
        2. 함수코드
        3. eval : 글자를 자바스크립트로 인정해서 실행한다. (하면 안 된다.)
        4. 모듈 코드 : export, import등 .js 파일내에 작성 되었구나.
    2. 실행준비 (player)
        1. 1단계로 코드를 보고 평가를 한다
        2. 2단계로 실행한다.
    3. 렉시컬 환경은 어떻게 쌓여있는 스택들 간에 변수, 함수를 찾아서 사용하는가.
        1. Scope가 결정되어지면 체인(찾아가는 연결)이 관리한다.
            - Global Scope : window
            - Local Scope : { }


**비동기의 이해 (대표적으로 addEventListner/fetch/axios … )**

- bt.addEventListener(”click”, function(){…})
- fetch(url).then(fucntion(){}).catch(function(){})

10번줄 fetch(”path”).then( res ⇒ console.log(res))

…

20번줄 say();
```

# Acios

## 1. axios를 연습할 때

- [josn-server](https://www.npmjs.com/package/json-server)
- [참조자료](https://poiemaweb.com/json-server)

## 2. 서버 구축 과정

- D: 드라이브에 server 폴더를 만든다.
- VSCode에서 프로젝트 등록을 한다. (리액트와 상관없음)

## 3. Node.js 프로젝트 생성하기

- `npm init`

## 4. json-server npm 설치

- `npm install -g json-server`
- db.json 파일 생성

## 5. json-server 실행

- `json-server --watch db.json`
- 리액트가 3000 포트를 사용하고 있다.
- json-server도 3000 포트를 사용하므로 충돌 발생함.
- 그래서 아래 버전으로 설치해야 한다.
- `json-server --watch db.json --port 5000`
- json-server 포트를 5000번으로 변경

## 6. package.json에 script 명령어 추가하기

```json
{
  "name": "server",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "start": "json-server --watch db.json --port 5000"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "json-server": "^1.0.0-beta.0"
  }
}
```

## 7. API 테스트하기

- CRUD 테스트 (크러드)
  : Create (POST)
  : Read (GET)
  : Update (PUT/Petch)
  : Delete (DELETE)
- Postman (웹 API 테스트시 일반적 사용)
- Swagger (웹 API 테스트시 별도로 BE에서 셋팅)
- Web Browser (웹 프로젝트 CORS 에러 발생함.)
  : package.json에 "proxy": "주소" 를 작성해야 한다.

## 8. Axios 활용

- [axios](https://axios-http.com/kr/docs/intro)
- `npm install axios`

## 8.1. axios 폴더 추천

- /src/apis 폴더 생성
- /src/apis/config.js

```js
// 서버 주소
export const SERVER_URL = "http://localhost:5000";
```

- /src/apis/todos.js

# js 24장

```txt
클로저

1. 실행 컨텍스트
- 코딩을 했다.

    JS 플레이어 (Web Browser) 에서는 2단계 진행

    - 1단계

        : 소스 코드 분석 단계 (전역/함수/모듈)

        : 변수 목록/함수 목록을 관리

    - 2단계

        : 코드 실행 단계 (렉시컬은 변수 찾기 범위 설정)

        : 변수/함수들에 대한 참조를 결정지어 버린다.

        : 참조한 내용들의 정보를 절대로 바꾸지 않는다.

2. 클로저
- 함수와 그 함수가 선언된(코딩된) 렉시컬 환경과의 조합이다.

    : JS는 함수를 호출, 즉 Call이 아니고 작성을 하는 순간 모든 참조가 결정된다. (렉시컬 범위가 세팅 완료)

- 외부 렉시컬 환경에 대한 참조도 저장해 둔다.

3. 함수 객체
- 함수도 객체라서 속성이 있다.

    [[Environment]] : 환경 슬롯이 이미 코딩된다.

    : 환경 슬롯이 이미 코딩된다.

    : 여기에는 렉시컬 환경 참조, 즉 상위 스코프를 기억한다.

4. 클로저의 조건

4-1. 함수 안에 함수를 만든다.

function Outer(){
	function gogo(){
	}
}


4-2. 함수 안에 함수를 만든 후 내부에 만든 함수를 리턴한다.

function Outer(){
	function gogo(){
	}
	return gogo;
}


4-3. React 예

const Header = function(){
	const handleClick = function(){
	}
	return ( <div></div> );
}


4-4. 외부 함수 보다 중첩 함수가 더 오래 유지되는 경우

: 중첩 함수는 이미 종료되어 버린 외부 함수의 변수를 참조할 수 있다.

function Out(){
	let age = 10;
	function In(){
		return age;
	}
	return In;
}

const gogo = Out();
gogo();

age는 함수가 종료되어 사라졌지만 함수는 gogo에 담았기 때문에 살아있다.


5. 클로저 활용

let num = 0;
const add = function(){
	return num++;
}
add()
num = -5000
add()
add()


- 함부로 접근해서 변수의 상태를 바꾸지 못하게 할 수 없을까?

    : 함수의 지역변수로 만들기


const 가져가 = function(){
	let 돈 = 100;
	return 돈 --;
}

const 남은돈 = 가져가(); // 99
const 남은돈 = 가져가(); // 99

console.log(돈) // 에러
// 돈이라는 변수에 접근할 수 없다.


- 외부에서 함수에 만든 지역 변수에 접근할 수 없을까?

const 가져가 = function(){
	let 돈 = 100;
	function 돈빼기(){
		return 돈--
	}
	return 돈빼기;
}

const 결과 = 가져가();
결과();
결과();
결과();


6. 클로저란?
    1. 함수에서 내부 함수를 리턴한다.
    2. 내부 함수는 외부의 변수를 사용한다.
    3. 이렇게 하면 데이터를 외부에서 접근할 수 없으므로 데이터를 은닉할 수 있다.
    4. 데이터에 접근하는 내부 함수를 통해서만 접근할 수 있으므로 안전하다.

    function 회원정보(){
    	let 사용자레벨 = 1; 회원
    	return function(){
    		return 사용자레벨++;
    	}
    }
    const 회원업데이트 = 회원정보();
    회원업데이트();
    회원업데이트();
    회원업데이트();


7. 고차함수
- 면접볼 때 자주 나오는 내용
- 함수에 함수를 매개변수로 전달한다.

배열.map(고차함수);
배열.map( function(item, index, arr){} )


8. 클로저
- 목적은 데이터를 안전하게 보관한다. 즉, 외부에서 함부로 접근할 수 없게 한다.
- 데이터를 변경해야 할 경우 내부 함수로 변경한다.

function 은행(){
	let 잔고 = 0;
	return {
		입금(_money){
			return 잔고 + _money
		}
		출금(_money){
			return 잔고 - _money
		}
	}
}

const 홍길동 = new 은행();
홍길동.입금(100)
홍길동.출금(50)

```
