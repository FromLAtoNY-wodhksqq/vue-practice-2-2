<!-- ParentComponent.vue -->
<template>
  <div>
    <ChildComponent
        :message="parentMessage"
        :id="1"
        :password="1234"
        @custom-event="handleEvent"
    />
  </div>
</template>

<script setup>
import ChildComponent from './ChildComponent.vue'
import { ref } from 'vue'

// 반응형 상태 정의
const parentMessage = ref('Hello from parent')

// 이벤트 핸들러 정의
const handleEvent = (payload) => {
  console.log(payload)
}
</script>
