<template>
    <div class="best-week">
      <h2>Melhores Quadrinhos da Semana</h2>
      <div class="comics-list">
        <div class="comic" v-for="comic in bestComics" :key="comic.id">
          <img :src="comic.image" :alt="comic.title" />
          <h3>{{ comic.title }}</h3>
          <p>{{ comic.price }} R$</p>
          <button @click="addToCart(comic)">Adicionar ao Carrinho</button>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { reactive } from 'vue'
  
  const bestComics = reactive([
    { id: 5, title: 'Capitão América #2', price: 38, image: 'https://i.imgur.com/Cg5R3bT.jpg' },
    { id: 6, title: 'Pantera Negra #4', price: 42, image: 'https://i.imgur.com/6JpFPG4.jpg' },
    { id: 7, title: 'Homem de Ferro #7', price: 45, image: 'https://i.imgur.com/znV6lK9.jpg' },
  ])
  
  function addToCart(comic) {
    localStorage.setItem(`cart-${comic.id}`, JSON.stringify(comic))
    alert(`${comic.title} adicionado ao carrinho!`)
  }
  </script>
  
  <style scoped>
  .best-week {
    text-align: center;
    margin-top: 30px;
    color: white;
  }
  
  .comics-list {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 30px;
    margin-top: 20px;
  }
  
  .comic {
    background: #222;
    padding: 20px;
    border-radius: 10px;
    width: 220px;
    transition: transform 0.3s;
  }
  
  .comic:hover {
    transform: scale(1.05);
  }
  
  img {
    width: 180px;
    height: 260px;
    object-fit: cover;
    border-radius: 5px;
  }
  
  button {
    margin-top: 10px;
    background-color: #e62429;
    color: white;
    border: none;
    padding: 8px 16px;
    cursor: pointer;
    border-radius: 5px;
  }
  
  button:hover {
    background-color: white;
    color: #e62429;
  }
  </style>  