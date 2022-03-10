<template>
  <div id="nav">
    <router-link class="link" to="/">Home</router-link>
    <router-link class="link" to="/about">About</router-link>
    <router-link class="link" to="/contact">Contact</router-link>
  </div>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style>
#nav {
  display: flex;
  justify-content: flex-end;
}
.link {
  padding: 0 45px 0 0;
  font-size: 25px;
  text-decoration: none;
  color: white;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
    "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
}
.link:hover {
  color: blue;
}
</style>
