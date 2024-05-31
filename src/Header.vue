<template>
    <header>
      <h1>Toko Kue Adelina</h1>
      <nav>
        <router-link to="/">Home</router-link>
        <router-link to="/cart">Product ({{ cartItemCount }})</router-link>
      </nav>
    </header>
  </template>
  
  <script>
  export default {
    name: 'Header',
    props: ['cartItemCount']
  }
  </script>
  
  <style scoped>
  header {
    background-color: #0b0b0c;
    padding: 10px 20px;
    border-bottom: 1px solid #080808;
  }
  nav a {
    margin: 0 15px;
  }
  </style>
  