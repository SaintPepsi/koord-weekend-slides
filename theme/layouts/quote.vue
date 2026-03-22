<template>
  <div class="slidev-layout gp-quote">
    <div class="gp-quote-mark gp-quote-open">"</div>
    <div class="gp-quote-mark gp-quote-close">"</div>
    <div class="gp-quote-accent-line" />
    <div class="gp-quote-content">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.gp-quote {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  padding: 3rem 6rem;
  background: radial-gradient(ellipse at 30% 50%, rgba(0, 212, 255, 0.04) 0%, transparent 60%),
              radial-gradient(ellipse at 70% 80%, rgba(124, 58, 237, 0.03) 0%, transparent 50%);
}

.gp-quote-mark {
  position: absolute;
  font-size: 18rem;
  font-family: Georgia, 'Times New Roman', serif;
  line-height: 1;
  pointer-events: none;
  z-index: 0;
  background: linear-gradient(135deg, rgba(0, 212, 255, 0.12), rgba(124, 58, 237, 0.08));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.gp-quote-open {
  top: -0.5rem;
  left: 2.5rem;
  animation: gp-fade-up 0.8s cubic-bezier(0.22, 1, 0.36, 1) both;
}

.gp-quote-close {
  bottom: -4rem;
  right: 2.5rem;
  animation: gp-fade-up 0.8s cubic-bezier(0.22, 1, 0.36, 1) 0.2s both;
}

.gp-quote-accent-line {
  position: absolute;
  left: 6rem;
  top: 50%;
  transform: translateY(-50%);
  width: 3px;
  height: 40%;
  background: linear-gradient(180deg, transparent, var(--gp-accent), var(--gp-accent-secondary), transparent);
  border-radius: 2px;
  z-index: 0;
  animation: gp-fade-up 0.6s cubic-bezier(0.22, 1, 0.36, 1) 0.1s both;
}

.gp-quote-content {
  position: relative;
  z-index: 1;
  max-width: 75%;
  padding-left: 2rem;
}

/* Reset base blockquote border */
.gp-quote :deep(blockquote) {
  border-left: none;
  padding-left: 0;
  font-style: normal;
  color: inherit;
}

.gp-quote :deep(blockquote p) {
  font-size: 2rem;
  line-height: 1.5;
  font-style: italic;
  font-weight: 400;
  color: var(--gp-text);
  animation: gp-fade-up 0.7s cubic-bezier(0.22, 1, 0.36, 1) 0.15s both;
  letter-spacing: -0.01em;
}

/* Attribution */
.gp-quote :deep(blockquote + p),
.gp-quote :deep(p:last-child:not(:first-child)) {
  color: var(--gp-accent);
  font-size: 1.05rem;
  font-style: normal;
  font-weight: 500;
  margin-top: 2rem;
  border-left: none;
  letter-spacing: 0.04em;
  text-transform: uppercase;
  animation: gp-fade-up 0.5s cubic-bezier(0.22, 1, 0.36, 1) 0.4s both;
}
</style>
