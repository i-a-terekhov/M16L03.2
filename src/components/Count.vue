<script setup>
const props = defineProps(["number", "count"]);
const emit = defineEmits(["onCountChange"]);

function changeCount() {
  emit('onCountChange', props.count + 1);
}
</script>

<template>
    <p>Count is {{ count }}</p>
    <button @click="changeCount">Click me</button>
</template>

<style scoped>
</style>