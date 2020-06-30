<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <p>{{ massage }}</p>
    <hr>
    <div>
      <input type="text" v-model="input">
      <button v-on:click="doAction">Click</button>
    </div>
  </div>
</template>

<script>
export default{
  name:'Helloworld',
  props:{
    title:String,
  },
  data:function(){
    return{
      massage:'お名前は？',
      input:'no name',
    };
  },
  methods:{
    doAction:function(){
      this.massage = 'こんにちは、' + this.input + 'さん';
      this.$emit('result-event',this.input)
    }
  }
}
</script>

<style>
  div{
    margin:0px;
    padding:0px;
    text-align:left;
  }
  h1{
    font-size:72pt;
    font-weight: bold;
    text-align: ringht;
    letter-spacing: -8px;
    color:#f0f0f0;
    margin: 0px;
  }
  p{
    margin: 0px;
    color:#666;
    font-size:16pt;
  }
</style>
