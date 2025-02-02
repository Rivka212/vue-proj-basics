<script>
import AnimalIndex from './cmps/AnimalIndex.vue'
import SeasonClock from './cmps/SeasonClock.vue'
import CountDown from './cmps/CountDown.vue'


export default {
  data() {
    return {
      txt: 'Hello Vue!'
    }
  },
}
</script>

<template>
  <h1>{{ txt }}</h1>
  <nav>
    <button @click="route = 'AnimalIndex'">Animal</button>
    <button @click="route = 'SeasonClock'">season-clock</button>
    <button @click="route = 'CountDown'">count-down</button>
  </nav>
</template>

<style scoped></style>
