<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import MagicWand from './components/icons/MagicWand.vue'
</script>

<template>
  <header>

    <div class="wrapper">
      <MagicWand class="logo" />
      <nav>

        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/blog">Blog</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped lang="scss">
@import '@/assets/styles/variables';

header {
  line-height: 1.5;
  max-height: 100vh;
  font-family: $font-family-base;
  font-weight: $font-weight-semibold ;

  @media (min-width: 1024px) {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);

    .wrapper {
      display: flex;
      place-items: flex-start;
      flex-wrap: nowrap;
      width: 100%;
      align-items: center;
    }
  }
}

.logo {
  display: block;
  margin: 0 auto 2rem;
  flex-basis: 5vw;

  @media (min-width: 1024px) {
    margin: 0 2rem 0 0;
  }
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;

  a {
    display: inline-block;
    padding: 0 1rem;
    border-left: 1px solid var(--color-border);
    font-weight: $font-weight-medium;

    &.router-link-exact-active {
      color: var(--color-text);

      &:hover {
        background-color: transparent;
      }
    }

    &:first-of-type {
      border: 0;
    }
  }

  @media (min-width: 1024px) {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;
    padding: 1rem 0;
  }
}
</style>
