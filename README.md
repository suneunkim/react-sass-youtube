# SCSS를 이용한 유튜브 클론 프로젝트

이 프로젝트는 React와 SCSS CSS 연습을 위해 YouTube API를 이용해 메인 페이지, 비디오 페이지, 검색 페이지를 클론하는 프로젝트입니다.

## 사용 기술

- React
- SCSS
- YouTube API

## SCSS에서 @use와 @forward의 역할 및 사용 이유

- SCSS에서는 스타일을 모듈화하여 관리하기 위해 @use와 @forward를 활용합니다.
- 이를 통해 각 파일에서 불필요하게 여러 번 import하지 않고, 한 곳에서만 관리할 수 있습니다.

### SCSS 폴더 구조

- 각 폴더마다 index.scss를 생성하여 내부 SCSS 파일을 @forward로 한 번에 관리

- main.scss에서 모든 index.scss를 @use하여 스타일을 적용

```
scss/
│── abstracts/      # 변수, 믹스인, 함수 등을 포함
│   ├── _variables.scss
│   ├── _mixins.scss
│   ├── index.scss  # abstracts 내부 파일을 @forward
│
│── layout/         # 공통 레이아웃 스타일 (헤더, 푸터 등)
│   ├── _navBar
│   ├── _sideBar
│   ├── index.scss  # layout 내부 폴더의 파일을 @forward
│
│── pages/          # 개별 페이지 스타일
│   ├── _mainPage.scss
│   ├── _searchedVideoPage.scss
│   ├── _videoPage.scss
│   ├── index.scss  # pages 내부 파일을 @forward
│
├── main.scss       # 모든 index.scss를 불러와 최종적으로 스타일을 적용
```
