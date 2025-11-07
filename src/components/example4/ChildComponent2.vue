<!-- ChildComponent.vue -->
<template>
  <div>
    <p>{{ sharedMessage }}</p>
  </div>
</template>

<script setup>
import { inject } from 'vue'

// 상위 컴포넌트로부터 데이터 주입
const sharedMessage = inject('sharedMessage')
</script>

<style scoped>
p {
  font-size: 1.5rem;
}
</style>
