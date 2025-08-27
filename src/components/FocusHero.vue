<script setup>
import { computed } from 'vue'

const props = defineProps({
  bannerSrc: { type: String, default: '/hero.jpg' },
  items: {
    type: Array,
    default: () => ([
      { icon: 'fa-solid fa-user', label: '个人网银登录', bg: '#22cdb5', color: '#fff' },
      { icon: 'fa-solid fa-lock', label: '企业网银登录', bg: '#ffffff', color: '#333' },
      { icon: 'fa-solid fa-circle-nodes', label: '在线办理及费率', bg: '#ffa51e', color: '#fff' }
    ])
  }
})

const safeBanner = computed(() => props.bannerSrc || '/vite.svg')
</script>

<template>
  <section class="focus-hero">
    <div class="container">
      <div class="panel">
        <a v-for="(it, idx) in items" :key="idx" class="row" :style="{ background: it.bg, color: it.color }" href="javascript:void(0)">
          <i :class="it.icon"></i>
          <span class="label">{{ it.label }}</span>
        </a>
      </div>
      <div class="banner">
        <img :src="safeBanner" alt="banner" />
      </div>
    </div>
  </section>
</template>

<style scoped>
.focus-hero { background: #f7f7f7; }
.container {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 320px 1fr;
  gap: 20px;
  align-items: stretch;
}
.panel { background: rgba(255,255,255,.85); padding: 20px 16px; border-radius: 6px; }
.row {
  display: flex;
  align-items: center;
  height: 64px;
  margin-bottom: 12px;
  border-radius: 6px;
  padding: 0 18px;
  font-size: 18px;
  text-decoration: none;
}
.row i { font-size: 24px; margin-right: 12px; }
.row:last-child { margin-bottom: 0; }
.banner { border-radius: 6px; overflow: hidden; background: #ddd; }
.banner img { width: 100%; height: 100%; object-fit: cover; display: block; }
</style> 