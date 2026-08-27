<script setup>
import { ref } from 'vue'

// 1. 조건부 온/오프 스위치 변수
const isLogged = ref(false)

// 2. 다중 조건 분기용 숫자 변수
const score = ref(85)
</script>

<template>
  <div class="practice-selection">
    <h2>v-if, v-else-if, v-else 디렉티브 학습</h2>
    <h3>1) 기본 로그인 상태 스위치</h3>
    <p v-if="isLogged">로그인 되었습니다</p>
    <p v-else>로그인이 필요합니다</p>
    <button @click="isLogged = !isLogged">{{ isLogged ? '로그아웃' : '로그인' }}</button>
    <br />
    <h3>2) 성적별 학점 등금 (다중 조건문)</h3>
    <label> 현재 점수 입력:</label>
    <input type="number" v-model="score" min="0" max="100" step="5" />
    <br />
    <div v-if="score >= 90">A 학점</div>
    <div v-else-if="score >= 80">B</div>
    <div v-else-if="score >= 70">C</div>
    <div v-else>D</div>
  </div>
</template>
