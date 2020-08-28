<template>
  <div>
    <div class="row">
      <div class="col-sm">
        <p style="font-size: 150%">{{aplayer.name}}</p>
        <p>
          <img v-bind:style="{width: aplayer.hp + 'px'}" :src="hp1" alt height="20px" />
        </p>
        <p style="font-size: 150%">{{thp}}{{aplayer.hp}}</p>
        <p>
          <img style="width:60%" :src="aplayer.image" />
        </p>
      </div>
      <div class="col-md">
        <div class="row ">
          <div class="col-md">
            <button class="btn btn-primary" @click="start()">StartBattle</button>
          </div>
          <div class="col-md">
            <button v-bind:disabled="end" class="btn btn-danger" @click="attack()">Attack</button>
          </div>
          <div class="col-md-5">
            <button v-bind:disabled="end" class="btn btn-dark" @click="special()">UltimatePower</button>
          </div>
          <div class="col-md-1">
            <button class="btn btn-light" @click="reset()">NewGame</button>
          </div>
          <br />
          <img class="rounded mx-auto d-block" 
            src="../assets/img/pngegg.png" width="40%"/>
        </div>
        <div class="row">
          <div class="col-md"></div>
          <div class="col-md">
            <div id="score">
              <div v-if="amonster.hp <= 0">You Win</div>
              <div v-else-if="aplayer.hp <= 0">You Lose</div>
            </div>
          </div>
          <div class="col-sm"></div>
        </div>
      </div>
      <div class="col-md">
        <p style="font-size: 150%">{{amonster.name}}</p>
        <p>
          <img v-bind:style="{width: amonster.hp + 'px'}" :src="hp2" alt height="25px" />
        </p>
        <p style="font-size: 150%">{{thp}}{{amonster.hp}}</p>
        <p>
          <img style="width:60%" :src="amonster.image" />
        </p>
      </div>
    </div>
    <hr />
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      thp: "HP:",
      end: false,
      hp2:
        "https://i.ppy.sh/bca61e3c2183a86ddb4c1d75914fab845e2b128f/687474703a2f2f692e696d6775722e636f6d2f6953766c5662432e706e67",
      hp1:
        "https://i.ppy.sh/bca61e3c2183a86ddb4c1d75914fab845e2b128f/687474703a2f2f692e696d6775722e636f6d2f6953766c5662432e706e67",
      aplayer: { name: "", hp: 1, image: "", hp1: "" },
      player: [
        {
          name: "Iron Man",
          hp: 220,
          image: require ( "../assets/img/iron_man.png"),
        },
        {
          name: "Captain America",
          hp: 330,
          image: require ( "../assets/img/captain-america.png"),
        },
        {
          name: "Thor",
          hp: 250,
          image: require ( "../assets/img/Thor.png"),
        },        
      ],
      amonster: { name: "", hp: 2, image: "", hp1: "" },
      monster: [
        {
          name: "Darth Vader",
          hp: 300,
          image: require ( "../assets/img/darth-vader-.png"),
        },
        {
          name: "Obi Wan ",
          hp: 250,
          image: require ( "../assets/img/obi-wan.png"),
        },
        {
          name: "Anakin skywalker",
          hp: 215,
          image: require ( "../assets/img/anakin-skywalker.png"),
        },
      ],
      pmax: "50%",
      mmax: "50% ",
    };
  },
  methods: {
    randomno: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
    start: function () {
      this.aplayer = this.player[this.randomno(1, 5) - 1];
      this.amonster = this.monster[this.randomno(1, 5) - 1];
    },
    attack: function () {
      this.pmax = Math.floor(Math.random() * 10 + 4);
      this.amonster.hp = this.amonster.hp - this.pmax;
      this.mmax = Math.floor(Math.random() * 10 + 4);
      this.aplayer.hp = this.aplayer.hp - this.mmax;
      if (this.aplayer.hp <= 0) {
        this.aplayer.hp = 0;
        this.end = true;
      } else if (this.amonster.hp <= 0) {
        this.amonster.hp = 0;
        this.end = true;
      }
    },
    special: function () {
      this.pmax = Math.floor(Math.random() * 50 + 6);
      this.amonster.hp = this.amonster.hp - this.pmax;
      this.mmax = Math.floor(Math.random() * 50 + 6);
      this.aplayer.hp = this.aplayer.hp - this.mmax;
      if (this.aplayer.hp <= 0) {
        this.aplayer.hp = 0;
        this.end = true;
      } else if (this.amonster.hp <= 0) {
        this.amonster.hp = 0;
        this.end = true;
      }
    },
    reset: function () {
      window.location.reload();
    },
  },
};
</script>
<style>
#score {
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  font-size: 450%;
  color: rgb(247, 1, 1);
}
</style>