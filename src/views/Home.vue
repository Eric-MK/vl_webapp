<template>
  <div class="home">
    <h1>Hey Beutiful!</h1>
    <p>Whats your name?</p>
    
    
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      surprise: false,
    };
  },
  methods: {
    showSurprise() {
      this.surprise = !this.surprise;
    },
  },
};
</script>

<style scoped>
.home {
  text-align: center;
  padding: 20px;
}

.gallery img {
  max-width: 100%;
  height: auto;
  border-radius: 8px;
}
</style>
