<template>
  <button @click="hidshow">hide and show</button>
  <div id="box" class="block">
    <img src="https://i.pinimg.com/564x/ab/d1/8d/abd18d321c0c1ab7481d235f37eb2cf3.jpg" alt="" />
  </div>
</template>
<script setup>
function hidshow() {
  const box = document.querySelector('#box')
  let status = box.getAttribute('class')
  console.log(status)
  if (status === 'block') {
    box.setAttribute('class', 'hidden')
  } else {
    box.setAttribute('class', 'block')
  }
}
</script>
<style>
.block {
  display: block;
}
.hidden {
  display: none;
}
</style>
