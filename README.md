# skala-vue

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VS Code](https://code.visualstudio.com/) + [Vue (Official)](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Recommended Browser Setup

- Chromium-based browsers (Chrome, Edge, Brave, etc.):
  - [Vue.js devtools](https://chromewebstore.google.com/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd)
  - [Turn on Custom Object Formatter in Chrome DevTools](http://bit.ly/object-formatters)
- Firefox:
  - [Vue.js devtools](https://addons.mozilla.org/en-US/firefox/addon/vue-js-devtools/)
  - [Turn on Custom Object Formatter in Firefox DevTools](https://fxdx.dev/firefox-devtools-custom-object-formatters/)

## Customize configuration

See [Vite Configuration Reference](https://vite.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```

### README 작성

# App.vue는 각 일차별로 보는 것이 가능하게 되어있다.

# 1일차

- vue 기본적인 문법 연습, 반응형 데이터
- directive (VueBind, VueBindClass, VueBindShorthand, VueBindStyle, VueFor, VueIf)

# 2일차

- 1일차에 이어 주요 문법 학습
- event(v-on) (EventBasic, EventModifier, EventObject)
- model(v-model) (ModelBasic, ModelForml, ModelModifier)

- directive 종합 (WeatherMockup.vue)
- 지금까지의 학습내용으로 도시의 날씨 검색, 날씨 정보 띄우고 bubbling, stop propagation과 같은 부분 구현

- composition API
- vue 3 에서 사용되는 내장함수 ref, reactive, computed, watch 학습
- (ComputedBasic, ReactiveRef, ReactiveReactive, WatchersBasic, WatchersDeep, WatchersMulti)
- (WatchersReactive, WatchersReactiveArray, WatchersRefArray, WatchersWatchEffect)

- 2일차 종합 (WeatherComposition)
- 실습에 적용하여 날씨 검색 구현

# 3일차

- Components 구성으로 컴포넌트 사이에 부모 자식관계를 가지고 데이터와 이벤트를 주고 받는 emit과 prop을 학습
- slot을 통해 자식 컴포넌트의 디자인 주입 가능
- Router 기능을 통해 URL 변화로 화면을 단계적으로 구성하면서 서버에 새롭게 요청하지 않으면서 다른 화면으로 이동 가능하다
- pinia를 통해 거리가 먼 컴포넌트간에 데이터를 주고받기 편하게 전역으로 접근 가능한 store를 만들어 데이터 관리한다
- (LifeCycle, WeatherParent, WeatherComponent, UnitToggler)

# 4일차

- Axios를 통해 API 데이터를 CRUD하는 학습 (AxiosWeather, AxiosJson)
- UI Library를 통해서 여러가지 유용한 툴을 추가로 사용가능합니다.
- element plus로 쉽게 컴포넌트 사용 (UserForm)
- Lint를 통해 자동적으로 문법오류를 감지하고 npm run lint로 전체적인 오류를 계산합니다
- Pritter, Environment Variables, Build로 여러 개발환경에서 효율적으로 작업 가능합니다.

# 궁금하고 어려웠던 점들

- 먼저 어려웠던 점으로는 3일차의 emit과 prop이 있었습니다. 구현하고자 하는 페이지가 있을 때 해당 vue를 어떻게 부모와 자식으로 구성해야 하는지가 감이 안왔습니다. 계속해보면서 자주 나오는 기능을 자식으로 설정해 놓으면 다양한 곳에 가져다 쓸 수 있었습니다.

- 전체적인 구조를 이미지화 하는 것이 어려웠습니다. 필요한 기능을 어떤 방식으로 사용자에게 보여주고, 어떻게 배치하는지를 설계할 수 있는 능력이 필요한 능력이었다고 생각하고, 이 부분은 교수님 진행방식대로 따라서 코드를 바꾸고 입력하면서 웹에서의 변화를 확인하는 작업을 반복함으로써 개선될 수 있다고 생각합니다.

- 궁금해서 더 찾아보고 싶은 점으로는 vue를 사용하면서 웹사이트 하나에 많은 vue파일이 사용되는 것을 느꼈는데 점점 많은 기능이 생기게 되면 언젠가는 페이지를 분리하는게 한 곳에서 모든 기능을 수행하는 것보다 좋지 않을까 싶습니다. 또한 여러가지 파일을 관리하는데 어떤 방식으로 분류하고 폴더 구조를 만들 지에 대한 점도 생각해 볼거리라고 생각합니다.

- 최종적인 사이트를 완성하면서 느낀점은 먼저 기능 구현하는 것과 vue 이해하는 데 집중하여 추가적인 기능이나 디자인에 신경쓰지 못한 점이 아쉬웠습니다.
