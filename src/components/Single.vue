<template>
  <div class="main">
    <div class="main-heading">Single Product</div>
    <div class="content">
      <h1>Title: {{ product.title }}</h1>
      <img :src="product.image" alt="" />
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
    };
  },
  mounted() {
    fetch("https://fakestoreapi.com/products/" + this.$route.params.id)
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
</style>
