<template>
  <h2>{{rank}}</h2>
  <p>Reaction time: {{score}}ms</p>
</template>

<script>
export default {
    props: ['score'],
    data(){
        return{
            rank: null,
        }
    },
    mounted(){
        if(this.score < 300){
            this.rank = "Ninja Finger"
        }
        else if(this.score < 400){
            this.rank = "Fast enough"
        }
        else{
            this.rank = "Too slow"
        }
    }
}
</script>

<style>

</style>