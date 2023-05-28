<template>
  <div class="block" v-if="showBlock" @click="StopTimer"> Click Me</div>
</template>

<script>
export default {
props:['delay'],
data(){
    return{
        showBlock: false,
        Timer:null,
        ReactionTime:0
    }
},
mounted(){
    console.log("Block","Component Mounted")
  setTimeout(() => {
    this.showBlock = true
    this.StartTimer()
    console.log(this.delay)
  }, this.delay);
},
updated(){
    console.log("Block","component Updated")

},
unmounted(){
console.log("Block","Component Unmounted")
},
methods:{
    StartTimer(){
        this.Timer = setInterval(() => {
            this.ReactionTime +=10
        }, 10);
    },
    StopTimer(){
        clearInterval(this.Timer)
         this.$emit('endtimer', this.ReactionTime)
         }
}
}
</script>

<style>
.block{
    width: 400px;
    border-radius: 20px;
    background: #1782c0;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}
</style>