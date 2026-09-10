<template>
  <div id="app">
    <AppHeader />
    <main class="main-content">
      <router-view />
    </main>
    <AppFooter />
  </div>
</template>

<script setup>
import AppHeader from '@/components/layout/AppHeader.vue'
import AppFooter from '@/components/layout/AppFooter.vue'
</script>

<style>
#app {
  display: grid;
  grid-template-rows: auto 1fr auto;
  min-height: 100vh;
  background-color: #FAFAFA;
}

.main-content {
  display: flex;
  flex-direction: column;
  min-height: 0;
}

/* Solo las vistas que necesitan ocupar todo el hueco (como ContactPage)
   usan flex: 1 dentro del main. Las demás crecen con su contenido. */
.main-content > * {
  display: flex;
  flex-direction: column;
}
</style>