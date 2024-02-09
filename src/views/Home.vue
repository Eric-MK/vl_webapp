<template>
  <div class="home">
    <h1>Hey Beutiful!</h1>
    <p>Whats your name?</p>
    
    <button @click="showSurprise">Click for a Surprise</button>
    <div v-if="surprise">
      <div class="gallery">
        <img src="@/assets/F1.png" alt="Love" />
      </div>
    </div>
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
