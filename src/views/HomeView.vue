<script setup lang="ts">
import TheHero from '../components/TheHero.vue';
import TheFooter from '../components/TheFooter.vue';
</script>

<template>
  <div class="home-view">
    <TheHero />
    <TheFooter />
  </div>
</template>

<style lang="scss" scoped>
.home-view {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  width: 100%;
}
</style>
