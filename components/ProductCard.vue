<template>
  <div class="product-card w-full">
    <div class="relative">
      <img
        :src="product.image"
        alt="Product Image"
        class="w-full h-[60vh] object-cover shadow-sm"
      />

      <p>{{ product.title }}</p>
      <div
        class="absolute bottom-6 bg-white w-[80%] h-28 flex border-b rounded-tr-md"
      >
        <div class="w-[70%] mx-auto flex gap-5 justify-between items-center">
          <p>
            <span
              class="bg-yellow-500 px-3 py-1 rounded-t-lg rounded-br-lg rounded-bl-sm font-bold text-white"
              >{{ product.review }}</span
            >
            <span
              class="text-yellow-500 ml-4 text-xl"
              v-html="starRating"
            ></span>
          </p>
          <p class="skewed-text">{{ product.title }}</p>
          <p>{{ product.address }}</p>
        </div>
      </div>
    </div>
    <div>
      <ProductMainSection :product="product" />
    </div>
  </div>
</template>

<script setup>
const { product } = defineProps(["product"]);
import { computed } from "vue";

const starRating = computed(() => {
  const fullStars = Math.floor(product.review);
  const emptyStars = 5 - fullStars;
  return "★".repeat(fullStars) + "☆".repeat(emptyStars);
});
</script>

<style scoped>
.product-card {
  width: 100%;
  height: 50vh;
}
.skewed-text {
  position: relative;
  padding: 0 3rem;
  border-left: 2px solid #d4c111;
  border-right: 2px solid #d4c111;
  transform: skewX(-12deg);
  background-color: #fff;
}

.skewed-text::before,
.skewed-text::after {
  content: "";
  position: absolute;
  top: 0;
  width: 50%;
  height: 100%;
  background-color: inherit;
  z-index: -1;
}

.skewed-text::before {
  left: -1px;
  transform: skewX(12deg);
}

.skewed-text::after {
  right: -1px;
  transform: skewX(-12deg);
}
</style>
