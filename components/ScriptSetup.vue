<template>
  <p @click="addCount">{{ counterRef }}</p>
</template>
<script setup>
import { ref } from 'vue'

const counterRef = ref(0)
// function addCount() {
//   counterRef.value++
// }
</script>
