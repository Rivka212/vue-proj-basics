<script>
import AnimalList from '../cmps/AnimalList.vue'

export default {

    data() {
        return {
            animals: [
                { type: 'Malayan Tiger', count: 787 },
                { type: 'Mountain Gorilla', count: 212 },
                { type: 'Fin Whale', count: 28 },
            ]
        };
    },

    components: {
        AnimalList,
    }
};
</script>

<template>
    <h2>Rare Animals</h2>
    <section class="animal-index">
        <AnimalList v-bind:animals="animals" />
    </section>
</template>

<style scoped>
h2 {
    padding: 40px 0 0 20px;
}
</style>