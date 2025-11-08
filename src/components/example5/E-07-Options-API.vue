<template>
  <div>
    <h2>{{ title }}</h2>
    <p>Full Name: {{ fullName }}</p>
    <input v-model="firstName" placeholder="First Name" />
    <input v-model="lastName" placeholder="Last Name" />
    <button @click="greet">Greet</button>
    <p>Greeting Count: {{ greetCount }}</p>
    <p>{{ message }}</p>
  </div>
</template>

<script setup>
import { ref, computed, watch, onBeforeMount, onMounted, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted } from 'vue'

// -----------------------------
// 1️⃣ props 정의 (readonly 문제 방지)
// -----------------------------
const props = {
  title: 'User Information' // 기본값
}
// 만약 부모로부터 props 받는 경우
// const props = defineProps({
//   title: { type: String, default: 'User Information' }
// })

const title = ref(props.title) // 템플릿에서 바로 사용 가능

// -----------------------------
// 2️⃣ 반응형 상태 정의
// -----------------------------
const firstName = ref('John')
const lastName = ref('Doe')
const greetCount = ref(0)
const message = ref('')

// -----------------------------
// 3️⃣ computed 정의
// -----------------------------
const fullName = computed(() => `${firstName.value} ${lastName.value}`)

// -----------------------------
// 4️⃣ methods 정의
// -----------------------------
const greet = () => {
  greetCount.value++
  message.value = `Hello, ${fullName.value}!`
}

const resetGreetCount = () => {
  greetCount.value = 0
}

// -----------------------------
// 5️⃣ watch 정의
// -----------------------------
watch(greetCount, (newValue, oldValue) => {
  console.log(`Greet count changed from ${oldValue} to ${newValue}`)
  if (newValue >= 3) {
    message.value = "That's enough greetings for now!"
  }
})

// -----------------------------
// 6️⃣ lifecycle hooks
// -----------------------------
onBeforeMount(() => console.log('beforeMount hook'))
onMounted(() => console.log('mounted hook'))
onBeforeUpdate(() => console.log('beforeUpdate hook'))
onUpdated(() => console.log('updated hook'))
onBeforeUnmount(() => console.log('beforeUnmount hook'))
onUnmounted(() => console.log('unmounted hook'))

// Options API의 beforeCreate, created는 setup 시작 시점에서 이미 처리됨
console.log('beforeCreate hook (setup 시작 시점)')
console.log('created hook (setup 시작 시점)')
</script>
