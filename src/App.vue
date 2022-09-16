<script setup>
import { reactive, ref, toRefs } from 'vue';

import HelloWorld from './components/HelloWorld.vue';
const ageRef = ref(100);
const state = reactive({
  name: 'zl',
});
const { name } = toRefs(state);
function onChange(info) {
  console.log('change', info);
  ageRef.value++;
}
function addCount() {
  ageRef.value++;
}
function onDelete(info) {
  console.log('delete', info);
}
</script>

<template>
  <button @click="addCount">增加年龄</button>
  <HelloWorld
    :name="name"
    :age="ageRef"
    @change="onChange"
    @delete="onDelete"
  />
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
