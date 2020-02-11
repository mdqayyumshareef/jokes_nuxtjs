<template>
  <header class="header">
    <div class="burger" role="button" @click="$store.dispatch('nav/toggleSidebar')">
      <img width="30px" height="30px" src="/menu-icon.svg" alt="hamburger-menu" />
    </div>
    <h1 class="title">Jokes</h1>
    <ul class="link-items">
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
  padding: 20px;
  border-bottom: 1px dotted #cccccc;
}

.header .title {
  font-size: 3rem;
  color: rgb(233, 164, 61);
}

.header li {
  display: inline-block;
  padding: 0.5rem 1rem;
  margin-right: 0.5rem;
  color: beige;
  background: #333;
}

.burger {
  display: none;
}

.link-items {
  display: flex;
}

@media screen and (max-width: 768px) {
  .burger {
    display: inline-block;
    margin-right: 20px;
  }
  .link-items {
    display: none;
  }
  .header {
    justify-content: flex-start;
  }
}
</style>