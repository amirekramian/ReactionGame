<template>
<h1>Reaction Timer</h1>
<button :disabled="IsPlaying" @click="StartGame" class="btn btn-danger">Play</button>
<p v-if="!IsPlaying">When you click on 'Play' button, apeare an area and you must click on it as soon as you can...</p>
<Block v-if="IsPlaying" :delay="delay" :IsPlaying="IsPlaying" @endtimer="endGame" />
<NOtPlayedDiv v-if="!IsPlaying" />
<Result v-if="score !=null" :result="score" />
</template>

<script>
//import HelloWorld from './components/HelloWorld'

import Block from './components/Block-Part'
import Result from './components/Result-Part'
import NOtPlayedDiv from './components/NOtPlayed-Part'

export default {
  name: 'App',
  components: {
    //HelloWorld
    Block,
    Result,
    NOtPlayedDiv
  },
  data(){
return{
  IsPlaying:false,
  delay:null,
  score:null
}
  },
  methods:{
    StartGame(){
      this.delay = 2000 + Math.random()*5000
      this.IsPlaying = true
      this.score = null
    },
    endGame(reactiontime){
      this.score = reactiontime
      this.IsPlaying = false
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
