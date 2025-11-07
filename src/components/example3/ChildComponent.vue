<!-- ChildComponent.vue -->
<template>
  <div>
    <p>{{ message }}</p>
    <p>{{ id }}</p>
    <p>{{ password }}</p>
    <button @click="emit('custom-event', 'Hello from child')">Send Event</button>
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue'

// Props 정의
const props = defineProps({
  message: String,
  id: String,
  password: String
})

// Emit 정의
const emit = defineEmits(['custom-event'])
</script>
