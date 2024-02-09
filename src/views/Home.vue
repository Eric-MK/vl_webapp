<template>
  <div>
    <h1>Home Page</h1>
    <input type="text" v-model="enteredName" placeholder="Enter your name"/>
    <button @click="checkName">Enter</button>
    <!-- Error Popup Modal -->
    <div v-if="showError" class="modal-overlay" @click="showError = false">
      <div class="modal">
        You are not Dorcas!
        <div><button @click="showError = false">Close</button></div>
        
      </div>
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
      if (this.enteredName.toLowerCase() === 'dorcas') {
        this.$router.push({ name: 'name' }); // Navigate to the 'name' route
      } else {
        this.showError = true;
      }
    }
  }
};
</script>

<style scoped>
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.6); /* Darker overlay for more focus */
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000; /* Ensure it's above other content */
}

.modal {
  background-color: #ffe0f0; /* Soft pink background */
  padding: 30px;
  border-radius: 15px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
  width: 90%; /* Responsive width */
  max-width: 400px; /* Max width to avoid overly wide modals on large screens */
  text-align: center; /* Center the text inside the modal */
}

.modal button {
  padding: 10px 20px;
  margin-top: 20px;
  border: none;
  background-color: #e63946; /* Valentine's red */
  color: white;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.modal button:hover {
  background-color: #ff6b6b; /* Lighter shade on hover */
}

/* Optional: Add some animation to make the popup appear more dynamic */
@keyframes popup {
  from {
    transform: translateY(-20px);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

.modal {
  animation: popup 0.3s ease-out;
}
</style>

