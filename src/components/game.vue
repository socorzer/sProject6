<template>
  <div>
    <p>HP Player {{randomCharacter(1,3)}} 
      {{player[randomCharacter(1,3)-1].name }}

    </p>
    <hr>
    <div id="example-1">
      <button @click="upFunction" class="btn btn-dark">{{lable}}</button>
      <button @click="downFunction" class="btn btn-dark ml-3">-</button>
      <p v-bind:style="{ fontSize: fsize + 'px' }">{{ counter }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      player: [
        { name: "Anakin", hp: "90" },
        { name: "Ironman", hp: "20" },
        { name: "Doraemon", hp: "10" },
      ],
      Monster: [
        { name: "Darth veder", hp: "90" /*img= "#"*/},
        { name: "Thanos", hp: "20" },
        { name: "Darth mor", hp: "10" },
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
    randomCharacter: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
    start:function(){
// 1. random player
// 2. random monster

    },
    attack:function(){
// 1. player ---> monster
// 2. player <--- monster
// 3. player.hp =0 ---> ?
// 4. monster.hp =0 ---> ?
// 5. end game

    }
  },
};
</script>

<style>
</style>