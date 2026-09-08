<script setup>
import Count from './components/Count.vue'

function onCountChangeHandler(countNumber, newCountValue) {
  console.log('Value for ' + countNumber + ' changed to ' + newCountValue)
}
</script>

<template>
  <Count v-bind:initial-count="10" v-on:on-count-change="onCountChangeHandler" v-bind:number="1"/>
  <Count :initial-count="20" @on-count-change="onCountChangeHandler" :number="2"/>
  <Count :initial-count="30" @on-count-change="onCountChangeHandler" :number="3"/>
</template>

<style scoped>
</style>
