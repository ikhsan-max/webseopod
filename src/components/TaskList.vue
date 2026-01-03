<script setup>
const props = defineProps({
  items: {
    type: Array,
    default: () => [],
  },
});

const badgeClass = (status) => {
  if (status === 'In progress') return 'in-progress';
  if (status === 'Ready to run') return 'ready';
  return 'planned';
};
</script>

<template>
  <div class="task-list glass-card">
    <div class="task" v-for="task in props.items" :key="task.title">
      <div class="task-main">
        <div class="task-head">
          <h4>{{ task.title }}</h4>
          <span class="pill" :class="badgeClass(task.status)">{{ task.status }}</span>
        </div>
        <p class="muted">{{ task.detail }}</p>
      </div>
      <div class="task-meta">
        <span class="badge">{{ task.impact }}</span>
        <button class="btn btn-secondary small">Lihat detail</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.task-list {
  display: flex;
  flex-direction: column;
  gap: 0.9rem;
  padding: 1.25rem;
  border: 1px solid rgba(15, 23, 42, 0.05);
}

.task {
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 1rem;
  padding: 1rem 1.1rem;
  border-radius: 16px;
  background: rgba(255, 255, 255, 0.9);
  border: 1px solid rgba(15, 23, 42, 0.05);
}

.task-head {
  display: flex;
  align-items: center;
  gap: 0.6rem;
  flex-wrap: wrap;
}

h4 {
  margin: 0;
  color: #0f172a;
}

.task-meta {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.badge {
  padding: 0.35rem 0.65rem;
  border-radius: 12px;
  background: rgba(15, 23, 42, 0.05);
  font-weight: 700;
}

.pill {
  padding: 0.25rem 0.6rem;
  border-radius: 999px;
  font-weight: 700;
  font-size: 0.9rem;
}

.pill.in-progress {
  background: rgba(37, 99, 235, 0.12);
  color: #1d4ed8;
}

.pill.ready {
  background: rgba(16, 185, 129, 0.16);
  color: #047857;
}

.pill.planned {
  background: rgba(15, 23, 42, 0.05);
  color: #0f172a;
}

@media (max-width: 720px) {
  .task {
    grid-template-columns: 1fr;
  }
  .task-meta {
    justify-content: flex-start;
  }
}
</style>
