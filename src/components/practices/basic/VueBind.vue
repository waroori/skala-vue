<script setup>
import { ref } from 'vue'
const dynamicUrl = 'https://www.google.com'
const logoIngSrc = 'https://vuejs.org/images/logo.png'
const logoWidth = 200
const isButtonDisabled = ref(true)
</script>

<template>
  <div class="practice-selection">
    <h2>v-bind 디렉티브 기본 (축약형 : 콜론)</h2>
    <h3>1) 동적 링크 연결</h3>
    <a :href="dynamicUrl">여기는 구글로 이동합니다</a>
    <br />
    <h3>2) 동적 이미지 연결</h3>
    <img :src="logoIngSrc" alt="Vue 로고" :width="logoWidth" />
    <br />
    <h3>3) 버튼 비활성화 제어</h3>
    <p>현재 버튼 사용 불가 상태: {{ isButtonDisabled }}</p>
    <button :disabled="isButtonDisabled">동의해야 클릭할 수 있는 버튼</button>&nbsp;
    <button :disabled="!isButtonDisabled">동의 안해야 클릭할 수 있는 버튼</button>&nbsp;

    <button @mouseenter="isButtonDisabled = !isButtonDisabled">위 버튼 토글하기</button>
  </div>
</template>
