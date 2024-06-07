<template>
    <div class="navbar">
      <h1>{{ title }}</h1>
    </div>
  </template>
  
  <script>
  export default {
    name: "Navbar",
    data() {
      return {
        title: "LAB - WikiCountries"
      };
    }
  };
  </script>
  
  <style scoped>
  /* Estilos para el navbar */
  .navbar {
    background-color: #333;
    color: white;
    padding: 1rem;
  }
  
  .navbar h1 {
    margin: 0;
  }
  </style>
  