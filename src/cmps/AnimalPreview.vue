<script>

export default {
    props: ['animal'],
    data() {
        return {
        }
    },
    methods: {
        // onChange(newVal) {
        //     console.log(newVal)
        // }
    },

}
</script>

<template class="animal-preview">
    <td>{{ animal.type }}</td>
    <td>{{ animal.count }}</td>
</template>


<style scoped>
td {
    border: 1px solid black;
    border-collapse: collapse;
    padding: 10px;
}

td:first-of-type {
    width: 150px;
}
</style>