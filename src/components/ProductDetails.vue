<template>
  <div>
    <img :src="product.img" alt="" />
    <h3>Название продукта: {{ product.name }}</h3>
    <p>Форматированная цена: {{ result.formattedPrice }}</p>
    <p v-if="product.available">Available</p>
    <p v-else="product.available">Out of stock</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      product: {
        img: require("@/assets/img/1.jpg"),
        name: "Миди клавиатура",
        price: "1000",
        available: false,
      },
    };
  },
  computed: {
    result() {
      const formattedPrice = "$" + this.product.price;
      return { formattedPrice };
    },
  },
};
</script>

<style scoped>
img {
  width: 200px;
}
</style>
