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

# Swiper Slide 적용해 보기

- _Slide를 직접 코딩하지 마세요_
- 사용법을 배운다.
- [Swiper](https://swiperjs.com/), [Slick](https://kenwheeler.github.io/slick/), [BxSlider](https://bxslider.com/)가 있다.

## 1. Swiper 슬라이드 적용시 주의사항

- html 로드 완료 및 이미지 로드 완료 후 실행 권장.

```js
window.addEventListener("load", function () {
  // 실제 슬라이드 코드 배치하자.
});
```
