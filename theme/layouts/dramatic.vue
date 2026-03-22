<template>
  <div class="slidev-layout gp-dramatic">
    <div class="gp-dramatic-vortex">
      <div class="gp-dramatic-ring gp-dramatic-ring-1" />
      <div class="gp-dramatic-ring gp-dramatic-ring-2" />
      <div class="gp-dramatic-ring gp-dramatic-ring-3" />
      <div class="gp-dramatic-core" />
    </div>
    <div class="gp-dramatic-content">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.gp-dramatic {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  text-align: center;
  padding: 3rem;
  background: radial-gradient(ellipse at center, rgba(0, 212, 255, 0.06) 0%, #0d1117 70%);
}

.gp-dramatic-vortex {
  position: absolute;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  pointer-events: none;
  z-index: 0;
}

.gp-dramatic-ring {
  position: absolute;
  border-radius: 50%;
  border: 1px solid rgba(0, 212, 255, 0.1);
}

.gp-dramatic-ring-1 {
  width: 600px;
  height: 600px;
  border-color: rgba(0, 212, 255, 0.04);
  animation: gp-ring-pulse 8s ease-in-out infinite;
}

.gp-dramatic-ring-2 {
  width: 400px;
  height: 400px;
  border-color: rgba(0, 212, 255, 0.08);
  animation: gp-ring-pulse 6s ease-in-out infinite 1s;
}

.gp-dramatic-ring-3 {
  width: 200px;
  height: 200px;
  border-color: rgba(124, 58, 237, 0.12);
  animation: gp-ring-pulse 4s ease-in-out infinite 0.5s;
}

.gp-dramatic-core {
  position: absolute;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(0, 212, 255, 0.6), rgba(0, 212, 255, 0) 70%);
  animation: gp-core-breathe 3s ease-in-out infinite;
}

@keyframes gp-ring-pulse {
  0%, 100% { transform: scale(1); opacity: 1; }
  50% { transform: scale(1.08); opacity: 0.6; }
}

@keyframes gp-core-breathe {
  0%, 100% { transform: scale(1); box-shadow: 0 0 40px rgba(0, 212, 255, 0.3); }
  50% { transform: scale(1.5); box-shadow: 0 0 80px rgba(0, 212, 255, 0.5), 0 0 120px rgba(124, 58, 237, 0.2); }
}

.gp-dramatic-content {
  position: relative;
  z-index: 1;
  max-width: 85%;
}

.gp-dramatic :deep(h1) {
  font-size: 3.5rem;
  font-weight: 700;
  letter-spacing: -0.04em;
  background: linear-gradient(135deg, var(--gp-accent) 0%, #fff 50%, var(--gp-accent-secondary) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  animation: gp-headline-in 0.8s cubic-bezier(0.22, 1, 0.36, 1) both;
  margin-bottom: 1.5rem;
  text-shadow: none;
}

.gp-dramatic :deep(p) {
  color: var(--gp-text-muted);
  font-size: 1.4rem;
  line-height: 1.6;
  animation: gp-fade-up 0.6s cubic-bezier(0.22, 1, 0.36, 1) 0.3s both;
}

.gp-dramatic :deep(strong) {
  color: var(--gp-accent);
  font-weight: 700;
}
</style>
