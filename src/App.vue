<template>
  
  <h1>Test Your "Click" Skill</h1>
  <h2>How fast can u clicK?</h2>
  <button @click="start" :disabled="isPlaying">Play</button>
  <div v-if="isPlaying">
    <Block :delay="delay" @end="showResult"></Block>
  </div>
  <div v-if="eend">
  <Result :score="score"/>
  </div>
</template>

<script>
import Block from "./components/Block.vue"
import Result from "./components/Result.vue"
export default {
  name: 'App',
  components: {
   Block,
   Result
  },
  data(){
    return {
      isPlaying : false,
      delay : null,
      score : 0,
      eend : false
    }
  },
  methods:{
    start(){
       this.isPlaying = true;
       this.delay = Math.random()*(5000-2000+1)+2000;
    },
    showResult(score){
      this.score = score;
      this.isPlaying = false;
      this.eend= true;
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
  color: #2c3e50;
  margin-top: 60px;
}
</style>
