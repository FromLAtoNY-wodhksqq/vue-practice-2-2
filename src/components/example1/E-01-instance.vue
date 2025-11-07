<template>
  <div>Hello, {{ message }}</div>
</template>

<script setup>
import { ref } from 'vue'

const name = '최재완'
const message = ref(name)
</script>

<style scoped>
div {
  color: blue;
}
</style>
