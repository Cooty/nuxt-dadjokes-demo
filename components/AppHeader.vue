<template>
  <header class="header">
    <h1 class="title">Dad Jokes</h1>

    <ul>
      <li>
        <nuxt-link to="/">Home</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/jokes">Jokes</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/about">About</nuxt-link>
      </li>
    </ul>
  </header>
</template>

<script>
export default {
  name: "AppHeader"
}
</script>

<style scoped>
  .header {
    background: rgba(0, 0, 0, .1);
    border-bottom: rgba(0, 0, 0, .2);
    padding: 1rem;
    margin-bottom: 5rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .header > ul {
    display: flex;
    list-style: none;
  }

  .header > ul > li {
    padding: 0 .5rem;
  }
</style>
