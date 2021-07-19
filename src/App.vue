<template>
  <h1>Ninja Reaction Timer</h1>
  <button @click="play()" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Results v-if="showResults" :score="score"/>
</template>

<script>
import Block from "./components/Block.vue"
import Results from "./components/Result.vue"

export default {
  data(){
    return{
      delay: null,
      score: null,
      isPlaying: false,
      showResults:false
    }
  },
  components:{
    Block,
    Results
  },
  methods:{
    play(){
        this.delay = Math.floor((Math.random() * 5000) + 2000)
        this.isPlaying = true
        this.showResults = false
    },
    endGame(reactionTime){
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
