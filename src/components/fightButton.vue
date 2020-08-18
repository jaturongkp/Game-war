<template>
  <div>
    <button v-on:click="randomDamage(0,100)" class="btn btn-warning">START  {{player[randomDamage(0,2)].name}}</button>
    <button v-on:click="randomDamage(10,100)" class="btn btn-warning">Random {{ randomNo }}</button>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      counter: 0,
      fsize: 50,
      randomNo: 0,
      player: [
        { name: "I", hp: 100, image: "" },
        { name: "D", hp: 100, image: "" },
        { name: "A", hp: 100, image: "" },
      ],
      Monster: [
        { name: "T", hp: 100, image: "" },
        { name: "C", hp: 100, image: "" },
        { name: "P", hp: 100, image: "" },
      ],
    };
  },
  props: {
    lable: String,
  },
  methods: {
    randomDamage: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
  },
};
</script>
<style>
</style>