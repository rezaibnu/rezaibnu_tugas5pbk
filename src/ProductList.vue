<template>
    <div>
      <h2>Products</h2>
      <div v-if="products.length">
        <div v-for="product in products" :key="product.id" class="product">
          <h3>{{ product.name }}</h3>
          <p>{{ product.description }}</p>
          <p>{{ product.price }}</p>
          <button @click="addToCart(product)">Add to Cart</button>
        </div>
      </div>
      <div v-else>
        <p>No products available.</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ProductList',
    data() {
      return {
        products: [
          { id: 1, name: 'Product 1', description: 'Description 1', price: '$10' },
          { id: 2, name: 'Product 2', description: 'Description 2', price: '$20' }
        ]
      }
    },
    methods: {
      addToCart(product) {
        this.$emit('add-to-cart', product);
      }
    }
  }
  </script>
  
  <style scoped>
  .product {
    border: 1px solid #ece3e3;
    padding: 10px;
    margin: 10px 0;
  }
  </style>
    