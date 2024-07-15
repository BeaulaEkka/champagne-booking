<template>
  <div class="w-full">
    <ProductCard v-if="product" :product="product" />
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useRoute } from "vue-router";
import ProductCard from "@/components/ProductCard.vue"; // Adjust the path as necessary
import data from "~/assets/data.json";

const route = useRoute();
const id = route.params.id;
const product = ref(null);

const fetchProduct = () => {
  const productId = Number(id);
  product.value = data.find((item) => item.id === productId);
};

fetchProduct();

definePageMeta({ layout: "product" });
</script>

<style scoped></style>
