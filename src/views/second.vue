<template>
    <div class="dorcas-container">
      <h2 class="greeting">Happy Valentine's Day, Dorcas!</h2>
      <p class="message">
        Just like your name suggests, you bring kindness and compassion to everyone around you. 
        Your warmth lights up the darkest days, and your caring heart makes the world a better place. 
        Here's to celebrating the wonderful person you are, Dorcas. 💖
      </p>
      <div class="heart-animation"></div>
    </div>
</template>
  

<script>
export default {
  name: 'DorcasMessage'
};
</script>


<style scoped>
.dorcas-container {
  max-width: 600px;
  margin: auto;
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

.heart-animation {
  margin-top: 20px;
  width: 100px;
  height: 90px;
  background-color: pink;
  position: relative;
  display: inline-block;
  transform: rotate(45deg);
  margin: 40px auto 0;
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
</style>
