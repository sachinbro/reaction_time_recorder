<template>
<div >
  <h1>Reaction Timer</h1>
  <button @click= "start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Results v-if="showResults" :score="score"/>
</div>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'
export default {
  name: 'App',
  components: {
    Block,
    Results
  },
  data(){
    return{
      isPlaying: false,
      showResults: false,
      delay: null,
      score:null,
    }
  },
  methods:{
    start(){
      this.delay = 1000 + Math.random()*5000
      this.isPlaying = true
      this.showResults = false
     
    },
    endGame(time){
      this.score = time
      this.isPlaying = false
      this.showResults = true
    },
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(253, 253, 253);
  margin-top: 60px;
  height: inherit;
}
div{
  height: inherit;
}
</style>
