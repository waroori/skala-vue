<script setup>
import { ref, onMounted, onUpdated, onUnmounted } from 'vue'
const count = ref(0)
let timerId = null
console.log('1. 컴포넌트가 메모리에 생성됨')
onMounted(() => {
  console.log('2.화면에 완벽히 부착되었습니다!')
  timerId = setInterval(() => {
    count.value++
  }, 3000)
})

onUpdated(() => {
  console.log(`3.데이터가 변경되어 화면을 새로 그렸습니다. (현재 count : ${count.value})`)
})

onUnmounted(() => {
  clearInterval(timerId)
  console.log(`4.컴포넌트가 소멸되었습니다.`)
})
const text = ref('')
const seeConsole = () => {
  text.value = text.value == '콘솔창 변화' ? '' : '콘솔창 변화'
}
</script>
<template>
  <p>컴포넌트 생명 주기</p>
  <div>
    <h3 @mouseover="seeConsole" @mouseleave.stop="seeConsole">
      마우스를 올렸다 내리면서 콘솔창 변화 확인하세요
    </h3>
    <p>{{ text }}</p>
  </div>
</template>
