<template>
  <div class="home-container">
    <div>
      <h1>Hey There!</h1>
      <input type="text" v-model="enteredName" placeholder="Enter your name"/>
      <button @click="checkName">Enter</button>
      <!-- Error Popup Modal -->
      <div v-if="showError" class="modal-overlay" @click="showError = false">
        <div class="modal">
          You are not Dorcas!
          <div><button @click="showError = false">Close</button></div>
        </div>
      </div>
      <!-- Success Popup Modal -->
      <div v-if="showSuccess" class="modal-overlay" @click="showSuccess = false">
        <div class="modal success">
          Welcome Dorcas!❤️
        </div>
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
      showSuccess: false, // New property for showing success message
    };
  },
  methods: {
    checkName() {
      if (this.enteredName.toLowerCase() === 'dorcas') {
        // Instead of navigating directly, show success message
        this.showSuccess = true; 
        // Add a delay before navigation to allow user to read the message
        setTimeout(() => {
          this.$router.push({ name: 'name' });
        }, 3000); // Adjust the delay as needed
      } else {
        this.showError = true;
      }
    }
  }
};
</script>

<style scoped>

.home-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh; /* Full height of viewport */
  text-align: center; /* Center text */
}

input[type="text"] {
  max-width: 300px;
  width: 100%; /* Full width */
  padding: 12px 20px;
  margin: 8px 0; /* Spacing */
  display: inline-block;
  border: 1px solid #ccc; /* Light grey border */
  border-radius: 4px; /* Rounded borders */
  box-sizing: border-box; /* Box sizing */
  transition: border-color 0.3s ease-in-out;
}

input[type="text"]:focus {
  border-color: #e63946; /* Valentine's red when focused */
  outline: none; /* Remove default focus outline */
}

button {
  width: auto; /* Auto width based on content */
  padding: 10px 20px; /* Padding */
  background-color: #e63946; /* Valentine's red */
  color: white; /* Text color */
  border: none; /* No border */
  border-radius: 5px; /* Rounded corners */
  cursor: pointer; /* Pointer cursor on hover */
  transition: background-color 0.3s ease; /* Smooth background color transition */
  margin-top: 10px; /* Margin top for spacing */
}

button:hover {
  background-color: #ff6b6b; /* Lighter shade on hover */
}


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

.success {
  background-color: #e0ffe0; /* Soft green background for success */
}

.success button {
  background-color: #4CAF50; /* Green */
}
</style>

