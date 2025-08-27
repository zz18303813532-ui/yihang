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
    </div>
  </section>
</template>

<style scoped>
.focus-hero { 
  background: url('/hero.jpg') no-repeat center center;
  background-size: contain;
  background-color: #f5f5f5;
  position: relative;
  min-height: 600px;
  padding: 40px 0;
}
.container {
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
  height: 100%;
  padding: 0 20px;
}
.panel { 
  background: rgba(255,255,255,.95); 
  padding: 20px 16px; 
  border-radius: 6px;
  position: absolute;
  left: 20px;
  top: 40px;
  width: 320px;
  z-index: 10;
  box-shadow: 0 4px 12px rgba(0,0,0,0.15);
  backdrop-filter: blur(5px);
}
.row {
  display: flex;
  align-items: center;
  height: 64px;
  margin-bottom: 12px;
  border-radius: 6px;
  padding: 0 18px;
  font-size: 18px;
  text-decoration: none;
  transition: all 0.3s ease;
}
.row:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0,0,0,0.15);
}
.row i { font-size: 24px; margin-right: 12px; }
.row:last-child { margin-bottom: 0; }
</style> 