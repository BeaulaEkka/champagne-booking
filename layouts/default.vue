<template>
  <div class="w-full mx-auto flex flex-col">
    <header
      :class="{
        '-translate-y-full': !isHeaderVisible,
        'translate-y-0': isHeaderVisible,
      }"
      class="w-full shadow-md h-18 justify-center items-center py-4 bg-white/5 fixed top-0 z-10 border-b border-gray-50/25 transition-transform duration-300"
    >
      <nav class="w-[70%] mx-auto flex justify-between">
        <div>
          <NuxtLink to="/"
            ><img src="../public/images/logo-white.webp" alt="logo" width="200"
          /></NuxtLink>
        </div>
        <ul class="flex items-center gap-5 text-white text-lg">
          <NuxtLink to="/"> <li class="font-semibold">Home</li></NuxtLink>
          <li
            class="relative font-semibold"
            @mouseover="showDropdown"
            @mouseleave="hideDropdown"
          >
            <NuxtLink to="/about"
              >Champagne Houses<span class="text-xs ml-1 text-white"
                ><font-awesome icon="fa-chevron-down" /></span
            ></NuxtLink>
            <ul
              v-if="isDropdownVisible"
              class="absolute left-0 bg-white shadow-md p-4 dropdown-menu text-gray-800"
            >
              <li class="p-2 text-red-600 font-semibold text-md">
                Popular destinations
              </li>
              <li
                class="p-2 hover:bg-gray-100 hover:underline-offset-2 text-nowrap border-b text-sm"
              >
                <NuxtLink to="/about/reims">Champagne Houses in Reims</NuxtLink>
              </li>
              <li class="p-2 hover:bg-gray-100 border-b text-sm">
                <NuxtLink to="/about/epernay"
                  >Champagne Houses in Epernay</NuxtLink
                >
              </li>
              <li class="p-2 hover:bg-gray-100 border-b text-sm">
                <NuxtLink to="/about/ay"
                  >Champagne Houses in Ay
                  <i class="fa fa-arrow-right" aria-hidden="true"></i
                ></NuxtLink>
              </li>
              <li class="p-2 text-red-600 font-semibold text-md">
                Popular in Reims
              </li>
              <li class="p-2 hover:bg-gray-100 border-b text-sm">
                <NuxtLink to="/about/pommery">Champagne Pommery</NuxtLink>
              </li>
              <li class="p-2 text-red-600 font-semibold text-md">
                Popular in Epernay
              </li>
              <li class="p-2 hover:bg-gray-100 border-b text-sm">
                <NuxtLink to="/about/mercier">Champagne Mercier</NuxtLink>
              </li>
            </ul>
          </li>
          <li class="font-semibold">
            <NuxtLink to="/top10"
              >Top 10
              <span class="text-xs ml-1 text-white"
                ><font-awesome icon="fa-chevron-down" /></span
            ></NuxtLink>
          </li>
          <li class="font-semibold">
            <NuxtLink to="/champagne-region"
              >Champagne Region
              <span class="text-xs ml-1 text-white"
                ><font-awesome icon="fa-chevron-down" /></span
            ></NuxtLink>
          </li>
          <li class="font-semibold">
            <NuxtLink to="/contact">Contact</NuxtLink>
          </li>
          <li class="font-semibold">
            <NuxtLink to="/products">Account</NuxtLink>
          </li>
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
import { ref, onMounted, onUnmounted } from "vue";

const isDropdownVisible = ref(false);
const isHeaderVisible = ref(true);
let lastScrollY = 0;

function showDropdown() {
  isDropdownVisible.value = true;
}

function hideDropdown() {
  isDropdownVisible.value = false;
}

function handleScroll() {
  const currentScrollY = window.scrollY;
  isHeaderVisible.value = currentScrollY < lastScrollY || currentScrollY < 10;
  lastScrollY = currentScrollY;
}

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<style scoped>
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

/* Transition class for header visibility */
.transition-transform {
  transition: transform 0;
}
</style>
