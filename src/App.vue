<script setup>
import Count from './components/Count.vue'

const items = [
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
];

function onCountChangeHandler(countNumber, newCountValue) {
  console.log('Value for ' + countNumber + ' changed to ' + newCountValue)
}

function addNewCount() {
  const number = items.length > 0 ? (items[items.length - 1].number + 1) : 1;

  items.push({
    number: number,
  });

  console.log(items);
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
