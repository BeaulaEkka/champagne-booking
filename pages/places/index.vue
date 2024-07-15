<template>
  <div>
    <div class="grid lg:grid-cols-4 md:grid-cols-2 gap-5 my-5">
      <div v-for="product in products" class="border rounded-md shadow-md p-5">
        <nuxt-link :to="`/products/${product.id}`">
          <div>
            <img
              :src="product.image"
              alt="{{
              product.title
              }}"
              width="150"
              height="auto"
            />
          </div>
          <h1 class="text-lg font-bold">{{ product.title }}</h1></nuxt-link
        >
      </div>
    </div>
  </div>
</template>

<script setup>
definePageMeta({ layout: "products" });

const { data: products } = await useFetch("https://fakestoreapi.com/products");
</script>

<style scoped></style>
