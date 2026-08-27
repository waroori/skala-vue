<script setup>
import { ElMessage, ElMessageBox } from 'element-plus'
import { ref } from 'vue'
const userForm = ref({ email: '', agree: false })
const handleRegister = () => {
  if (!userForm.value.email.includes('@')) {
    ElMessage.error('올바른 이메일 형식이 아닙니다.')
    return
  }
  if (!userForm.value.agree) {
    ElMessage.warning('이용약관에 동의하셔야합니다.')
    return
  }
  ElMessage.success('가입 신청이 정상적으로 완료되었습니다.')
}
const productQuantity = ref(1)
const productRate = ref(4)
const downloadProgress = ref(0)
const isDownloading = ref(false)

const confirmDelete = () => {
  ElMessageBox.confirm('서버에서 해당 파일을 영구히 삭제하시겠습니까?', '최종경고', {
    confirmButtonText: '네 삭제합니다.',
    cancelButtonText: '취소',
    type: 'danger',
  })
    .then(() => {
      ElMessage.success('파일이 안전하게 삭제되었습니다.')
    })
    .catch(() => {
      ElMessage.success('파일이 안전하게 파쇄되었습니다.')
    })
}
const startDownload = () => {
  if (isDownloading.value) return (isDownloading.value = true)
  downloadProgress.value = 0

  const interval = setInterval(() => {
    downloadProgress.value += 20
    if (downloadProgress.value >= 100) {
      clearInterval(interval)
      isDownloading.value = false
      ElMessage.success('대용량 데이터 로드가 완료되었습니다')
      return
    }
  }, 400)
}
</script>

<template>
  <h2>Element-plus 사용</h2>
  <div>
    <h3>실습 1. 회원가입 Form & 인풋 제어</h3>
    <p>이메일 주소:</p>

    <el-input v-model="userForm.email" placeholder="example@email.com"> </el-input>
    <el-switch v-model="userForm.agree" active-text="이용약관에 동의합니다"></el-switch>
    <br />
    <el-button @click="handleRegister">회원가입</el-button>
  </div>
  <div>
    <h3>실습2. 커머스 상품 수량 및 평점 시스템</h3>
    <span>구매 수량 선택:</span>
    <el-input-number v-model="productQuantity" :min="1" :max="10"></el-input-number>
    <span>최대 10개</span>
    <br />
    <el-rate v-model="productRate" allow-half :max="10"></el-rate>
    <p>실시간 장부 요약: 선택 수량 {{ productQuantity }}개/ 내가 준 점수 {{ productRate }}점</p>
  </div>
  <div>
    <h3>실습 3. 시스템피드백 & 프로그레스 인터랙션</h3>
    <el-button @click="confirmDelete">서버 파일 삭제 테스트</el-button>
    <el-button @click="startDownload">대용량 다운로드</el-button>
  </div>
</template>
