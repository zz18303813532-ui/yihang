<script setup>
import HeaderBar from '../components/HeaderBar.vue'
import FocusHero from '../components/FocusHero.vue'
</script>

<template>
    <div>
        <HeaderBar />
        <FocusHero bannerSrc="/hero.jpg" />
    </div>
</template>

<style scoped>
section {
  padding: 16px;
}
</style>
