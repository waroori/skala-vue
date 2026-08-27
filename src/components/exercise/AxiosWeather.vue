<script setup>
import { ref } from 'vue'
import axios from 'axios'
const weatherData = ref(null)
const isLoading = ref(false)
const handleFetchWeather = async () => {
  isLoading.value = true
  const lat = 38.964556
  const lon = -92.325556
  const API_KEY = import.meta.env.VITE_API_KEY
  const URL = `https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${lon}&appid=${API_KEY}&units=metric`

  try {
    const response = await axios.get(URL)
    console.log('Axios 통신 응답 전체 객체 : ', response)
    console.log('백엔드가 준 핵심 날씨 데이터(JSON):', response.data)
    weatherData.value = response.data
  } catch (error) {
    console.error('통신 중 에러가 발생했습니다:', error)
    alert('데이터를 가져오지 못했습니다.')
  } finally {
    isLoading.value = false
  }
}
</script>

<template>
  <h3>미주리 주 컬럼비아의 날씨</h3>
  <div class="practice-section">
    <h2>Axios 통신 검증</h2>
    <el-button @click="handleFetchWeather" :disabled="isLoading">
      {{ isLoading ? '데이터 로딩 중...' : '실시간 날씨 당겨오기' }}
    </el-button>
    <div v-if="weatherData" class="result-card">
      <p>
        위치:
        <strong
          >{{ weatherData.name }} 경도: {{ weatherData.coord.lon }},위도:
          {{ weatherData.coord.lat }}</strong
        >
      </p>
      <p>
        현재 기온: <strong>{{ weatherData.main.temp }} 'C</strong>
      </p>
      <p>
        날씨 상태: <strong>{{ weatherData.weather[0].description }}</strong>
      </p>
      <p>
        습도: <strong>{{ weatherData.main.humidity }} %</strong>
      </p>
    </div>
    <div v-else>
      <p>아직 가져온 데이터가 없습니다. 버튼을 눌러 통신을 가동하세요.</p>
    </div>
  </div>
</template>
