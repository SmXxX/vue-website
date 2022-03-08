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
            <h2>
              Title: <span>{{ product.title }}</span>
            </h2>
            <h3>
              Category: <span>{{ product.category }}</span>
            </h3>
          </div>

          <router-link class="link" :to="'/single/' + product.title"
            ><img :src="product.image" alt=""
          /></router-link>
          <h4>Price: {{ product.price }}</h4>
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
      api: "https://fakestoreapi.com/products?limit=10",
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

<style scoped>
img {
  width: 300px;
  height: 300px;
  object-fit: contain;
}
img:hover {
  width: 305px;
  height: 305px;
  cursor: pointer;
}
</style>
