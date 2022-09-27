<template>
  <h1>Ninja Reaction Timer</h1>
  <!-- disable button while isPlaying is true -->
  <button type="button" @click="start" :disabled="isPlaying">Play</button>
  <!-- the block component should show based on the delay time -->
  <Block v-if="isPlaying" :delay="delay" />
</template>

<script>
import Block from './components/Block';
export default {
  name: 'App',
  components: { Block },
  data() {
    return {
      isPlaying: false,
      delay: null,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      console.log(this.isPlaying, this.delay);
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

