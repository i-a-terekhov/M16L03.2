<script setup>
import { ref } from 'vue';

const props = defineProps(["number", "count"]);
const emit = defineEmits(["onCountChange"]);

const data = ref(0);

function changeCount() {
  const intData = parseInt(data.value);
  emit('onCountChange', props.count + (!isNaN(intData) ? intData : 1));
}

function changeData(event) {
  data.value = event.target.value;
}
</script>

<template>
  <div>
    <p>Count is {{ count }}</p>
    <input type="text" :value="data" @input="changeData"/>
    <button @click="changeCount">Click me</button>
  </div>
</template>

<style scoped>
</style>