<template>
  <h1>Ninja Reaction Timer</h1>
  <!-- disable button while isPlaying is true -->
  <button type="button" @click="start" :disabled="isPlaying">Play</button>
  <!-- the block component should show based on the delay time -->
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <p v-if="showResult">Reaction Time: {{ score }}ms</p>
</template>

<script>
import Block from './components/Block';
export default {
  name: 'App',
  components: { Block },
  data() {
    return {
      isPlaying: false,
      showResult: false,
      delay: null,
      score: null,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 3000;
      this.isPlaying = true;
      this.showResult = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResult = true;
    },
  },
};
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

