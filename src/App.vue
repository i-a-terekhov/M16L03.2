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
]

function onCountChangeHandler(countNumber, newCountValue) {
  console.log('Value for ' + countNumber + ' changed to ' + newCountValue)
}
</script>

<template>
  <Count v-for="item in items" :initial-count="item.initialCount" @on-count-change="onCountChangeHandler"
         :number="item.number" key="item.number" />
</template>

<style scoped>
</style>
