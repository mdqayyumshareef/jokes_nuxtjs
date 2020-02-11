<template>
  <div class="sidenav-container">
    <div v-if="toggleSidebar" class="backdrop" @click="$store.dispatch('nav/toggleSidebar')"></div>
    <transition name="slide-side">
      <div v-if="toggleSidebar" class="sidenav">
        Hello from side nav
        <ul class="nav-list">
          <li class="nav-item" @click="$store.dispatch('nav/toggleSidebar')">
            <nuxt-link to="/">Home</nuxt-link>
          </li>
          <li class="nav-item" @click="$store.dispatch('nav/toggleSidebar')">
            <nuxt-link to="/jokes">Jokes</nuxt-link>
          </li>
          <li class="nav-item" @click="$store.dispatch('nav/toggleSidebar')">
            <nuxt-link to="/about">About</nuxt-link>
          </li>
        </ul>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  computed: {
    toggleSidebar() {
      return this.$store.getters["nav/toggleSidebar"];
    }
  }
};
</script>

<style scoped>
.nav-list {
  list-style: none;
  display: block;
  padding: 0;
  margin: 0;
}
.nav-item {
  margin: 0 10px;
  margin-top: 16px;
  margin-bottom: 16px;
}
.nav-item a {
  text-decoration: none;
  color: blue;
}
.nav-item a:hover,
.nav-item a:active {
  color: #b4b4b4;
}
/* @media (max-width: 767px) {
  .nav-list {
    display: block;
  }
  .nav-item {
    margin-top: 16px;
    margin-bottom: 16px;
  }
}
@media (min-width: 768px) {
  .nav-list {
    display: flex;
  }
} */

.sidenav-container {
  height: 100%;
  width: 100%;
}
.sidenav {
  height: 100%;
  width: 300px;
  background-color: #d6d6d6;
  z-index: 10000;
  position: fixed;
  top: 0;
  left: 0;
  box-sizing: border-box;
  padding: 30px;
}
.backdrop {
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  z-index: 1000;
  position: fixed;
  top: 0;
  left: 0;
}
.slide-side-enter-active,
.slide-side-leave-active {
  transition: all 0.3s ease-out;
}
.slide-side-enter,
.slide-side-leave-to {
  transform: translateX(-100%);
}
</style>