<template>
  <h1>Yun's Reaction Timer Game</h1>
  <button @click='start' :disabled='isPlaying'>Play</button>

  <Block v-if='isPlaying' :delay='delay' @endOfGame='endGame' />

  <!-- <p v-if='showResults'>Score: {{ score }} ms</p> -->
  <Results v-if='showResults' :score='score' />
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  components: { Block, Results },
  data() {
    return {
      isPlaying: false,
      showResults: false,
      delay: null,
      score: null
    }
  },
  methods: {
    start() {
      this.isPlaying = true,
      this.showResults = false,
      this.delay = 2000 + (Math.random() * 5000)
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.showResults = true
      this.isPlaying = false
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
