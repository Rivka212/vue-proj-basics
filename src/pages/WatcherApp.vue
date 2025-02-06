<script>
import WatchersList from '../cmps/WatchersList.vue'

export default {

    data() {
        return {
            watchers: [
                { id: 'w101', fullname: 'Puki Ba', movies: ['Rambo', 'Rocky'] },
                { id: 'w102', fullname: 'Buki Na', movies: ['Rambo', 'Rocky'] },
                { id: 'w103', fullname: 'Noli Ma', movies: ['Rambo', '101 Dalmatians'] },
                { id: 'w104', fullname: 'Kobi Sar', movies: ['The Sound of Music', 'Rocky'] },
                { id: 'w105', fullname: 'Poli Zor', movies: ['Rambo', 'Rocky'] },
            ]
        };
    },

    methods: {
        remove(watcherId) {
            const idx = this.watchers.findIndex(watcher => watcher.id === watcherId)
            this.watchers.splice(idx, 1)
        },
        selectWatcher(watcherId) {
            const idx = this.watchers.findIndex(watcher => watcher.id === watcherId)
            // this.watchers.splice(idx, 1)
        },
        addWatcher() {
            const id = Date.now() % 1000
            var newWatcherName = prompt('what is the fullname?')
            if (!newWatcherName) return
            var newWatcherMovies = prompt('what is the movies?')
            const watcher = {
                id,
                fullname: newWatcherName,
                movies: [newWatcherMovies]
            }
            this.watchers.unshift(watcher)
        }
    },

    components: {
        WatchersList,
    }
};
</script>

<template>
    <section class="watcher-index">
        <h2>Watchers App</h2>
        <button @click="addWatcher()">Add Watcher</button>
        <WatchersList v-bind:watchers="watchers" v-on:remove="remove" v-on:selectWatcher="selectWatcher"/>
    </section>
</template>

<style scoped>
button{
    margin-top: 30px;
    margin-inline-start: 40px;
    padding: 4px;
    background-color: rgb(188, 188, 237);
}

h2 {
    padding: 40px 0 0 20px;
}
</style>