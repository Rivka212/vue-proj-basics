
<script>

export default {
    props: ['watcher'],
    data() {
        return {
        }
    },
    methods: {
        closeModal() {
            this.$emit('close')
        },
    },
    components: {
    }
}
</script>

<template>
    <section class="watcher-app-modal">
         <h3>{{ watcher.fullname }}</h3>
        <ul>
            <li v-for="(movie) in watcher.movies" :key="movie">
                <p>{{movie}}</p>
            </li>
        </ul>    
     <button v-on:click.stop="closeModal()">Close</button>
    </section>
</template>

<style scoped>
.watcher-app-modal {
    display: grid;
    align-content: center;
    justify-content: center;
    background-color: rgb(200, 102, 134);
    position: fixed;
    top: 0;
    right: 0;
    z-index: 10;
    padding:30px 50px 30px 50px;
}
ul{
    padding: 7px;
    margin-top: 5px;
}

li::marker{
    margin: 0;
}

</style>