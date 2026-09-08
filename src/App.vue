<script setup>
import Count from './components/Count.vue'
import { ref } from 'vue';

const items = ref([
  {
    number: 1,
    initialCount: 10,
  },
  {
    number: 2,
    initialCount: 20,
  },
  {
    number: 3,
    initialCount: 30,
  },
  {
    number: 4,
    initialCount: 40,
  },
]);

function onCountChangeHandler(countNumber, newCountValue) {
  console.log('Value for ' + countNumber + ' changed to ' + newCountValue)
}

function addNewCount() {
  const number = items.value.length > 0 ? (items.value[items.value.length - 1].number + 1) : 1;

  items.value.push({
    number: number,
  });

  console.log(items.value);
}

</script>

<template>
  <Count v-for="item in items" :initial-count="item.initialCount" @on-count-change="onCountChangeHandler"
         :number="item.number" key="item.number"/>

  <div>
    <button @click="addNewCount">Add new Count</button>
  </div>
</template>

<style scoped>
</style>
