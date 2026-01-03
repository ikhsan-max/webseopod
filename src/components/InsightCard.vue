<script setup>
const props = defineProps({
  title: String,
  description: String,
  tags: {
    type: Array,
    default: () => [],
  },
  impact: String,
});
</script>

<template>
  <article class="insight-card">
    <div class="gradient" />
    <div class="content">
      <div class="header">
        <p class="label">{{ impact }}</p>
        <div class="spark" aria-hidden="true"></div>
      </div>
      <h4>{{ title }}</h4>
      <p class="muted">{{ description }}</p>
      <div class="tags">
        <span v-for="tag in tags" :key="tag" class="pill">{{ tag }}</span>
      </div>
    </div>
  </article>
</template>

<style scoped>
.insight-card {
  position: relative;
  overflow: hidden;
  padding: 1rem;
  border-radius: 18px;
  border: 1px solid rgba(15, 23, 42, 0.05);
  background: linear-gradient(145deg, rgba(255, 255, 255, 0.9), rgba(224, 231, 255, 0.7));
  box-shadow: var(--shadow-soft);
}

.gradient {
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at 20% 20%, rgba(37, 99, 235, 0.12), transparent 40%),
    radial-gradient(circle at 80% 0%, rgba(16, 185, 129, 0.1), transparent 30%);
  filter: blur(10px);
  opacity: 0.8;
}

.content {
  position: relative;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  z-index: 1;
}

.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.spark {
  width: 12px;
  height: 12px;
  background: linear-gradient(120deg, #60a5fa, #34d399);
  border-radius: 50%;
  box-shadow: 0 0 0 6px rgba(37, 99, 235, 0.12);
}

h4 {
  margin: 0.15rem 0;
  color: #0f172a;
  font-size: 1.1rem;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
}

.pill {
  background: rgba(255, 255, 255, 0.7);
}
</style>
