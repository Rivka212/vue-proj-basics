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
<img :src="`https://robohash.org/${watcher.id}`" alt="">
    <!-- <img :src="require(`@/src/assets/imgs/${watcher.id}.jpg`)" alt=""> -->
    <!-- <img :src="getImageSrc(watcher.id)" alt=""> -->
    <!-- <img :src="`@/assets/imgs/${watcher.id}.jpg`" alt=""> -->

    <!-- <img :src="'./../assets/imgs/' + watcher.id+'.jng'" alt=""> -->
</template>


<style scoped>
h3 {
    padding: 10px;
}

img{
height: 90px;
    width: 90px;
    margin-bottom: 10px;
    margin-left: 20px;
}
</style>