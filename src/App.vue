<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
   <h1> {{total}} </h1>
    <div class="row">
      <div class="col-6"><game lable="ok" @cc="sum" /></div>
      <div class="col-6"><game lable="ชอบ" @cc="sum"/></div>
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import game from "./components/game.vue";
export default {
  name: "App",
  components: {
    HelloWorld,
    game,
  },
  data:function(){
    return{
    total: 0,
    name:'',
    code:'',
    gpa:0.1,
    }
  },
  methods:{
    sum(counterValue){
    this.total +=counterValue
    }
  }
};
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
