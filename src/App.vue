<script setup>
import Count from './components/Count.vue'
import { ref, watch } from 'vue';

const count = ref(3);

const items = ref([
  {
    number: 1,
  },
  {
    number: 2,
  },
  {
    number: 3,
  },
  {
    number: 4,
  },
]);

function onCountChangeHandler(newCountValue) {
  count.value = newCountValue;
}

function addNewCount() {
  const number = items.value.length > 0 ? (items.value[items.value.length - 1].number + 1) : 1;

  items.value.push({
    number: number,
  });

  console.log(items.value);
}

watch(count, (newValue, oldValue) => {
  console.log('Count value changed from ' + oldValue + ' to ' + newValue);
})

</script>

<template>
  <Count v-for="item in items" @on-count-change="onCountChangeHandler"
         :number="item.number" :count="count" key="item.number"/>

  <div>
    <button @click="addNewCount">Add new Count</button>
  </div>
</template>

<style scoped>
</style>
