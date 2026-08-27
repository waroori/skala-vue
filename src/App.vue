<script setup>
import { ref } from 'vue'
import SampleOne from './components/practices/basic/SampleOne.vue'
import SampleTwo from './components/practices/basic/SampleTwo.vue'
import VueBind from './components/practices/basic/VueBind.vue'
import VueBindClass from './components/practices/basic/VueBindClass.vue'
import VueIf from './components/practices/basic/VueIf.vue'
import VueShow from './components/practices/basic/VueShow.vue'
import VueFor from './components/practices/basic/VueFor.vue'

import EventObject from './components/practices/basic/EventObject.vue'
import EventBasic from './components/practices/basic/EventBasic.vue'
import EventModifier from './components/practices/basic/EventModifier.vue'
import ModelBasic from './components/practices/basic/ModelBasic.vue'
import ModelForm from './components/practices/basic/ModelForm.vue'
import ModelModifier from './components/practices/basic/ModelModifier.vue'
import WeatherMockup from './components/exercise/WeatherMockup.vue'
import ReactiveRef from './components/practices/composition/ReactiveRef.vue'
import ReactiveReactive from './components/practices/composition/ReactiveReactive.vue'
import ComputedBasic from './components/practices/composition/ComputedBasic.vue'
import WatchersBasic from './components/practices/composition/WatchersBasic.vue'
import WatchersMulti from './components/practices/composition/WatchersMulti.vue'
import WatchersDeep from './components/practices/composition/WatchersDeep.vue'
import WatchersReactive from './components/practices/composition/WatchersReactive.vue'
import WatchersRefArray from './components/practices/composition/WatchersRefArray.vue'
import WatchersReactiveArray from './components/practices/composition/WatchersReactiveArray.vue'
import WatchersWatchEffect from './components/practices/composition/WatchersWatchEffect.vue'
import WeatherComposition from './components/exercise/WeatherComposition.vue'

import LifeCycle from './components/practices/day3/LifeCycle.vue'

import AxiosWeather from './components/exercise/AxiosWeather.vue'
import AxiosJson from './components/practices/day4/AxiosJson.vue'
import UserForm from './components/practices/day4/UserForm.vue'
import WeatherParent from './components/exercise/WeatherComponent/WeatherParent.vue'
import UnitToggler from './components/exercise/UnitToggler.vue'
const isVisible1 = ref(false)
const isVisible2 = ref(false)
const isVisible3 = ref(false)
const isVisible4 = ref(false)
const isVisible5 = ref(false)
</script>
<template>
  <div style="padding: 20px">
    <el-button @click="isVisible1 = !isVisible1">day1 표시/숨김</el-button>
    <el-button @click="isVisible2 = !isVisible2">day2 표시/숨김</el-button>
    <el-button @click="isVisible3 = !isVisible3">day3 표시/숨김</el-button>
    <el-button @click="isVisible4 = !isVisible4">day4 표시/숨김</el-button>
    <el-button @click="isVisible5 = !isVisible5">날씨 실습 시리즈 표시/숨김</el-button>

    <div id="1st day" v-show="isVisible1">
      <SampleOne />
      <br />
      <hr />
      <SampleTwo />
      <br />
      <hr />
      <VueBind />
      <br />
      <hr />
      <VueBindClass />
      <br />
      <hr />
      <VueIf />
      <br />
      <hr />
      <VueShow />
      <br />
      <hr />
      <VueFor />
      <br />
      <hr />
    </div>
    <div id="2nd day" v-show="isVisible2">
      <EventBasic />
      <br />
      <hr />
      <EventObject />
      <br />
      <hr />
      <EventModifier />
      <br />
      <hr />
      <ModelBasic />
      <br />
      <hr />
      <ModelForm />
      <br />
      <hr />
      <ModelModifier />
      <br />
      <hr />
      <ReactiveRef />
      <br />
      <hr />
      <ReactiveReactive />
      <br />
      <hr />
      <ComputedBasic />
      <br />
      <hr />
      <WatchersBasic />
      <br />
      <hr />
      <WatchersMulti />
      <br />
      <hr />
      <WatchersDeep />
      <br />
      <hr />
      <WatchersReactive />
      <br />
      <hr />
      <WatchersRefArray />
      <br />
      <hr />
      <WatchersReactiveArray />
      <br />
      <hr />
      <WatchersWatchEffect />
    </div>
    <div id="3rd day" v-show="isVisible3">
      <br />
      <hr />
      <LifeCycle />
    </div>
    <div id="4th day" v-show="isVisible4">
      <br />
      <hr />
      <AxiosJson />
      <br />
      <hr />
      <UserForm />
    </div>

    <div id="weather" v-show="isVisible5">
      <br />
      <hr />
      <WeatherMockup />
      <br />
      <hr />
      <WeatherComposition />
      <br />
      <hr />
      <WeatherParent />
      <br />
      <hr />
      <AxiosWeather />

      <div class="app-container">
        <h1>⛅ 과제 4: 라우터적용</h1>
        <hr />
        <div class="dashboard-wrapper">
          <nav class="navigation-bar">
            <RouterLink to="/" class="nav-item">🌦️ 날씨 대시보드</RouterLink>
            <span class="divider">|</span>
            <RouterLink to="/about" class="nav-item">ℹ️ 서비스 소개</RouterLink>
          </nav>
          <main>
            <RouterView />
            <!-- RouterView v-slot="{ Component }">
          <KeepAlive>
            <component :is="Component" />
          </KeepAlive>
        </RouterView-->
          </main>
        </div>
      </div>
      <div class="app-container">
        <h1>⛅ 과제 5: 스토어적용</h1>
        <hr />
        <div class="dashboard-wrapper">
          <nav class="navigation-bar">
            <RouterLink to="/" class="nav-item">🌦️ 날씨 대시보드</RouterLink>
            <span class="divider">|</span>
            <RouterLink to="/about" class="nav-item">ℹ️ 서비스 소개</RouterLink>
            <UnitToggler />
          </nav>
          <main>
            <RouterView />
          </main>
        </div>
      </div>
    </div>
  </div>
</template>
