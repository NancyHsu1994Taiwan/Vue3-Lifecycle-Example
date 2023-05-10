<script setup>
import { ref, onActivated, onDeactivated } from 'vue'
onActivated(() => {
  console.log('onActivated執行，Vue元件A被啟動')
})
onDeactivated(() => {
  console.log('onDeactivated執行，Vue元件A被銷毀')
})
const count = ref(0)
</script>

<template>
  <p>Current component: A</p>
  <span>count: {{ count }}</span>
  <button @click="count++">+</button>
</template>
