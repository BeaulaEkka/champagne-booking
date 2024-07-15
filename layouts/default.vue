<template>
  <div class="w-full mx-auto bg-transparent">
    <header class="shadow-md h-16 justify-center items-center py-4 fixed">
      <nav class="w-[70%] mx-auto flex justify-between fixed">
        <div>
          <NuxtLink to="/">Nuxt Dojo</NuxtLink>
        </div>
        <ul class="flex gap-5">
          <li><NuxtLink to="/">Home</NuxtLink></li>
          <!-- <li><NuxtLink to="/about">About</NuxtLink></li> -->
          <li><NuxtLink to="/products">Products</NuxtLink></li>
        </ul>
      </nav>
    </header>
    <div class="mx-auto"><slot /></div>
    <footer>
      <div class="lg:grid-4">
        <div>
          POPULAR PAGES TOP 15 Champagne Tours Champagne Houses in Reims
          Champagne Houses in Epernay Champagne Houses in Aÿ Champagne Region
          France
        </div>
        <div>
          TOP CHAMPAGNE HOUSES Champagne Pommery Champagne Bollinger Champagne
          Mercier Champagne Taittinger Champagne Perrier-Jouët
        </div>
        <div>
          CHAMPAGNE BOOKING Home Blog Champagne facts Registration new
          partnership Contact
        </div>
        <div>OFFICIAL PARTNER</div>
      </div>
    </footer>
  </div>
</template>

<style scoped>
.router-link-exact-active {
  color: #12b488;
}
</style>
