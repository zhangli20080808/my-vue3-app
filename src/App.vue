<script setup>
import { reactive, ref, toRefs, onMounted } from 'vue';

import HelloWorld from './components/HelloWorld.vue';
const ageRef = ref(100);
// 获取子组件信息
const childRef = ref(null);
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

onMounted(() => {
  console.log(childRef.value);
  console.log(childRef.value.passCount);
});
</script>

<template>
  <button @click="addCount">增加年龄</button>
  <HelloWorld
    :name="name"
    :age="ageRef"
    @change="onChange"
    @delete="onDelete"
    ref="childRef"
  />
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
