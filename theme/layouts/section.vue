<template>
  <div class="slidev-layout gp-section">
    <div class="gp-section-line gp-section-line-left" />
    <div class="gp-section-line gp-section-line-right" />
    <div class="gp-section-content">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.gp-section {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  padding: 3rem 4rem;
  text-align: center;
  background: radial-gradient(ellipse at 50% 50%, rgba(0, 212, 255, 0.04) 0%, transparent 70%);
}

.gp-section-line {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 20%;
  height: 1px;
  z-index: 0;
}

.gp-section-line-left {
  left: 0;
  background: linear-gradient(90deg, transparent, var(--gp-accent));
  animation: gp-line-extend 1s cubic-bezier(0.22, 1, 0.36, 1) 0.4s both;
}

.gp-section-line-right {
  right: 0;
  background: linear-gradient(90deg, var(--gp-accent-secondary), transparent);
  animation: gp-line-extend 1s cubic-bezier(0.22, 1, 0.36, 1) 0.6s both;
}

@keyframes gp-line-extend {
  from { transform: translateY(-50%) scaleX(0); }
  to { transform: translateY(-50%) scaleX(1); }
}

.gp-section-content {
  position: relative;
  z-index: 1;
}

.gp-section :deep(h1) {
  font-size: 4rem;
  font-weight: 700;
  letter-spacing: -0.03em;
  animation: gp-headline-in 0.7s cubic-bezier(0.22, 1, 0.36, 1) both;
  background: linear-gradient(135deg, var(--gp-accent), var(--gp-text), var(--gp-accent-secondary));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.gp-section :deep(h1)::after {
  content: '';
  display: block;
  height: 3px;
  width: 120px;
  margin: 1.25rem auto 0;
  background: linear-gradient(90deg, var(--gp-accent), var(--gp-accent-secondary));
  border-radius: 2px;
  animation: gp-underline-draw 1s cubic-bezier(0.22, 1, 0.36, 1) 0.3s both;
}

.gp-section :deep(p) {
  color: var(--gp-text-muted);
  font-size: 1.3rem;
  margin-top: 1.25rem;
  animation: gp-fade-up 0.5s cubic-bezier(0.22, 1, 0.36, 1) 0.4s both;
}
</style>
