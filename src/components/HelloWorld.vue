<script setup>
import { ref } from 'vue';
const props = defineProps({
  name: String,
  age: Number,
});
const emit = defineEmits(['change', 'delete']);
const passCount = ref('我是组件需要暴漏的数据');
defineExpose({
  passCount,
});
function onDelete() {
  emit('delete', 'del-type');
}
</script>

<template>
  <h1>child - name:{{ props.name }} | age: {{ props.age }}</h1>
  <button @click="$emit('change', 'add-type')">emit change</button>
  <button @click="onDelete">delete</button>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
