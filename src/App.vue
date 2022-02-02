<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <SayingsDisplay :saying=this.sayings[this.activeSayingNum] @next="increaseSayingNum" @previous="decreaseSayingNum"/>
  </div>
</template>

<script>
import SayingsDisplay from './components/SayingsDisplay'

export default {
  name: 'App',
  components: {
    SayingsDisplay
  },
  data() {
    return {
      sayings: [
        "I likes me a sammich",
        "Hey is that a tentacle",
        "Cheese is delicious",
        "Dude, wheres my car?"
        ],
      activeSayingNum: 0
    }
  },
  methods: {
    increaseSayingNum() {
      this.activeSayingNum +=1;
      if(this.activeSayingNum>=this.sayings.length){
        this.activeSayingNum = 0;
      }
      console.log(this.activeSayingNum);
    },
    decreaseSayingNum() {
      this.activeSayingNum -=1;
      if(this.activeSayingNum<0){
        this.activeSayingNum = this.sayings.length-1;
      }
      console.log(this.activeSayingNum);
    },
    ticketyBoo(){
      console.log("ticketyBoo");
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
