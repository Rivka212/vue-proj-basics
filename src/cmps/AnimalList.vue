<script>
import AnimalPreview from './AnimalPreview.vue'


export default {
    props: ['animals'],
    data() {
        return {
        }
    },
    methods: {
        onChange(newVal) {
            console.log(newVal)
        }
    },
    components: {
        AnimalPreview,
    }
}
</script>

<template>
    <section class="animal-list">
        <table>
            <tbody v-for="(animal, index) in animals" :key="index">
                <tr>
                    <AnimalPreview v-bind:animal="animal" />
                    <td> <a :href="'https://www.google.com/search?q='+ animal.type" target="_blank">Search</a></td>
                </tr>
            </tbody>
        </table>
    </section>
</template>

<style scoped>
table {
    margin: 20px;
    padding: 10px;
    background-color: lightsteelblue;
    border-collapse: collapse;
}

td {
    border: 1px solid black;
    border-collapse: collapse;
    padding: 10px;

}
</style>