<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <nav>
    <RouterLink to="/">Home</RouterLink>
    <RouterLink to="/search">Search User</RouterLink>
  </nav>
  <RouterView />
</template>

<style>
#app {
  font-family: 'Ubuntu', sans-serif;
  min-height: 100vh;
  max-width: 40rem;
  margin: 0 auto;
  text-align: center;
}
h1 {
  color: #42B883;
  margin: 1rem auto .25rem;
}
footer {
  height: 3rem;
  margin-top: 2rem;
  padding: 1rem 0;
}
a {
  color: #42B883;
  font-weight: 600;
  text-decoration: none;
}
a + a {
  margin-left: 1rem;
}
a:hover {
  cursor: pointer;
  filter: brightness(0.9);
}
nav {
  border-bottom: 1px solid #FFFFFF;
  padding: 1rem 0;
  margin-bottom: 1rem;
}
</style>
