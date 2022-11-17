<template>
  <div>
    <div class="card">
      <div class="pokeImg">
        <img
          src="https://assets.pokemon.com/assets/cms2/img/pokedex/full/150.png"
          alt=""
        />
      </div>
      <div class="pokeId">#150</div>
      <div class="pokeName">Mewtwo</div>
      <div class="pokeType">Pysic</div>
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
      pokeId: null,
      pokeName: null,
      pokeType: null,
    };
  },
  methods: {
    getPoke() {
      axios
        .get("https://pokeapi.co/api/v2/pokemon-form/150")
        .then(res => {
            console.log(res)
        }).catch(e=> console.log(e))
    }, 
  },
};
</script>

<style lang="scss" scoped></style>
