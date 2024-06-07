<template>
    <div v-if="country">
      <h2>{{ country.name }}</h2>
      <p>Capital: {{ country.capital }}</p>
      <p>Population: {{ country.population }}</p>
      <!-- Agrega más detalles según sea necesario -->
    </div>
  </template>
  
  <script setup>
  import { ref, watchEffect } from 'vue';
  import { useRouter } from 'vue-router';
  
  const country = ref(null);
  const router = useRouter();
  
  watchEffect(() => {
    // Obtener el alpha3Code del país de la URL
    const alpha3Code = router.currentRoute.value.params.alpha3Code;
  
    // Hacer la solicitud a la API para obtener los datos del país específico
    fetchCountryData(alpha3Code);
  });
  
  async function fetchCountryData(alpha3Code) {
    try {
      const response = await fetch(`https://ih-countries-api.herokuapp.com/countries/${alpha3Code}`);
      const data = await response.json();
      country.value = data;
    } catch (error) {
      console.error('Error al cargar los datos del país desde la API:', error);
    }
  }
  </script>
  