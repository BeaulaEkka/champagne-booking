<template>
  <div class="min-h-screen flex flex-col w-full">
    <header class="shadow-md bg-white">
      <nav class="container mx-auto p-4">
        <NuxtLink to="/products">Nuxt Dojo Merch</NuxtLink>
      </nav>
    </header>
    <div class="w-full mx-auto flex flex-grow"><slot /></div>
  </div>
</template>

<style scoped>
.router-link-exact-active {
  color: #12b488;
}
</style>
