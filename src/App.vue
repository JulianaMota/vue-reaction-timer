<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Results v-if="showResults" :score="score" />
  <ResultTable v-if="showResults" :resultsArr="resultsArr"/>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'
import ResultTable from './components/ResultTable.vue'

export default {
  name: 'App',
  components: {
    Block,
    Results,
    ResultTable
  },
  data(){
    return{
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
      resultsArr: []
    }
  },
  methods:{
    start(){
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.showResults = false
    },
    endGame(reactionTime){
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
      this.resultsArr.push(reactionTime)
      console.log(this.resultsArr)
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
  color: #fff;
  margin-top: 60px;
}
button{
  background-color: rgba(238, 174, 202, 1);
  padding: 10px 30px;
  border: none;
  border-radius: 5px;
  box-shadow: 1px 1px 8px 2px #000;
  color: #fff;
  font-size:  20px;
  font-weight: bolder;
}
</style>
