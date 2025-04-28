<template>
    <div class="home">
      <header class="header">
        <h1>MarvelVerse Comics</h1>
        <nav class="nav">
          <button @click="$emit('navigate', 'catalog')">Catálogo</button>
          <button @click="$emit('navigate', 'best')">Melhores da Semana</button>
          <button @click="$emit('navigate', 'cart')">Carrinho</button>
        </nav>
      </header>
  
      <section class="banner">
        <h2>Explore o Universo Marvel em Quadrinhos!</h2>
      </section>
    </div>
  </template>
  
  <script setup>
  </script>
  
  <style scoped>
  .home {
    text-align: center;
    color: white;
  }
  
  .header {
    background-color: #e62429;
    padding: 20px;
  }
  
  .header h1 {
    margin: 0;
    font-size: 2.5rem;
  }
  
  .nav {
    margin-top: 15px;
  }
  
  .nav button {
    margin: 0 10px;
    padding: 10px 20px;
    background-color: black;
    color: white;
    border: 2px solid white;
    border-radius: 5px;
    cursor: pointer;
    font-weight: bold;
    transition: 0.3s;
  }
  
  .nav button:hover {
    background-color: white;
    color: black;
  }
  
  .banner {
    margin-top: 40px;
    background: url('https://i.imgur.com/H5W5Rzp.jpg') no-repeat center;
    background-size: cover;
    height: 400px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  
  .banner h2 {
    background-color: rgba(0, 0, 0, 0.6);
    padding: 20px;
    border-radius: 10px;
  }
  </style>  