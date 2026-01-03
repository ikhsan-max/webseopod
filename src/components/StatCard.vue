<script setup>
const props = defineProps({
  title: String,
  value: String,
  change: String,
  tone: {
    type: String,
    default: 'neutral',
  },
  detail: String,
});

const toneClass = {
  positive: 'positive',
  negative: 'negative',
  neutral: 'neutral',
};
</script>

<template>
  <article class="stat-card glass-card">
    <header class="stat-head">
      <p class="label">{{ title }}</p>
      <span class="pill" :class="toneClass[props.tone]">{{ change }}</span>
    </header>
    <div class="value">{{ value }}</div>
    <p class="muted">{{ detail }}</p>
  </article>
</template>

<style scoped>
.stat-card {
  display: flex;
  flex-direction: column;
  gap: 0.35rem;
  border: 1px solid rgba(15, 23, 42, 0.05);
  min-height: 160px;
}

.stat-head {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 0.5rem;
}

.value {
  font-size: 2rem;
  font-weight: 700;
  margin: 0;
  color: #0f172a;
}

.pill {
  display: inline-flex;
  align-items: center;
  gap: 0.35rem;
  padding: 0.35rem 0.6rem;
  border-radius: 999px;
  font-weight: 700;
  font-size: 0.85rem;
}

.pill.positive {
  background: rgba(16, 185, 129, 0.12);
  color: #047857;
}

.pill.negative {
  background: rgba(239, 68, 68, 0.12);
  color: #b91c1c;
}

.pill.neutral {
  background: rgba(15, 23, 42, 0.05);
  color: #0f172a;
}
</style>
