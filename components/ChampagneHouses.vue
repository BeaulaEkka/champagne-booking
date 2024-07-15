<template>
  <section class="champagne-houses">
    <h2>Champagne Houses in Reims</h2>
    <p>
      Discover the world-renowned Champagne houses located in the heart of the
      Champagne region.
    </p>
    <ul>
      <li>
        <a href="#">Veuve Clicquot</a>
      </li>
      <li>
        <a href="#">Ruinart</a>
      </li>
      <li>
        <a href="#">Taittinger</a>
      </li>
      <li>
        <a href="#">Pommery</a>
      </li>
      <li>
        <a href="#">Lanson</a>
      </li>
    </ul>
    <nuxt-link to="/champagne-houses">
      <button>Explore All Houses</button>
    </nuxt-link>
  </section>
</template>

<script>
export default {
  // No data or methods needed for this component
};
</script>

<style scoped>
.champagne-houses {
  /* Add styles for the section here */
  background-color: aqua;
}
</style>
