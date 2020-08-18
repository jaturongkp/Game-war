<template>
  <div id="app">
    <div class="card">
      <div class="container">
        <div id="app2">
          <div class="card container">
            <img alt="redTeam" src="./img/darth-vader-.png" width="200px" />
            <HelloWorld msg="" />
          </div>
          <div class="card col-3">
            <img alt="redTeam" src="./img/anakin-skywalker.png" width="200px" />
            <HelloWorld msg="" />
          </div>
          <div class="card col-3">
            <img alt="redTeam" src="./img/obi-wan.png" width="200px" />
            <HelloWorld msg="" />
          </div>
        </div>
      </div>

      <div class="card col-3 container">
        <img alt="redTeam" src="./img/iron_man.png" width="200px" />
        <HelloWorld msg="" />
      </div>
      <div class="card col-3 container">
        <img alt="redTeam" src="./img/captain-america.png" width="200px" />
        <HelloWorld msg="" />
      </div>
      <div class="card col-3 container">
        <img alt="redTeam" src="./img/Thor.png" width="200px" />
        <HelloWorld msg="" />
      </div>
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
//import fightButton from "./components/fightButton.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    //fightButton,
  },
};
</script>

<style>
#app {
  background-image: url(./img/chris-kesler.jpg);
  background-size: cover;
}
#app2 {
  color: #2c3e50;
  float: right;
}
</style>
