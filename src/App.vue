<script setup>
import { RouterLink ,RouterView } from 'vue-router'
</script>

<template>
  <header class="container">
    <RouterLink to="/">Home</RouterLink>
    <RouterLink to="/about">About</RouterLink>
    <Transition name="route">
      <RouterView />
    </Transition>
  </header>
</template>

<style scoped>
/* @media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
} */

.container{
  align-items: center;
  margin-left: 10px;
}
.container a{
  margin-right: 10px;
  font-size: 20px;
  font-weight: bold;
  opacity: 0.5;
}

.container a:hover{
opacity: 1;
}

.route-enter-from {
  opacity: 0;
  transform: translateX(100px);
}
.route-enter-to {
  opacity: 1;
  transform: translateX(0);
}
.route-enter-active {
 transition: all 0.5s ease;
}
</style>
