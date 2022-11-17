<template>
  <div>
    <div class="card">
      <div class="pokeImg">
        <img
          :src="pokeImg"
          alt=""
        />
      </div>
      <div class="pokeId">#{{pokeId}}</div>
      <div class="pokeName">{{pokeName}}</div>
      <div class="pokeType">{{pokeType}}</div>
    </div>
    <button @click="getPoke">POKE</button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      pokeImg: null,
      pokeId:null,
      pokeName: "at",
      pokeType: null,
      random:null
    };
  },
  methods: {
   async getPoke() {
      let randomId = Math.floor(Math.random() * 905 + 1);
      this.random = randomId;
      console.log(this.random);

      axios
        .get("" + this.random)
        .then((res) => {

            console.log(res)
          let pokemon = res.data;
            this.pokeImg=pokemon
            this.pokeId=pokemon.id
            this.pokeName=pokemon.name
            this.pokeType=pokemon.types[0].type.name
            this.pokeImg=`https://assets.pokemon.com/assets/cms2/img/pokedex/full/${this.pokeId}.png`


        });
    },
  },
};
</script>

<style lang="scss" scoped></style>
