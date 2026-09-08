<script setup>
const props = defineProps(["number", "count"]);
const emit = defineEmits(["onCountChange"]);

function changeCount() {
  emit('onCountChange', props.count + 1);
}
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