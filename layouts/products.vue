<template>
  <div class="min-h-screen flex flex-col">
    <header class="shadow-md bg-white">
      <nav class="container mx-auto p-4">
        <NuxtLink to="/products">Nuxt Dojo Merch</NuxtLink>
      </nav>
    </header>
    <div class="container mx-auto p-4 flex flex-grow"><slot /></div>
    <footer
      class="container mx-auto p-4 flex justify-between border-t-2 w-full"
    >
      <ul class="flex gap-4">
        <li><NuxtLink to="/">Home</NuxtLink></li>
        <li><NuxtLink to="/about">About</NuxtLink></li>
        <li><NuxtLink to="/products">Products</NuxtLink></li>
      </ul>
    </footer>
  </div>
</template>

<style scoped>
.router-link-exact-active {
  color: #12b488;
}
footer {
  height: 25px;
}
</style>
