<script setup>
import AccueilApp from './components/AccueilApp.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <AccueilApp msg="Réaliser une to do list avec VueJs!" />
    </div>
  </header>

  <main>

  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}
.wrapper {
  margin: 0 auto;
}
.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }
}
</style>
