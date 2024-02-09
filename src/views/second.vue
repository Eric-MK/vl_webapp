<template>
    <div class="dorcas-container">
      <h2 class="greeting">🌹Fun Fact about the name Dorcas!🌹</h2>
      <p class="message">
        Dorcas is a name of Greek origin. In the Bible Dorcas is a warm woman who is known for her charitable acts and good works. She is also referred to as Tabitha, which is an Aaramaic name. It is a name that was popular in the early Christian church.
      </p>
      <button @click="showSurprise">Click for a Surprise</button>
        <div v-if="surprise">
            <div>
                <h1>Happy Valentines Babe!❤️</h1>
            </div>
            <div class="gallery">
                <img src="@/assets/F1.png" alt="Love" />
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

</style>
