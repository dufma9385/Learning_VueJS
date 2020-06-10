# Vue JS
CDN = <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
## I 핵심
### 1. SPA
Single Page Application
- 페이지의 전환 없이(새로운 요청응답 없이) UI의 변화를 일으킬 수 있는 형태
- 왜?
    기존의 부분랜더링을 위한 flash사용을 줄이고 javascript 기반으로 사용하기 시작
    react, vue와 같은 자바스크립트 툴을 사용하지 않더라도 부분랜더링 가능(순수javascript)
  1. 사용자 편의를 위한 부분 랜더링
  2. 서버 리소스

### 2. MVVM
Model-View-ViewModel 의 구조를 가진다.
  (control대신에 viewModel)
- MVC(Model-View-Control)와의 비교

### 3. Declarative Programming
선언적 프로그래밍 <-> 명령형 프로그래밍
(Imperative Programming)
- 명령형(절차적): 변화를 단계적으로 명령하는 방식
  - Vanilla Javascript DOM 조작
- 선언형: 변화를 선언(그림 그리기)
  - 프레임 워크를 통한 조작

## II. vue JS의 요소
### 1. Directive(지시자)
- `v-for` : 배열과 같은 데이터를 순회
- `v-if` : 조건부 랜더링
- `v-else` : 조건부 랜더링
- `v-on` : 이벤트 바인딩(`addEventListener()`)
- `v-model` : 양방향 데이터 바인딩
- `v-on` : 이벤트 설정 (`addEventListener()`) == (`@`)
- `v-bind`: 속성값 설정 (`:`)
- `v-text`: 데이터 렌더(innerText)==`{{}}`
- `v-html`: 데이터 렌더(innerHTML)

### 2. Vue Instance(객체)
- `new Vue({})`
- `el: '#app'` : 마운트 포인트
- `data: {}` : 관리할 데이터
- `methods: {}`: 함수
- `computed: {}`: 함수화된 데이터
- `watch:{}` : 데이터 변경에 대한 콜백

