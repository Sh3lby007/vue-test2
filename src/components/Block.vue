<template>
    <div class="block" v-if="showBlock" @click="stopTimer">
        Click me
    </div>

</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showblock: false,
            timer: null,
            reactionTime: 0

        }
    },
    mounted() {
        setTimeout(() => {
            this.showblock = true
            this.startTimer()
        }, this.delay)
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10)
        },
        stopTimer() {
            clearInterval(this.timer)

        }
    }
}
</script>