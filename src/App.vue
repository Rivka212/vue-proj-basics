<script>
import AnimalIndex from './cmps/AnimalIndex.vue'
import SeasonClock from './cmps/SeasonClock.vue'
import CountDown from './cmps/CountDown.vue'


export default {
  data() {
    return {
      txt: 'Hello Vue!',
      route: 'AnimalIndex',
    }
  },
  methods: {
    onChange(route) {
      this.route = route
    }
  },
  components: {
    AnimalIndex,
    SeasonClock,
    CountDown,
  }
}
</script>

<template>
  <header>
    <h1>{{ txt }}</h1>
    <nav>
      <button @click="onChange('AnimalIndex')">Animal</button>
      <button @click="onChange('SeasonClock')">season-clock</button>
      <button @click="onChange('CountDown')">count-down</button>
    </nav>
  </header>

  <AnimalIndex v-if="route === 'AnimalIndex'"/>

</template>



<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  background-color: lightsteelblue;
}

nav {
  display: flex;
  gap: 10px;
}

button {
  padding: 8px;
  background-color: whitesmoke;
  border-radius: 4px;
  border: none;
}
</style>
