<template>
  <button @click="show">CLICK</button>
</template>

<script setup>
const show=()=>{
  uni.showToast({title:'3'})
}
</script>

<style scoped></style>
