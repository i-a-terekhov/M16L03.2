<script setup>
import { ref, onMounted, defineProps } from 'vue';

const props = defineProps(["initialCount"]);

const count = ref(props.initialCount);

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