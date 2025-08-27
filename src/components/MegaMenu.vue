<script setup>
const sections = [
  { icon: 'fa-solid fa-chart-line', title: '投资理财', items: ['理财', '基金'] },
  { icon: 'fa-solid fa-credit-card', title: '信用卡', items: ['我要办卡', '刷卡优惠'] },
  { icon: 'fa-solid fa-globe', title: '个人电子银行', items: ['网上银行', '掌上银行'] },
  { icon: 'fa-solid fa-shield-halved', title: '网络支付', items: ['支付产品', '结算产品'] },
  { icon: 'fa-solid fa-piggy-bank', title: '存款', items: [] },
  { icon: 'fa-solid fa-id-card', title: '借记卡', items: [] },
  { icon: 'fa-solid fa-yen-sign', title: '贷款', items: [] },
  { icon: 'fa-solid fa-file-invoice-dollar', title: '支付结算', items: [] },
  { icon: 'fa-solid fa-graduation-cap', title: '留学金融', items: [] },
  { icon: 'fa-solid fa-scroll', title: '章程协议', items: [] },
  { icon: 'fa-solid fa-gem', title: '贵宾服务', items: [] },
  { icon: 'fa-solid fa-arrows-rotate', title: '外汇', items: [] }
]
</script>

<template>
  <div class="mega">
    <div class="grid">
      <div v-for="(s, i) in sections" :key="i" class="cell">
        <div class="head">
          <i :class="s.icon"></i>
          <span class="title">{{ s.title }}</span>
        </div>
        <ul v-if="s.items.length" class="sub">
          <li v-for="(t, j) in s.items" :key="j"><span class="sub-text">{{ t }}</span></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped>
.mega {
  width: 100%;
  background: #fff;
  border: 1px solid #e6e6e6; /* 左右边框 1px */
  box-shadow: 0 8px 24px rgba(0,0,0,.06);
  height: 268px; /* 统一高度，贴近截图 */
}
/* 让父级控制整体宽度，这里不再设置 max-width */
.grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px 24px; padding: 16px 18px 18px; height: 100%; box-sizing: border-box; }
.cell { padding: 2px 8px 10px; border-right: 1px solid #f0f0f0; }
.cell:nth-child(4n) { border-right: none; }
.head { display: flex; align-items: center; gap: 12px; margin: 6px 0 8px; }
/* 默认图标：青绿色 */
.cell .head i { font-size: 22px; color: #21b69b; width: 24px; text-align: center; }
/* 第一行（前4个）：黄色图标 */
.cell:nth-child(-n+4) .head i { color: #f5a623 !important; }
.title { font-size: 16px; color: #333; font-weight: 700; cursor: pointer; display: inline-block; border-bottom: 1px solid transparent; padding-bottom: 2px; }
/* 标题悬停：1px 下划线 */
.head:hover .title, .title:hover { border-bottom-color: #21b69b; }
/* 子项与标题左边对齐：通过 padding-left 匹配图标+间距的总宽 */
.sub { list-style: none; padding: 0 0 0 36px; margin: 0; }
.sub li { display: block; line-height: 26px; }
.sub-text { color: #666; font-size: 13px; cursor: pointer; display: inline-block; border-bottom: 1px solid transparent; padding-bottom: 1px; }
/* 子项悬停：1px 下划线 + 变绿 */
.sub li:hover .sub-text { color: #21b69b; border-bottom-color: #21b69b; }
</style> 