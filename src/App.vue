<template>
  <div class="app">
    <NavBar />
    <router-view />
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import NavBar from "./components/NavBar.vue";

const countries = ref([]);

onMounted(() => {
  // Cargar los datos de países desde la API cuando el componente se monte
  fetchCountriesData();
});

async function fetchCountriesData() {
  try {
    const response = await fetch('https://ih-countries-api.herokuapp.com/countries');
    const data = await response.json();
    countries.value = data;
  } catch (error) {
    console.error('Error al cargar los datos de países desde la API:', error);
  }
}
</script>


<style>
/* Estilos para la aplicación */
.app {
  padding: 20px;
}
</style>
