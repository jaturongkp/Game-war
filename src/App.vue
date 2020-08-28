<template>
  <div id="app">
        <div class="battle">Battle Warfare</div>
    <br />
    <img class="rounded-circle" />
    <br />    
    <div>
      <herose />
    </div>
  </div>

</template>

<script>
import herose from "./components/herose";
export default {
  name: "App",
  components: {
    herose,
  },
};
</script>

<style>
body{
  background-image: url("./assets/img/fighting.gif");
 font-family: 'Times New Roman', Times, serif;
 background-size: cover;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #edf1f5;

}
.battle{
  font-size: 50px;
  margin-top: 20px;
  color: rgb(255, 255, 255);
  
}

</style>
