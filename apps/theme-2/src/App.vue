<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div id="app">
    <header class="theme-2-header">
      <div class="wrapper">
        <h1>Theme 2 Application</h1>
        <nav>
          <RouterLink to="/">Home</RouterLink>
          <RouterLink to="/about">About</RouterLink>
        </nav>
      </div>
    </header>

    <main>
      <RouterView />
    </main>
  </div>
</template>

<style scoped lang="scss">
.theme-2-header {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  padding: 2rem;
  color: white;

  h1 {
    margin: 0 0 1rem 0;
    font-size: 2rem;
  }

  nav {
    display: flex;
    gap: 1.5rem;

    a {
      color: white;
      text-decoration: none;
      padding: 0.5rem 1rem;
      border-radius: 0.5rem;
      transition: background 0.3s;

      &:hover {
        background: rgba(255, 255, 255, 0.2);
      }

      &.router-link-active {
        background: rgba(255, 255, 255, 0.3);
      }
    }
  }
}

main {
  padding: 2rem;
}
</style>
