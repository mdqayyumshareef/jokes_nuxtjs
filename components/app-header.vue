<template>
  <header class="header">
    <h1 class="title">Jokes</h1>
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
  name: "app-header"
};
</script>

<style>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
  border-bottom: 1px dotted #cccccc;
}

.header .title {
  font-size: 3rem;
  color: rgb(233, 164, 61);
}

.header ul {
  display: flex;
}

.header li {
  display: inline-block;
  padding: 0.5rem 1rem;
  margin-right: 0.5rem;
  color: beige;
  background: #333;
}
</style>