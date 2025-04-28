<template>
    <div class="payment">
      <h2>Escolha o Método de Pagamento</h2>
  
      <div class="payment-options">
        <button @click="selectPayment('pix')">Pix</button>
        <button @click="selectPayment('card')">Cartão de Crédito</button>
        <button @click="selectPayment('boleto')">Boleto</button>
      </div>
  
      <div v-if="selectedPayment">
        <h3>Pagamento via: {{ selectedPayment }}</h3>
        <form @submit.prevent="submitPayment">
          <div v-if="selectedPayment === 'pix'">
            <label for="pix">Chave Pix</label>
            <input type="text" v-model="paymentInfo.pix" required />
          </div>
          <div v-if="selectedPayment === 'card'">
            <label for="cardNumber">Número do Cartão</label>
            <input type="text" v-model="paymentInfo.cardNumber" required />
          </div>
          <div v-if="selectedPayment === 'boleto'">
            <label for="boleto">Código do Boleto</label>
            <input type="text" v-model="paymentInfo.boleto" required />
          </div>
          <button type="submit">Confirmar Pagamento</button>
        </form>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const selectedPayment = ref(null)
  const paymentInfo = ref({
    pix: '',
    cardNumber: '',
    boleto: '',
  })
  
  function selectPayment(method) {
    selectedPayment.value = method
  }
  
  function submitPayment() {
    console.log(`Pagamento via ${selectedPayment.value} confirmado!`)
    // Simular comprovante e redirecionar para a tela final
  }
  </script>
  
  <style scoped>
  .payment {
    text-align: center;
    color: white;
    margin-top: 20px;
  }
  
  .payment-options button {
    margin: 10px;
    padding: 10px;
    background-color: #00b894;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  .payment-options button:hover {
    background-color: #019f83;
  }
  
  form {
    margin-top: 20px;
  }
  
  input {
    padding: 10px;
    margin: 10px 0;
    border-radius: 5px;
    border: 1px solid #ccc;
    width: 200px;
  }
  
  button {
    padding: 10px 20px;
    background-color: #00b894;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #019f83;
  }
  </style>  