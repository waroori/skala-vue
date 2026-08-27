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

# 4일차

- Axios를 통해 API 데이터를 CRUD하는 학습 (AxiosWeather, AxiosJson)
