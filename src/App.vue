<script>
import AnimalIndex from './pages/AnimalIndex.vue'
import SeasonClock from './pages/SeasonClock.vue'
import CountDown from './pages/CountDown.vue'
import WatcherApp from './pages/WatcherApp.vue'


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
    },
    onDone(){
      console.log('Done!')
    }
    
  },
  components: {
    AnimalIndex,
    SeasonClock,
    CountDown,
    WatcherApp,
  }
}
</script>

<template>
  <header>
    <h1>{{ txt }}</h1>
    <nav>
      <button @click="onChange('AnimalIndex')">Animal</button>
      <button @click="onChange('SeasonClock')">Season Clock</button>
      <button @click="onChange('CountDown')">Count Down</button>
      <button @click="onChange('WatcherApp')">Watcher App</button>
    </nav>
  </header>

  <AnimalIndex v-if="route === 'AnimalIndex'" />
  <SeasonClock v-if="route === 'SeasonClock'" />
  <CountDown v-if="route === 'CountDown'" @done="onDone"/>
  <WatcherApp v-if="route === 'WatcherApp'" />

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
