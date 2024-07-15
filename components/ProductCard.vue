<template>
  <div>
    <img :src="product.image" alt="Product Image" width="150" height="auto" />
    <p>{{ product.title }}</p>
    <p>{{ product.price }}</p>
    <p>{{ product.description }}</p>
    <p>Product Details for {{ id }}</p>
  </div>
</template>

<script setup>
const { product } = defineProps(["product"]);
</script>

<style scoped></style>
