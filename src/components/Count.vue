<script setup>
import { ref, computed } from 'vue';

const CONST_VAL = 10;

const props = defineProps(["number", "count"]);
const emit = defineEmits(["onCountChange"]);

const data = ref(0);

function changeCount() {
  const intData = parseInt(data.value);
  emit('onCountChange', props.count + (!isNaN(intData) ? intData : 1));
}

const mixedCount = computed(() => {
  return 'Count plus constant is ' + (props.count + CONST_VAL);
})

</script>

<template>
  <div>
    <p>Count is {{ count }}</p>
    <p>Mixed Count is {{ mixedCount }}</p>
    <input type="text" v-model="data" />
    <button @click="changeCount">Click me</button>
  </div>
</template>

<style scoped>
</style>