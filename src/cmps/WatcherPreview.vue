<script>
export default {
    props: ['watcher'],
    data() {
        return {
        }
    },
    methods: {
        getImageSrc(id) {
        return require(`@/assets/imgs/${id}.jpg`);
    }
    },

}
</script>

<template class="watcher-preview">
    <h3>{{ watcher.fullname }}</h3>

    <!-- <img :src="require(`@/src/assets/imgs/${watcher.id}.jpg`)" alt=""> -->
    <!-- <img :src="getImageSrc(watcher.id)" alt=""> -->
    <img :src="`@/assets/imgs/${watcher.id}.jpg`" alt="">

    <!-- <img :src="'./../assets/imgs/' + watcher.id+'.jng'" alt=""> -->
</template>


<style scoped>
h3 {
    padding: 20px;
}

img{
height: 50px;
    width: 50px;
    /* background-color: blueviolet; */
}
</style>