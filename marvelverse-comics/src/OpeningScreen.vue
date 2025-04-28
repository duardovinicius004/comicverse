<template>
    <div class="opening">
      <div class="comic-open">
        <h1>Bem-vindo ao MarvelVerse Comics!</h1>
      </div>
    </div>
  </template>
  
  <script setup>
  import { onMounted } from 'vue'
  
  // Emite um evento para avisar que a abertura terminou
  const emit = defineEmits(['finish'])
  
  onMounted(() => {
    setTimeout(() => {
      emit('finish')
    }, 3000) // 3 segundos de abertura
  })
  </script>
  
  <style scoped>
  .opening {
    width: 100vw;
    height: 100vh;
    background: linear-gradient(45deg, #000, #111);
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }
  
  .comic-open {
    animation: openComic 2s ease forwards;
  }
  
  @keyframes openComic {
    0% {
      transform: scaleX(0); /* Começa fechado */
    }
    100% {
      transform: scaleX(1); /* Abre totalmente */
    }
  }
  
  h1 {
    font-size: 3rem;
    color: red;
  }
  </style>    