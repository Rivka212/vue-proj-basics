<template>
    <section class="conut-down">
        <div :class="counterStyle">{{ counter }}</div>
    </section>

</template>
<script>

export default {
    data() {
        return {
            counter: 10,
            intervalId: null,

        };
    },

    computed: {
        counterStyle() {
            return {
                red: this.counter < 4
            }
        }
    },

    mounted() {
        this.startCountdown()
    },

    beforeDestroy() {
        clearInterval(this.intervalId);
    },
    methods: {
        startCountdown() {
            this.intervalId = setInterval(() => {
                if (this.counter <= 1) {
                    clearInterval(this.intervalId)
                   this.$emit('done')
                }
                return this.counter -= 1
            }, 1000)
        },
    //     unmounted(){
    //         clearInterval(this.intervalId);        }
    },
}


</script>

<style scoped>
.conut-down {
    font-family: monospace;
}

.red {
    color: rgb(223, 29, 29);
}

div {
    width: 100px;
    margin: 40px;
    padding: 40px;
    background-color: rgb(147, 147, 218);
    font-weight: 500;
    font-size: 23px;

}
</style>