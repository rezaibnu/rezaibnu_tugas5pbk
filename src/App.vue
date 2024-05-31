<template>
  <div id="app">
    <Header :cartItemCount="cartItemCount" />
    <router-view @add-to-cart="addToCart" @remove-from-cart="removeFromCart" :cart="cart" />
    <Footer />
  </div>
</template>

<script>
import Header from './Header.vue';
import Footer from './Footer.vue';
import ProductList from './ProductList.vue';
import Cart from './Cart.vue';

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    ProductList,
    Cart
  },
  data() {
    return {
      cart: []
    }
  },
  computed: {
    cartItemCount() {
      return this.cart.length;
    }
  },
  methods: {
    addToCart(product) {
      this.cart.push(product);
    },
    removeFromCart(product) {
      this.cart = this.cart.filter(item => item.id !== product.id);
    }
  }
}
</script>

<style>
body {
  font-family: Arial, sans-serif;
  margin: 100;
  padding: 0;
}
</style>
