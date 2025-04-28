<template>
    <div class="cart">
      <h2>Seu Carrinho</h2>
  
      <div v-if="cart.length === 0">
        <p>Seu carrinho está vazio.</p>
      </div>
      <div v-else>
        <div v-for="item in cart" :key="item.id" class="cart-item">
          <img :src="item.image" :alt="item.title" class="cart-item-image" />
          <div class="cart-item-info">
            <h3>{{ item.title }}</h3>
            <p>{{ item.description }}</p>
            <button @click="removeFromCart(item.id)">Remover</button>
          </div>
        </div>
        <div class="cart-summary">
          <p>Total: {{ totalPrice }}</p>
          <button @click="checkout">Finalizar Compra</button>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const cart = ref([])
  
  // Função para adicionar item ao carrinho
  function addToCart(comic) {
    cart.value.push(comic)
  }
  
  // Função para remover item do carrinho
  function removeFromCart(itemId) {
    cart.value = cart.value.filter(item => item.id !== itemId)
  }
  
  // Função para calcular o preço total
  const totalPrice = computed(() => {
    return cart.value.reduce((total, item) => total + 9.99, 0) // Preço fixo de exemplo
  })
  
  // Função para finalizar a compra
  function checkout() {
    console.log("Iniciando o checkout...")
    // Redirecionar para a página de pagamento
  }
  </script>
  
  <style scoped>
  .cart {
    text-align: center;
    color: white;
    margin-top: 20px;
  }
  
  .cart-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 20px;
    background-color: #222;
    padding: 10px;
    border-radius: 8px;
  }
  
  .cart-item-image {
    width: 50px;
    height: 75px;
    object-fit: cover;
  }
  
  .cart-item-info {
    flex-grow: 1;
    margin-left: 10px;
  }
  
  .cart-summary {
    margin-top: 20px;
    font-size: 1.5rem;
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