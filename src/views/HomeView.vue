<script setup>
import {
  onBeforeMount,
  onMounted,
  onBeforeUnmount,
  onUnmounted,
  onBeforeUpdate,
  onUpdated,
  onActivated,
  onDeactivated,
  // ref,
  shallowRef
} from 'vue'
import CompA from '../components/CompItemA.vue'
import CompB from '../components/CompItemB.vue'
onBeforeMount(() => {
  console.log('onBeforeMount執行，Vue 實體尚未與模板 (DOM 節點) 綁定')
})
onMounted(() => {
  console.log('onMounted執行，vue實體掛載完成')
})

onBeforeUnmount(() => {
  console.log('切換頁面，onBeforeUnmount執行，Vue 實體物件HomeView被銷毀前')
})
onUnmounted(() => {
  console.log('切換頁面，onUnmounted執行，Vue 實體物件HomeView被銷毀完畢')
})
onBeforeUpdate(() => {
  console.log('onBeforeUpdate執行，狀態被變動時，畫面同步更新前')
})
onUpdated(() => {
  console.log('onUpdated執行，狀態被變動，畫面同步更新完成')
})
onActivated(() => {
  console.log('onActivated執行，Vue元件被啟動')
})
onDeactivated(() => {
  console.log('onDeactivated執行，Vue元件被銷毀')
})

// let num = ref(1)
// function addNum() {
//   num.value += 1
// }

const current = shallowRef(CompA)
</script>

<template>
  <div class="demo">
    <label><input type="radio" v-model="current" :value="CompA" /> A</label>
    <label><input type="radio" v-model="current" :value="CompB" /> B</label>

    <keep-alive>
      <component :is="current" />
    </keep-alive>
    <!-- </router-view> -->
  </div>
</template>

<style>
.text-white {
  color: white;
}
.block {
  display: block;
}
.hidden {
  display: none;
}
</style>
