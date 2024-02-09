<template>
  <div>
    <h1>Home Page</h1>
    <input type="text" v-model="enteredName" placeholder="Enter your name"/>
    <button @click="checkName">Enter</button>
    <div v-if="showError" class="error-popup">
      You are not Dorcas!
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      enteredName: '',
      showError: false,
    };
  },
  methods: {
    checkName() {
      // Convert both input and comparison string to lowercase to ensure case-insensitive comparison
      if (this.enteredName.toLowerCase() === 'dorcas') {
        this.$router.push({ name: 'name' }); // Assuming 'name' is the name of the route you want to navigate to
      } else {
        this.showError = true;
        // Optionally hide the popup after some time
        setTimeout(() => {
          this.showError = false;
        }, 3000);
      }
    }
  }
};
</script>

<style scoped>
.error-popup {
  color: red;
}
</style>
