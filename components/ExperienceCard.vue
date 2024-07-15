<template>
  <div class="relative">
    <div class="card-container flex overflow-hidden">
      <div
        class="flex transition-transform duration-500 w-full"
        :style="{
          transform: `translateX(-${currentIndex * (100 / cardsPerView)}%)`,
        }"
      >
        <div
          v-for="(item, index) in cards"
          :key="item.id"
          class="card flex flex-col shadow-md rounded-md hover:scale-105 transition-transform duration-300"
        >
          <nuxt-link
            :to="`/places/${item.id}`"
            class="cursor-pointer block h-full"
          >
            <div class="rounded-t-md overflow-hidden">
              <img
                :src="item.image"
                alt="Card image"
                class="w-full h-52 object-cover"
              />
            </div>
            <div class="p-4 flex flex-col flex-grow">
              <div class="flex flex-col flex-grow">
                <h2 class="font-semibold text-lg pb-2">{{ item.title }}</h2>
                <p class="text-sm flex-grow pb-4">{{ item.description }}</p>
              </div>
              <div
                class="flex justify-between border-t pt-2 text-sm text-gray-500"
              >
                <p>From €{{ item.price }}</p>
                <p class="text-sm">{{ item.activities }} activities</p>
              </div>
            </div>
          </nuxt-link>
        </div>
      </div>
    </div>

    <!-- Navigation Arrows -->
    <button
      v-if="currentIndex > 0"
      @click="prev"
      class="absolute left-0 top-1/2 transform -translate-y-1/2 bg-gray-700 text-white px-2 py-1 rounded text-2xl"
    >
      &lt;
    </button>
    <button
      v-if="currentIndex < maxIndex"
      @click="next"
      class="absolute right-0 top-1/2 transform -translate-y-1/2 bg-gray-700 text-white px-2 py-1 rounded text-2xl"
    >
      &gt;
    </button>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";
import data from "../assets/data.json";

const cards = ref(data);
const currentIndex = ref(0);
const cardsPerView = 4;

const maxIndex = computed(() => Math.max(0, cards.value.length - cardsPerView));

const prev = () => {
  if (currentIndex.value > 0) {
    currentIndex.value -= 1;
  }
};

const next = () => {
  if (currentIndex.value < maxIndex.value) {
    currentIndex.value += 1;
  }
};
</script>

<style scoped>
.card-container {
  width: 100%;
  display: flex;
  overflow: hidden;
}
.card-container .flex {
  display: flex;
  width: 100%;
}
.card {
  flex: 0 0 23.5%;
  border: 1px solid #ccc;
  margin: 10px;
  width: calc(100% / 4 - 20px);
}
</style>
