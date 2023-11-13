<template>
  <div class="card" style="width: 400px">
    <h2>Adicionar Produto</h2>
    <form @submit.prevent="addProduct">
      <label for="name">Nome do Produto:</label>
      <input type="text" v-model="name" required>

      <label for="price">Preço:</label>
      <input type="number" v-model="price" required>

      <label for="category">Categoria:</label>
      <textarea v-model="category" required></textarea>

      <button type="submit">Adicionar</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      price: 0,
      category: '',
    };
  },
  methods: {
    addProduct() {
      this.$emit('add-product', {
        name: this.name,
        price: this.price,
        category: this.category,
      });

      this.name = '';
      this.price = 0;
      this.category = '';
    },



    
  },
};
</script>

<style scoped>
.card {
  border: 1px solid #ddd;
  padding: 15px;
  margin: 15px;
  border-radius: 8px;
}

form {
  display: flex;
  flex-direction: column;
}

label {
  margin-top: 10px;
}

input,
textarea {
  margin-bottom: 10px;
  padding: 8px;
  border: 1px solid #ddd;
  border-radius: 4px;
}

button {
  background-color: #4caf50;
  color: white;
  padding: 10px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}
</style>
