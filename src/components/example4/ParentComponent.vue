<!-- ParentComponent.vue -->
<template>
  <div>
    <ChildComponent1 />
  </div>
</template>

<script setup>
import { provide } from 'vue'
import ChildComponent1 from '@/components/example4/ChildComponent1.vue'

// provide()로 하위 컴포넌트에 데이터 제공
provide('sharedMessage', 'Hello from provide')
</script>
