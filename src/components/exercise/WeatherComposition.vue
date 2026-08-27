<script setup>
import { ref, watch, computed, watchEffect } from 'vue'

const searchQuery = ref('')
const selectedCityInfo = ref('카드를 클릭하거나 검색해 보세요.')
const weatherList = ref([
  { id: 'city_01', name: '서울', temp: 28, status: '맑음' },
  { id: 'city_02', name: '수원', temp: 24, status: '비' },
  { id: 'city_03', name: '부산', temp: 26, status: '구름낌' },
])
const filteredWeatherList = computed(() => {
  const query = searchQuery.value.trim()

  if (!query) {
    return weatherList.value
  }

  return weatherList.value.filter((item) => item.name.includes(query))
})

watch(selectedCityInfo, (newInfo) => {
  console.log(`상태바 문구가 ${newInfo}로 바뀌었습니다.`)
})

watchEffect(() => {
  console.log(`현재 검색어는 ${searchQuery.value}입니다.`)
})
const showDetail = (cityName, status) => {
  window.alert(`현재 ${cityName}의 날씨는 ${status}입니다.`)
}
</script>

<template>
  <div class="dashboard-wrapper">
    <h3>도시 검색</h3>
    <input
      type="text"
      :value="searchQuery"
      @input="(e) => (searchQuery = e.target.value)"
      placeholder="검색할 도시 이름 입력"
    />
    <p>검색중인 도시 : {{ searchQuery }}</p>
    <div v-for="CITY in filteredWeatherList" :key="CITY.id">
      <p>{{ CITY.name }} {{ CITY.status }}</p>
      <p>현재 기온 : {{ CITY.temp }}</p>
      <p v-if="CITY.temp >= 20">더움</p>
      <p v-else>시원함</p>
      <button @click="showDetail(CITY.name, CITY.status)">상세보기</button>
    </div>
  </div>
</template>
