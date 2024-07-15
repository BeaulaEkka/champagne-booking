<template>
  <div class="min-h-screen flex flex-col w-full">
    <header
      class="w-full shadow-md h-18 justify-center items-center py-4 bg-white border-b-4 border-yellow-500"
    >
      <nav class="w-[70%] mx-auto flex justify-between items-center">
        <div>
          <NuxtLink to="/"
            ><img src="../public/images/logo.webp" alt="logo" width="200"
          /></NuxtLink>
        </div>
        <ul class="flex gap-5 text-gray-800 text-lg">
          <li><NuxtLink to="/">Home</NuxtLink></li>
          <li
            class="relative"
            @mouseover="showDropdown"
            @mouseleave="hideDropdown"
          >
            <NuxtLink to="/about"
              >Champagne Houses
              <span class="text-xs ml-1 text-gray-500"
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
          <li>
            <NuxtLink to="/top10"
              >Top 10<span class="text-xs ml-1 text-gray-500"
                ><font-awesome icon="fa-chevron-down" /></span
            ></NuxtLink>
          </li>
          <li>
            <NuxtLink to="/champagne-region"
              >Champagne Region<span class="text-xs ml-1 text-gray-500"
                ><font-awesome icon="fa-chevron-down" /></span
            ></NuxtLink>
          </li>
          <li><NuxtLink to="/contact">Contact</NuxtLink></li>
          <li><NuxtLink to="/products">Account</NuxtLink></li>
        </ul>
      </nav>
    </header>
    <div class="flex flex-grow min-h-[130vh]"><slot /></div>
  </div>
  <FooterComponent />
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
  width: 270px;
  border-radius: 0.5rem;
}
</style>
