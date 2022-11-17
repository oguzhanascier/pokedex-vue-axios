<template>
  <div>
    <button class="changePoke" @click="getId">Random Pokemon</button>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {
    getId() {
      let randomNumber = Math.floor(Math.random() * 905 + 1);

      this.$emit('randomID', randomNumber)
      console.log("button component", randomNumber)
    },
  },
};
</script>

<style lang="scss" scoped></style>
