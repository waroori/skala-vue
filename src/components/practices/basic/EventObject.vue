<script setup>
import { ref } from 'vue'

const position = ref('')
const tagName = ref('')
const getOnlyEvent = (e) => {
  position.value = `좌표: X=${e.clientX}, Y=${e.clientY}`
}
const getWithParam = (name, e) => {
  tagName.value = `대상:${name} / 이벤트 타입: ${e.type}`
}
</script>

<template>
  <div class="practice-section">
    <h2>v-on 이벤트 객체($event) 활용</h2>
    <p @mouseover.once="getOnlyEvent">좌표: {{ position }}</p>
    <p>태그: {{ tagName }}</p>
    <button @click="getOnlyEvent">클릭 좌표 알아내기</button>
    <button @click="getWithParam('회원A', $event)" @mouseenter="getWithParam('회원A', $event)">
      회원 정보와 태그
    </button>
  </div>
</template>
