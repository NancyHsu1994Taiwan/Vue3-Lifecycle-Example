<script setup>
import { ref, onActivated, onDeactivated } from 'vue'
onActivated(() => {
  console.log('onActivated執行，Vue元件B被啟動')
})
onDeactivated(() => {
  console.log('onDeactivated執行，Vue元件B被銷毀')
})
const msg = ref('')
</script>

<template>
  <p>Current component: B</p>
  <span>Message is: {{ msg }}</span>
  <input v-model="msg" />
</template>
