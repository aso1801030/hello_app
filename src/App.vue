<template>
  <div id="app">
    <HelloWorld v-bind:title="massage" v-on:result-event='appAction' />
    <P>{{result}}</P>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data: function(){
    return{
      massage:"HELLO",
    };
  },
  methods:{
    doAction:function(){
      var input = prompt("new title:");
      this.massage = input;
    },
    appAction:function(massage){
      this.result = '(*** you send:"' + massage + '".***)'
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
