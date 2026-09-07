<script setup>
import { ref, onMounted } from 'vue';
const count = ref(3);

function changeCount() {
  count.value++;
}

onMounted(() => {
  console.log('Component mounted. Count is ' + count.value);
});
</script>

<template>
  <p>Count is {{ count }}</p>
  <button @click="changeCount">Click me</button>
</template>

<style scoped>
</style>