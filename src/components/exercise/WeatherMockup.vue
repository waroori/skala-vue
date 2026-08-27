<script setup>
import { ref } from 'vue'

const weatherList = ref([
  { id: 'city_01', name: '서울', temp: 28, status: '맑음' },
  { id: 'city_02', name: '수원', temp: 24, status: '비' },
  { id: 'city_03', name: '부산', temp: 26, status: '구름' },
  { id: 'city_04', name: '인천', temp: 25, status: '안개' },
  { id: 'city_05', name: '대구', temp: 31, status: '맑음' },
  { id: 'city_06', name: '대전', temp: 27, status: '흐림' },
  { id: 'city_07', name: '광주', temp: 29, status: '맑음' },
  { id: 'city_08', name: '울산', temp: 26, status: '비' },
  { id: 'city_09', name: '세종', temp: 27, status: '구름' },
  { id: 'city_10', name: '제주', temp: 30, status: '맑음' },
])

const showDetail = (cityName, status) => {
  window.alert(`${cityName}의 현재 날씨는 [${status}] 상태입니다.`)
}
const whichcity = ref('')
const search = ref('')
const showCity = (cityName) => {
  whichcity.value = `${cityName}이 선택되었습니다.`
}
</script>

<template>
  <div class="dashboard-wrapper">
    <p>mockup 날씨 검색 (서울,수원,부산,인천,대구,대전,광주,울산,세종,제주)</p>
    <input
      type="text"
      :value="search"
      @input="(e) => (search = e.target.value)"
      placeholder="도시 검색창"
    />
    <p>{{ whichcity }}</p>
    <br />

    <div class="cityBlock" @click="showCity(city.name)" v-for="city in weatherList" :key="city.id">
      <div v-if="search == city.name">
        {{ city.name }} ( {{ city.status }} )
        <el-button @click.stop="showDetail(city.name, city.status)">상세보기</el-button>
        <p v-if="city.temp > 25">더움 현재기온: {{ city.temp }}</p>
        <p v-else>선선함 현재기온: {{ city.temp }}</p>
        <br />
      </div>
    </div>
  </div>
</template>
