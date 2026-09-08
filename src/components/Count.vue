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
  <div v-if="count !== 1">
    <p>Count is {{ count }}</p>
    <button @click="changeCount">Click me</button>
  </div>
  <div v-else>
    Nothing
  </div>
</template>

<style scoped>
</style>