<template>
  <div>
    <input v-model="id" placeholder="ID 입력" />
    <input v-model="password" placeholder="Password 입력" />
    <p>{{ message }}</p>
    <button @click="whoami">whoami</button>
  </div>
</template>

<script setup>
import { ref } from 'vue'

// 반응형 상태 정의
const id = ref('')
const password = ref('')
const message = ref('Hello Vue')

// 이벤트 핸들러 함수 정의
const whoami = () => {
  message.value = `${id.value} ${password.value}`
}
</script>

<style scoped>
input {
  display: block;
  margin: 4px 0;
}

button {
  margin-top: 6px;
}
</style>
