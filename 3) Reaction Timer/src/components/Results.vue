<template>
  <h3>Your Reaction Time: {{ score }} ms</h3>
  <h2 class='rank'>{{ rank }}</h2>
</template>

<script>
export default {
  props: ['score'],
  data() {
    return {
      rank: null
    }
  },
  mounted() {
    if (this.score < 250) {
      this.rank = 'Ninja Fingers!!!'
    } else if (this.score < 350) {
      this.rank = 'Rapid Reflexes!!!'
    } else {
      this.rank = "You're a snail..."
    }
  }
}
</script>

<style>
  .rank {
    font-size: 1.6em;
    color: #0faf87;
    font-weight: bold;
  }
</style>