<template>
    <div class="auth">
      <h2 v-if="isLogin">Login</h2>
      <h2 v-else>Registro</h2>
  
      <form @submit.prevent="handleSubmit">
        <input type="text" v-model="user.email" placeholder="Email" required />
        <input type="password" v-model="user.password" placeholder="Senha" required />
        <button type="submit">{{ isLogin ? 'Entrar' : 'Registrar' }}</button>
      </form>
  
      <p>
        <span @click="toggleAuth">{{ isLogin ? 'Não tem uma conta? Registre-se' : 'Já tem uma conta? Entre' }}</span>
      </p>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const isLogin = ref(true)
  const user = ref({
    email: '',
    password: '',
  })
  
  function handleSubmit() {
    if (isLogin.value) {
      console.log('Login com:', user.value)
    } else {
      console.log('Registro com:', user.value)
    }
  }
  
  function toggleAuth() {
    isLogin.value = !isLogin.value
  }
  </script>
  
  <style scoped>
  .auth {
    text-align: center;
    color: white;
  }
  
  input {
    padding: 10px;
    margin: 10px;
    width: 200px;
    border-radius: 5px;
    border: 1px solid #ccc;
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