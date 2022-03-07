<template>
  <div>
    <h1 class="api-heading">API Store</h1>
    <div
      style="display: inline-block"
      v-for="product in data"
      :key="product.id"
    >
      <div class="container">
        <div class="box">
          <div class="content">
            <h2>Title: {{ product.title }}</h2>
            <h3>Category: {{ product.category }}</h3>
          </div>
          <img :src="product.image" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import "./App.css";
export default {
  name: "Home",
  data() {
    return {
      data: "",
      api: "https://fakestoreapi.com/products?limit=6",
    };
  },
  mounted() {
    fetch(this.api)
      .then((response) => {
        return response.json();
      })
      .then((result) => {
        // console.log(result);
        this.data = result;
      })
      .catch((err) => {
        console.log(err.message);
      });
  },
};
</script>
