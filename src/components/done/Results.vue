<template>
    <h1>Reaction time: {{ score }} ms</h1>
    <p>{{ rank }}</p>
</template>

<script>
export default {
    data(){
        return{
           rank: null
        }
    },
    mounted(){
        if(this.score < 250){
            this.rank = "Ninja Fingers"
        }
        else if(this.score < 400){
            this.rank = "Rapid reflexes"
        }
        else{
            this.rank = "Snail pace..."
        }
    },
    props: ['score'],
    methods:{
        scoreList(a){
            switch(a){
                case 200:
                    return "Fast"
                    break;
                case 300:
                    return "Fast Enough"
                    break
                case 400:
                    return "Slow"
                    break
                case 500:
                    return "Too slow"
                    break
                default:
                    return "Veeeery slow"
            }
        }
    }
}
</script>

<style>

</style>