<template>
  <div class="about">
    <div v-for="pro in products" :key="pro.id">
      <img :src="pro.img" alt="" class="h-64" />
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      products: [],
    };
  },
  mounted() {
    fetch("http://localhost:3000/products")
      .then((res) => res.json())
      .then((data) => (this.products = data))
      .catch((err) => console.log(err.message));
  },
};
</script>
