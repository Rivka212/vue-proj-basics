<script>
import WatcherPreview from './WatcherPreview.vue'
import WatcherAppModal from './WatcherAppModal.vue'


export default {
    props: ['watchers'],
    data() {
        return {
            isOpenModal: false,
            selectedWatcher: null,
        }
    },
    methods: {
        onRemove(watcherId) {
            this.$emit('remove', watcherId)
        },
        onSelect(watcherId) {
            if (this.selectedWatcher === watcherId) {
                this.selectedWatcher = null;
            } else {
                this.selectedWatcher = watcherId;
            }
        },
        closeModal() {
            this.selectedWatcher = null 
           }
    },
    components: {
        WatcherPreview,
        WatcherAppModal,
    }
}
</script>

<template>
    <section class="watcher-list">
        <ul>
            <li v-for="(watcher) in watchers" :key="watcher.id">
                <watcherPreview v-bind:watcher="watcher" />
                <button v-on:click.stop="onRemove(watcher.id)">x</button>
                <button v-on:click.stop="onSelect(watcher.id)">Select</button>
             <WatcherAppModal v-bind:watcher="watcher" v-if="selectedWatcher === watcher.id"  @close="closeModal"/>
            </li>
        </ul>
    </section>
</template>

<style scoped>
.watcher-list {
    display: grid;
    align-content: center;
    justify-content: center;
    /* background-color: rgb(104, 104, 139); */
}

li {
    text-decoration: none;
    background-color: rgb(175, 120, 156);
    border-radius: 5px;
    width: 180px;
    padding: 10px;
    margin: 15px;

}

ul{
    border-radius: 5px;
    list-style-type: none;
}
button{
    border: none;
    border-radius: 5px;
    padding: 5px;
    margin-inline: 7px;
    margin-bottom: 8px;
}
button:first-of-type{
    width: 30px;
}

button:hover{
    background-color: rgb(154, 168, 204);
}
</style>