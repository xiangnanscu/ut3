<template>
  <div>Home12</div>
  <test-hmr/>
  <thread-list  :records="records"></thread-list>
</template>

<script setup>
import {onMounted, ref} from "vue"
import TestHmr from "../components/test-hmr";
import threadList from "./thread-list.vue";

const records = ref([])
onMounted(async ()=>{
const {data:{records}} = await uni.request({url:'http://localhost:8080/thread', data:{pagesize:3}})
records.value = records
})
</script>

<style scoped></style>
