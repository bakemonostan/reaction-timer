<template>
  <h3> Reaction time - {{ score }}ms</h3>
  <p class="rank">{{ rank }} </p>
</template>

<script>
export default {
  props: ['score'],
  data() {
    return {
      rank: '',
    };
  },
  mounted() {
    if (this.score < 250) {
      this.rank = 'Ninja Fingers 🚀';
    } else if (this.score < 400) {
      this.rank = 'Sakura is faster 😑';
    } else {
      this.rank = "You'll never be Hokage 😢";
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.4em;
  background: #0faf87;
  color: white;
  font-weight: bold;
  width: 200px;
  margin: 0 auto;
  padding: 0.7rem;
  border-radius: 4px;
}
</style>
