<template>
    <div class="dorcas-container">
        <h2 class="greeting">🌹Fun Fact about the name Dorcas!🌹</h2>
        <p class="message">
            Dorcas is a name of Greek origin. In the Bible, Dorcas is a woman known for her charitable acts and good works. She is also referred to as Tabitha, which is an Aramaic name. It is a name that was popular in the early Christian church.
        </p>
        <button @click="showSurprise">Click for a Surprise</button>
        <div v-if="surprise" class="modal-overlay" @click.self="surprise = false">
            <div class="modal">
                <h1 class="h1-valentine">Happy Valentine's Babe!❤️</h1>
                <div class="gallery">
                    <img src="@/assets/F1.png" alt="Love" />
                </div>
                <button @click="surprise = false">Close</button>
            </div>
        </div>
    </div>
</template>

  

<script>
export default {
  name: 'DorcasMessage',
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
.dorcas-container {
  max-width: 800px;
  margin: auto;
  margin-top: 80px;
  padding: 20px;
  text-align: center;
  background-color: #ffe0f0;
  border-radius: 15px;
  color: #333;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.h1-valentine {
  font-family: 'Great Vibes', cursive;
  font-size: 48px; /* Adjust the size as needed */
  color: #e63946; /* Feel free to change the color */
}

.greeting {
  color: #e63946;
  margin-bottom: 15px;
}

.message {
  font-size: 18px;
  line-height: 1.6;
}



.heart-animation:before,
.heart-animation:after {
  content: "";
  width: 100px;
  height: 150px;
  background-color: pink;
  border-radius: 50%;
  position: absolute;
  top: -60px;
  left: 0;
}

.heart-animation:after {
  left: 60px;
  top: -60px;
}

.gallery img {
  max-width: 100%;
  height: auto;
  border-radius: 8px;
}

button {
  margin-top: 20px;
  padding: 10px 20px;
  font-size: 16px;
  color: #fff;
  background-color: #e63946;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
  margin-top: 20px;
}

button:hover {
  background-color: #ff6b6b;
}

.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal {
  background-color: #fff;
  padding: 20px;
  border-radius: 8px;
  max-width: 500px;
  height: 97%;
  text-align: center;
  
}

/* Add or modify button styles here if necessary */


</style>
