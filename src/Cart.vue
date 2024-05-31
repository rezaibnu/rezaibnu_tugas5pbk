<template>
    <div>
      <h2>Shopping Cart</h2>
      <div v-if="cart.length">
        <div v-for="item in cart" :key="item.id" class="cart-item">
          <h3>{{ item.name }}</h3>
          <p>{{ item.price }}</p>
          <button @click="removeFromCart(item)">Remove</button>
        </div>
        <p>Total: {{ totalPrice }}</p>
      </div>
      <div v-else>
        <p>Your cart is empty.</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Cart',
    props: ['cart'],
    computed: {
      totalPrice() {
        return this.cart.reduce((total, item) => total + parseFloat(item.price.substring(1)), 0).toFixed(2);
      }
    },
    methods: {
      removeFromCart(item) {
        this.$emit('remove-from-cart', item);
      }
    }
  }
  </script>
  
  <style scoped>
  .cart-item {
    border: 1px solid #e7e7e7;
    padding: 10px;
    margin: 10px 0;
  }
  </style>
  