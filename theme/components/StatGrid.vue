<script setup>
defineProps({
  stats: {
    type: Array,
    default: () => []
    // Each item: { value: string, label: string }
  }
})
</script>

<template>
  <div class="gp-stat-grid">
    <div v-for="(stat, i) in stats" :key="i" class="gp-stat-card" :style="{ animationDelay: `${0.1 + i * 0.1}s` }">
      <div class="gp-stat-value">{{ stat.value }}</div>
      <div class="gp-stat-label">{{ stat.label }}</div>
      <div class="gp-stat-glow" />
    </div>
  </div>
</template>

<style scoped>
.gp-stat-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
  max-width: 900px;
  margin: 0 auto;
}

.gp-stat-card {
  position: relative;
  background: var(--gp-bg-surface);
  border: 1px solid var(--gp-border);
  border-radius: var(--gp-radius);
  padding: 1.75rem 1.25rem;
  text-align: center;
  overflow: hidden;
  animation: gp-fade-up 0.5s cubic-bezier(0.22, 1, 0.36, 1) both;
  transition: border-color 0.3s ease, transform 0.3s ease;
}

.gp-stat-card:hover {
  border-color: rgba(0, 212, 255, 0.3);
  transform: translateY(-2px);
}

.gp-stat-glow {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 60%;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--gp-accent), transparent);
  opacity: 0.5;
}

.gp-stat-value {
  font-size: 2.5rem;
  font-weight: 700;
  font-family: 'JetBrains Mono', monospace;
  background: linear-gradient(135deg, var(--gp-accent), var(--gp-accent-secondary));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  line-height: 1.2;
  margin-bottom: 0.5rem;
}

.gp-stat-label {
  font-size: 0.95rem;
  color: var(--gp-text-muted);
  text-transform: uppercase;
  letter-spacing: 0.08em;
  font-weight: 500;
}
</style>
