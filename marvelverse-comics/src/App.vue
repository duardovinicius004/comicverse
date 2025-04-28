<template>
  <div id="app">
    <div v-if="showWelcome">
      <Welcome @start="startApp" />
    </div>

    <div v-else>
      <header>
        <nav>
          <ul>
            <li @click="navigate('home')">Página Inicial</li>
            <li @click="navigate('catalog')">Catálogo</li>
            <li @click="navigate('best')">Melhores da Semana</li>
            <li @click="navigate('cart')">Carrinho ({{ cart.length }})</li>
            <li @click="navigate('auth')">Login/Registro</li>
          </ul>
        </nav>
      </header>

      <main>
        <Home v-if="currentPage === 'home'" @navigate="navigate" />
        <Catalog v-if="currentPage === 'catalog'" @navigate="navigate" />
        <BestOfWeek v-if="currentPage === 'best'" />
        <Cart v-if="currentPage === 'cart'" />
        <Payment v-if="currentPage === 'payment'" />
        <Auth v-if="currentPage === 'auth'" />
      </main>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'
import Welcome from './views/Welcome.vue'
import Home from './views/Home.vue'
import Catalog from './views/Catalog.vue'
import BestOfWeek from './views/BestOfWeek.vue'
import Cart from './views/Cart.vue'
import Payment from './views/Payment.vue'
import Auth from './views/Auth.vue'

const showWelcome = ref(true)
const currentPage = ref('home')  // Página inicial
const cart = ref([])

// Função de navegação entre páginas
function navigate(page) {
  currentPage.value = page
}

// Função para esconder a tela de boas-vindas e mostrar a aplicação
function startApp() {
  showWelcome.value = false
}
</script>

<style scoped>
#app {
  text-align: center;
  color: white;
}

header {
  background-color: #333;
  padding: 10px;
}

header nav ul {
  list-style: none;
  padding: 0;
}

header nav ul li {
  display: inline;
  margin: 0 10px;
  cursor: pointer;
}

header nav ul li:hover {
  text-decoration: underline;
}

main {
  margin-top: 20px;
}
</style>