<template>
  <div class="main">
    <div class="main-heading">Single Product</div>
    <div class="content">
      <h1>Title: {{ product.title }}</h1>
      <img :src="product.image" alt="" />
      <h3>Price: ${{ product.price }}</h3>
      <h3>Category: {{ product.category }}</h3>
      <div class="desc">Description: {{ product.description }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Single",
  props: ["id"],
  data: function () {
    return {
      product: "",
      api: "https://fakestoreapi.com/products/",
    };
  },
  mounted() {
    fetch(this.api + this.$route.params.id)
      .then((response) => response.json())
      .then((data) => (this.product = data));
  },
};
</script>

<style scoped>
.main-heading {
  color: #fff;
  font-size: 45px;
  margin-top: 20px;
}
img {
  width: 300px;
  height: 350px;
}
h1,
h3 {
  font-size: 25px;
  color: #fff;
}
.product {
  display: flex;
  justify-content: center;
  font-size: 18px;
  color: #fff;
}
.desc,
.rate {
  font-size: 18px;
  color: gray;
  width: 1200px;
  display: flex;
  margin: 0 auto;
}
</style>
