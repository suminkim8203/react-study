# 프로젝트 생성

## 1. 기본사항
- 깃허브에 먼저 소문자로 프로젝트명을 만든다.
- 깃허브에 설명은 반드시 작성한다.
- PC에 동일한 소문자로 폴더를 만든다.

### 1.1. 리액트 및 퍼블리싱 프로젝트 생성
- VSCode를 실행한다.
- PC에 만든 폴더를 드래그 해서 등록한다.
- 명령어를 통하여 기본 파일럿 프로젝트를 생성한다.
 : `npm create-react-app ./`를 실행한다.
 : Node.js 권장 설치버전 (https://nodejs.org/en/download)
 : Node.js는 20.12.0 (LTS) 버전을 선택.
 : 설치는 기본 경로 그대로 설치. 다른 경로에 설치할 시 오류 발생 가능성 있음.
 : npm 오류가 발생할 시 에러 넘버 구글링 (ex. -4058 Error)
 : `npm uninstall -g create-react-app`
 : `npm install -g create-react-app`
 : 위와 같은 오류 발생시 위의 사항을 실행한 후
 : `npm create-react-app ./`를 실행한다.

### 1.2. 테스트 해보기
- `npm run start` 실행해서 확인한다.
- 터미널에서 `ctrl + C`로 미리보기 종료한다.

## 2. 작업순서 기준

### 2.1. 웹 서비스 개발 순서(프론트)
- 퍼블리싱부터 진행
- 리액트 진행 (필요시)
- 타입스크립트 진행 (필요시)
- Next.js 진행 (필요시)

### 2.2. 퍼블리싱 해보기
- 생성된 폴더 최상위를 `Root` 라고 부른다.
- 코드상으로는 `/` 로 표현.
- 퍼블리싱은 `/public` 폴더에 `www` 폴더 생성후 진행.
- 퍼블리싱 기본 폴더 생성 진행.
 : images 폴더 생성 (.png, .jpg, .gif, .svg )
 : css 폴더 생성 (.css 파일들을 보관)
 : js 폴더 생성 (.js 파일들을 보관)
 : assets 폴더 생성 (문서, 동영상, 디자인 원본(.psd)...)
 : index.html 파일 생성

### 2.3. index.html 기본구성
- `! + Tab` html 기본형이 제공된다. (스냅샷)
- lang="en"은 "ko"로 수정한다.
- title은 변경.
- 미리보기 (html 파일에서 마우스 오른쪽 Open With Live Server 선택)

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>카카오 브레인 블로그</title>
</head>
<body>
    
</body>
</html>
```

### 2.4. html 문서의 작업 순서