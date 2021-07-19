<template>
    <div class="block" v-if="isPlaying" @click="stopTimer()">
        Click Me
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data(){
        return{
            timer: null,
            reactionTime: null,
            isPlaying: false
        }
    },
    mounted(){
        setTimeout(() => {
            this.isPlaying = true
            this.startTimer()
        }, this.delay);
    },
    methods:{
        startTimer(){
            this.timer = setInterval(()=>{
                this.reactionTime += 10;
            }, 10)
        },
        stopTimer(){
            clearInterval(this.timer)
            this.$emit("end", this.reactionTime)
        }
    }
}
</script>

<style>
 .block{
        width: 400px;
        border-radius: 20px;
        background: #0faf97;
        color: #fff;
        text-align: center;
        padding: 100px 0;
        margin: 40px auto;
    }
</style>