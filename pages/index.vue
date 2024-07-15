<template>
  <div class="min-h-screen flex flex-col">
    <div class="relative w-[100vw] h-[70vh]">
      <img
        src="/images/vineyard2.jpg"
        class="w-full h-full object-cover shadow-md"
      />
      <div
        class="absolute top-[38%] left-0 right-0 text-white p-4 w-[70%] mx-auto text-left"
      >
        <p class="py-2 font-semibold leading-3">
          CHAMPAGNE TOURS & PROEVERIJEN
        </p>
        <h2 class="text-6xl font-semibold">Book the perfect Champagne Tour</h2>
      </div>
      <div class="w-full absolute bottom-[-40px]"><SearchBar /></div>
    </div>

    <div></div>
    <div class="mt-32"><Reim /></div>
    <div class="mb-[30%]"><NewExperiences /></div>
  </div>
</template>

<script setup></script>

<style scoped></style>
