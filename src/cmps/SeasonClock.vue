<script>

export default {

    data() {
        return {
            sectionStyle: '',
            date: new Date(),
            locale: 'en-US',
            time: new Date().toLocaleTimeString(),
            intervalId: null,
            season: '',
            monthNames: '',
            day:'',
        };
    },

    methods: {
        toggleDarkMode() {
            this.sectionStyle = this.sectionStyle === 'dark' ? '' : 'dark';
        },
        getDayName() {
            return this.date.toLocaleDateString(this.locale, { weekday: 'long' });
        },

        getMonthName() {
            const monthNames = ['January', 'February', 'March', 'April', 'May', 'June',
                'July', 'August', 'September', 'October', 'November', 'December'];
            return monthNames[this.date.getMonth()];

        },

        getSeason() {
            const month = this.date.getMonth();
            if (month === 11 || month <= 1) {
                this.season = 'winter';
            } else if (month >= 2 && month <= 4) {
                this.season = 'spring';
            } else if (month >= 5 && month <= 7) {
                this.season = 'summer';
            } else {
                this.season = 'autumn'
            }
            return this.season
        },


        updateTime() {
            this.date = new Date();
            this.time = this.date.toLocaleTimeString();
        },
    },

    mounted() {
        this.day = this.getDayName(),
        this.season = this.getSeason(),
        this.monthNames = this.getMonthName(),

        this.intervalId = setInterval(this.updateTime, 1000);
    },
    beforeDestroy() {
        clearInterval(this.intervalId);
    }
}
</script>

<template>
    <button @click="toggleDarkMode()" :class="['season-clock', sectionStyle]">
        <p>{{ monthNames }}</p>
        <p>({{ season }})</p>
        <img :src="'./../assets/imgs/' + season + '.png'" alt="season-image">
        <p>{{ day }}</p>
        <p>{{ time }}</p>
    </button>
</template>

<style scoped>
.season-clock {
    background-color: rgb(127, 191, 255);
    padding: 30px;
    margin: 20px;
    font-size: 20px;
    font-weight: 600;

}

img {
    width: 20px;
    height: 20px;
}

.dark {
    background-color: rgb(27, 27, 96);
}
</style>