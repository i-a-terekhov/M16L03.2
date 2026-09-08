<script setup>
import { ref, onMounted, defineProps, defineEmits } from 'vue';

const props = defineProps(["initialCount", "number"]);
const emit = defineEmits(["onCountChange"]);

const count = ref(props.initialCount);

function changeCount() {
  count.value++;
  emit('onCountChange', props.number, count.value);
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