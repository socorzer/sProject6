<template>
  <div id="app">
    <br />
    <img class="" src="https://seeklogo.com/images/M/Marvel_Comics-logo-D489AEB9C1-seeklogo.com.png" width="20%" />
    <HelloWorld msg = "Chaos War" />
    <br />
    
    <div>
      <bt />
    </div>
  </div>
</template>
<script>
import HelloWorld from "./components/HelloWorld.vue";
import bt from "./components/bt.vue";
export default {
  name: "App",
  components: {
    HelloWorld,
    bt,
  },
};
</script>

<style>
#app {
  background-image: url(https://imgs.abduzeedo.com/files/articles/wicked-fighting-game-background-gifs/zW8idqja.gif);
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  position: relative;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color:azure;
}
</style>
