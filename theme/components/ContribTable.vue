<script setup>
defineProps({
  rows: {
    type: Array,
    default: () => []
    // Each item: { name: string, type: string, messages: string, commits: string }
    // type: 'ai' | 'human'
  }
})
</script>

<template>
  <div class="gp-contrib-table">
    <div class="gp-contrib-header">
      <span class="gp-contrib-col-name">Agent</span>
      <span class="gp-contrib-col">Messages</span>
      <span class="gp-contrib-col">Commits</span>
    </div>
    <div
      v-for="(row, i) in rows"
      :key="i"
      class="gp-contrib-row"
      :class="{ 'gp-contrib-ai': row.type === 'ai' }"
      :style="{ animationDelay: `${0.2 + i * 0.12}s` }"
    >
      <span class="gp-contrib-col-name">
        <span class="gp-contrib-indicator" :class="row.type === 'ai' ? 'gp-indicator-ai' : 'gp-indicator-human'" />
        {{ row.name }}
        <span class="gp-contrib-badge">{{ row.type === 'ai' ? 'AI' : 'Human' }}</span>
      </span>
      <span class="gp-contrib-col gp-contrib-number">{{ row.messages }}</span>
      <span class="gp-contrib-col gp-contrib-number">{{ row.commits }}</span>
    </div>
  </div>
</template>

<style scoped>
.gp-contrib-table {
  max-width: 700px;
  margin: 0 auto;
  border: 1px solid var(--gp-border);
  border-radius: var(--gp-radius);
  overflow: hidden;
  background: var(--gp-bg-surface);
}

.gp-contrib-header {
  display: flex;
  padding: 0.75rem 1.5rem;
  background: var(--gp-bg-elevated);
  border-bottom: 1px solid var(--gp-border);
  font-size: 0.8rem;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: var(--gp-text-muted);
  font-weight: 600;
}

.gp-contrib-row {
  display: flex;
  padding: 1rem 1.5rem;
  border-bottom: 1px solid rgba(139, 148, 158, 0.08);
  animation: gp-fade-up 0.4s cubic-bezier(0.22, 1, 0.36, 1) both;
  transition: background 0.2s ease;
}

.gp-contrib-row:last-child {
  border-bottom: none;
}

.gp-contrib-row:hover {
  background: rgba(0, 212, 255, 0.03);
}

.gp-contrib-ai {
  background: rgba(0, 212, 255, 0.02);
}

.gp-contrib-col-name {
  flex: 2;
  display: flex;
  align-items: center;
  gap: 0.75rem;
  font-weight: 600;
  font-size: 1.1rem;
}

.gp-contrib-col {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
}

.gp-contrib-number {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1.15rem;
  font-weight: 600;
  color: var(--gp-text);
}

.gp-contrib-indicator {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  flex-shrink: 0;
}

.gp-indicator-ai {
  background: var(--gp-accent);
  box-shadow: 0 0 8px rgba(0, 212, 255, 0.4);
}

.gp-indicator-human {
  background: var(--gp-accent-secondary);
  box-shadow: 0 0 8px rgba(124, 58, 237, 0.4);
}

.gp-contrib-badge {
  font-size: 0.65rem;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  padding: 0.15em 0.5em;
  border-radius: 4px;
  font-weight: 600;
  color: var(--gp-text-muted);
  background: rgba(139, 148, 158, 0.1);
}
</style>
