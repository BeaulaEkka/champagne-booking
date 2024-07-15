<template>
  <div class="w-full mx-auto flex flex-col">
    <header
      class="w-full shadow-md h-16 justify-center items-center py-4 bg-white/5 fixed top-0 z-10"
    >
      <nav class="w-[70%] mx-auto flex justify-between">
        <div>
          <NuxtLink to="/"></NuxtLink>
        </div>
        <ul class="flex gap-5 text-white text-lg">
          <li>Home</li>
          <li
            class="relative"
            @mouseover="showDropdown"
            @mouseleave="hideDropdown"
          >
            <NuxtLink to="/about">Champagne Houses</NuxtLink>
            <ul
              v-if="isDropdownVisible"
              class="absolute left-0 bg-white shadow-md p-4 dropdown-menu text-gray-800"
            >
              <li class="p-2 text-red-600 font-semibold">
                Popular destinations
              </li>
              <li
                class="p-2 hover:bg-gray-100 hover:underline-offset-2 text-nowrap border-b"
              >
                <NuxtLink to="/about/reims">Champagne Houses in Reims</NuxtLink>
              </li>
              <li class="p-2 hover:bg-gray-100 border-b">
                <NuxtLink to="/about/epernay"
                  >Champagne Houses in Epernay</NuxtLink
                >
              </li>
              <li class="p-2 hover:bg-gray-100 border-b">
                <NuxtLink to="/about/ay"
                  >Champagne Houses in Ay
                  <i class="fa fa-arrow-right" aria-hidden="true"></i
                ></NuxtLink>
              </li>
              <li class="p-2 text-red-600 font-semibold">Popular in Reims</li>
              <li class="p-2 hover:bg-gray-100 border-b">
                <NuxtLink to="/about/pommery">Champagne Pommery</NuxtLink>
              </li>
              <li class="p-2 text-red-600 font-semibold">Popular in Epernay</li>
              <li class="p-2 hover:bg-gray-100 border-b">
                <NuxtLink to="/about/mercier">Champagne Mercier</NuxtLink>
              </li>
            </ul>
          </li>
          <li><NuxtLink to="/top10">Top 10</NuxtLink></li>
          <li><NuxtLink to="/champagne-region">Champagne Region</NuxtLink></li>
          <li><NuxtLink to="/contact">Contact</NuxtLink></li>
          <li><NuxtLink to="/products">Account</NuxtLink></li>
        </ul>
      </nav>
    </header>
    <div class="flex flex-grow">
      <slot />
    </div>
    <footer>
      <FooterComponent />
    </footer>
  </div>
</template>

<script setup>
import { ref } from "vue";

const isDropdownVisible = ref(false);

function showDropdown() {
  isDropdownVisible.value = true;
}

function hideDropdown() {
  isDropdownVisible.value = false;
}
</script>

<style scoped>
.router-link-exact-active {
  color: #12b488;
}

/* Additional styling for dropdown */
.relative {
  position: relative;
}

.absolute {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 10;
}

.bg-white {
  background-color: white;
}

.shadow-md {
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.p-2 {
  padding: 0.5rem;
}

.hover\:bg-gray-100:hover {
  background-color: #f7fafc;
}

/* Custom class for dropdown menu */
.dropdown-menu {
  width: 250px;
  border-radius: 0.5rem;
}
</style>
