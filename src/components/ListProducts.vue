
<template>
  <div class="lista-produtos">
    <h2>Lista de Produtos</h2>
    <ul>
      <li v-for="product in products" :key="product.id">
        <h3>{{ product.name }}</h3>
        <p>Preço: {{ product.price }}</p>
        <p>Descrição: {{ product.description }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    products: {
      type: Array,
      default: () => [],
    },
  },

  setup() {
    return {};
  },

  methods: {
  //
  },
  mounted() {
    console.log('produtos:' + this.products);
  },

};
</script>

<style scoped>
.lista-produtos {
  margin-top: 20px;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  border: 1px solid #ddd;
  padding: 10px;
  margin-bottom: 10px;
  border-radius: 4px;
}

h3 {
  margin: 0;
}

p {
  margin: 5px 0;
}
</style>