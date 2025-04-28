<template>
    <div class="rating">
      <h3>Avalie este Quadrinho:</h3>
      
      <div class="stars">
        <span
          v-for="star in 5"
          :key="star"
          :class="['star', { active: rating >= star }]"
          @click="setRating(star)"
        >
          ★
        </span>
      </div>
  
      <p v-if="rating > 0">Você avaliou com {{ rating }} estrelas!</p>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const rating = ref(0)
  
  function setRating(star) {
    rating.value = star
  }
  </script>
  
  <style scoped>
  .rating {
    text-align: center;
    margin-top: 20px;
    color: white;
  }
  
  .stars {
    font-size: 30px;
    cursor: pointer;
  }
  
  .star {
    color: #aaa;
  }
  
  .star.active {
    color: #ffd700;
  }
  
  p {
    margin-top: 10px;
    font-size: 18px;
  }
  </style>   