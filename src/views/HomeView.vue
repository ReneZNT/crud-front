<script setup>
import ProductCard from '../components/ProductCard.vue';
import ListProducts from '../components/ListProducts.vue';

</script>

<template>
  <main>
    <ProductCard @add-product="addProduct" />
    <ListProducts :products="products" />
  </main>
</template>

<script>
export default {
  components: {
    ProductCard,
    ListProducts,
  },

  data() {
    return {
      products: [],
    };
  },

  methods: {
    addProduct(product) {
      console.log(product);
      this.products.push(product);
    },
  },
};

</script>

<style scoped>

</style>
