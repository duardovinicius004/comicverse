<template>
    <div class="catalog">
      <h2>Catálogo de Quadrinhos</h2>
  
      <div class="catalog-items">
        <div class="item" v-for="comic in comics" :key="comic.id">
          <img :src="comic.image" :alt="comic.title" class="comic-image" />
          <div class="comic-info">
            <h3>{{ comic.title }}</h3>
            <p>{{ comic.description }}</p>
            <button @click="addToCart(comic)">Adicionar ao Carrinho</button>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const comics = ref([
    {
      id: 1,
      title: 'Spider-Man',
      description: 'O Homem-Aranha em uma nova aventura.',
      image: 'https://via.placeholder.com/200x300?text=Spider-Man',
    },
    {
      id: 2,
      title: 'Iron Man',
      description: 'A batalha de Tony Stark contra os vilões.',
      image: 'https://via.placeholder.com/200x300?text=Iron+Man',
    },
    {
      id: 3,
      title: 'Captain America',
      description: 'O Capitão América defende o país.',
      image: 'https://via.placeholder.com/200x300?text=Captain+America',
    },
  ])
  
  function addToCart(comic) {
    console.log(`${comic.title} adicionado ao carrinho.`)
  }
  </script>
  
  <style scoped>
  .catalog {
    text-align: center;
    color: white;
    margin-top: 20px;
  }
  
  .catalog h2 {
    font-size: 2.5rem;
    margin-bottom: 20px;
  }
  
  .catalog-items {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
  }
  
  .item {
    background-color: #222;
    padding: 20px;
    border-radius: 8px;
    width: 200px;
    text-align: center;
  }
  
  .comic-image {
    max-width: 100%;
    border-radius: 8px;
  }
  
  .comic-info {
    margin-top: 10px;
  }
  
  .comic-info h3 {
    font-size: 1.2rem;
    margin: 10px 0;
  }
  
  .comic-info p {
    font-size: 1rem;
    margin-bottom: 10px;
  }
  
  button {
    background-color: #00b894;
    color: white;
    border: none;
    padding: 10px 20px;
    cursor: pointer;
    border-radius: 5px;
  }
  
  button:hover {
    background-color: #019f83;
  }
  </style>      