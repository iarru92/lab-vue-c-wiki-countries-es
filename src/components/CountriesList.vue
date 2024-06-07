<template>
    <div class="countries-list">
      <h2>Lista de Países</h2>
      <ul>
        <li v-for="country in countries" :key="country.alpha3Code">
          <router-link :to="'/list/' + country.alpha3Code">{{ country.name }}</router-link>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    name: "CountriesList",
    data() {
      return {
        countries: [
          { alpha3Code: "ESP", name: "España" },
          { alpha3Code: "FRA", name: "Francia" },
          { alpha3Code: "ITA", name: "Italia" },
          // Agrega más países según sea necesario
        ]
      };
    }
  };
  </script>
  
  <style scoped>
  /* Estilos para la lista de países */
  .countries-list {
    margin-top: 20px;
  }
  
  .countries-list h2 {
    margin-bottom: 10px;
  }
  
  .countries-list ul {
    list-style-type: none;
    padding: 0;
  }
  
  .countries-list li {
    margin-bottom: 5px;
  }
  
  /* Estilos para los enlaces */
  .router-link-active {
    font-weight: bold;
  }
  </style>
  