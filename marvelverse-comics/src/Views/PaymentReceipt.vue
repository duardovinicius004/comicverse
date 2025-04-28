<template>
    <div class="payment-receipt">
      <h2>Comprovante de Pagamento</h2>
      
      <p><strong>ID da Transação:</strong> {{ transactionId }}</p>
      <p><strong>Valor Pago:</strong> R$ {{ paymentAmount }}</p>
      <p><strong>Forma de Pagamento:</strong> {{ paymentMethod }}</p>
      
      <div class="receipt-actions">
        <button @click="goToCatalog">Voltar ao Catálogo</button>
        <button @click="goToHome">Voltar à Página Inicial</button>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  // Propriedades do pagamento
  const transactionId = ref(Math.floor(Math.random() * 1000000000)) // Gerando um ID aleatório para a transação
  const paymentAmount = ref('30.00') // Valor do pagamento
  const paymentMethod = ref('Cartão de Crédito') // Método de pagamento utilizado
  
  const goToCatalog = () => {
    // Lógica para voltar ao catálogo
    window.location.href = '#catalog'
  }
  
  const goToHome = () => {
    // Lógica para voltar à página inicial
    window.location.href = '#home'
  }
  </script>
  
  <style scoped>
  .payment-receipt {
    text-align: center;
    color: white;
    margin-top: 30px;
  }
  
  .receipt-actions {
    margin-top: 20px;
  }
  
  .receipt-actions button {
    padding: 10px 20px;
    margin: 10px;
    background-color: #444;
    color: white;
    border: none;
    cursor: pointer;
  }
  
  .receipt-actions button:hover {
    background-color: #555;
  }
  </style>  