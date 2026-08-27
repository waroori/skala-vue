<script setup>
import { ref } from 'vue'
const count = ref(1)

// 메서드 핸들러 함수 정의
const showAlert = () => {
  alert('함수 호출 성공')
}
</script>

<template>
  <div class="practice-section">
    <h2>v-on 이벤트 핸들링 기초</h2>
    <h3>1) 인라인 연산 처리</h3>
    <p>현재 카운트: {{ count }}</p>
    <p @mouseenter="count *= 2">여기에 마우스를 올리면 값이 2배가 됩니다.</p>
    <p v-if="count >= 1000000" @mouseenter.prevent>1000000초과 불가 {{ count = 1000000 }}</p>
    <br />
    <h3>2) 스크립트 함수 호출</h3>
    <button @click="showAlert">함수 호출 버튼</button>
  </div>
</template>
