<template>
  <div class="slidev-layout gp-cover">
    <!-- Animated node network in background -->
    <svg class="gp-cover-network" viewBox="0 0 1920 1080" preserveAspectRatio="xMidYMid slice">
      <defs>
        <radialGradient id="coverNodeGlow" cx="50%" cy="50%" r="50%">
          <stop offset="0%" stop-color="#00d4ff" stop-opacity="0.6"/>
          <stop offset="100%" stop-color="#00d4ff" stop-opacity="0"/>
        </radialGradient>
      </defs>
      <!-- Connection lines -->
      <g stroke="#00d4ff" stroke-opacity="0.08" stroke-width="1" fill="none">
        <line x1="200" y1="200" x2="500" y2="350"/>
        <line x1="500" y1="350" x2="800" y2="250"/>
        <line x1="800" y1="250" x2="1100" y2="400"/>
        <line x1="1100" y1="400" x2="1400" y2="280"/>
        <line x1="1400" y1="280" x2="1700" y2="380"/>
        <line x1="500" y1="350" x2="650" y2="600"/>
        <line x1="650" y1="600" x2="960" y2="540"/>
        <line x1="960" y1="540" x2="1100" y2="400"/>
        <line x1="1100" y1="400" x2="1300" y2="650"/>
        <line x1="1300" y1="650" x2="1700" y2="550"/>
        <line x1="200" y1="200" x2="300" y2="550"/>
        <line x1="300" y1="550" x2="650" y2="600"/>
        <line x1="960" y1="540" x2="900" y2="780"/>
        <line x1="900" y1="780" x2="1100" y2="850"/>
        <line x1="1100" y1="850" x2="1300" y2="650"/>
        <line x1="1700" y1="550" x2="1750" y2="780"/>
      </g>
      <!-- Nodes -->
      <g fill="#00d4ff">
        <circle cx="200" cy="200" r="2" opacity="0.4">
          <animate attributeName="opacity" values="0.4;0.7;0.4" dur="3s" repeatCount="indefinite"/>
        </circle>
        <circle cx="500" cy="350" r="3" opacity="0.5">
          <animate attributeName="opacity" values="0.5;0.8;0.5" dur="4s" repeatCount="indefinite"/>
        </circle>
        <circle cx="800" cy="250" r="2" opacity="0.4">
          <animate attributeName="opacity" values="0.4;0.6;0.4" dur="3.5s" repeatCount="indefinite"/>
        </circle>
        <circle cx="960" cy="540" r="5" opacity="0.7">
          <animate attributeName="opacity" values="0.7;1;0.7" dur="2.5s" repeatCount="indefinite"/>
          <animate attributeName="r" values="5;7;5" dur="2.5s" repeatCount="indefinite"/>
        </circle>
        <circle cx="1100" cy="400" r="3" opacity="0.5">
          <animate attributeName="opacity" values="0.5;0.8;0.5" dur="3s" repeatCount="indefinite" begin="0.5s"/>
        </circle>
        <circle cx="1400" cy="280" r="2" opacity="0.4">
          <animate attributeName="opacity" values="0.4;0.7;0.4" dur="4s" repeatCount="indefinite" begin="1s"/>
        </circle>
        <circle cx="1700" cy="380" r="2.5" opacity="0.45">
          <animate attributeName="opacity" values="0.45;0.75;0.45" dur="3.5s" repeatCount="indefinite"/>
        </circle>
        <circle cx="650" cy="600" r="2.5" opacity="0.45"/>
        <circle cx="1300" cy="650" r="2.5" opacity="0.45"/>
        <circle cx="300" cy="550" r="2" opacity="0.3"/>
        <circle cx="1700" cy="550" r="2" opacity="0.3"/>
        <circle cx="900" cy="780" r="2" opacity="0.3"/>
        <circle cx="1100" cy="850" r="2" opacity="0.3"/>
        <circle cx="1750" cy="780" r="2" opacity="0.3"/>
      </g>
      <!-- Center glow -->
      <circle cx="960" cy="540" r="40" fill="url(#coverNodeGlow)" opacity="0.2"/>
    </svg>

    <div class="gp-cover-orb gp-cover-orb-1" />
    <div class="gp-cover-orb gp-cover-orb-2" />
    <div class="gp-cover-orb gp-cover-orb-3" />
    <div class="gp-cover-content">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.gp-cover {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  text-align: center;
  padding: 3rem;
}

.gp-cover-network {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
  pointer-events: none;
  opacity: 0.8;
}

/* Floating orbs for depth */
.gp-cover-orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(100px);
  pointer-events: none;
  z-index: 0;
}

.gp-cover-orb-1 {
  width: 500px;
  height: 500px;
  background: rgba(0, 212, 255, 0.1);
  top: -15%;
  right: -8%;
  animation: gp-orb-float 14s ease-in-out infinite;
}

.gp-cover-orb-2 {
  width: 400px;
  height: 400px;
  background: rgba(124, 58, 237, 0.08);
  bottom: -15%;
  left: -8%;
  animation: gp-orb-float 18s ease-in-out infinite reverse;
}

.gp-cover-orb-3 {
  width: 250px;
  height: 250px;
  background: rgba(0, 212, 255, 0.06);
  top: 40%;
  left: 30%;
  animation: gp-orb-float 10s ease-in-out infinite 3s;
}

@keyframes gp-orb-float {
  0%, 100% { transform: translate(0, 0) scale(1); }
  33% { transform: translate(30px, -20px) scale(1.05); }
  66% { transform: translate(-20px, 15px) scale(0.95); }
}

.gp-cover-content {
  position: relative;
  z-index: 1;
  max-width: 80%;
}

.gp-cover :deep(h1) {
  font-size: 5rem;
  font-weight: 700;
  letter-spacing: -0.04em;
  line-height: 1.1;
  background: linear-gradient(135deg, var(--gp-accent) 0%, #e6edf3 40%, var(--gp-accent-secondary) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  animation: gp-headline-in 1s cubic-bezier(0.22, 1, 0.36, 1) both;
  margin-bottom: 1.5rem;
}

.gp-cover :deep(p) {
  color: var(--gp-text-muted);
  font-size: 1.5rem;
  margin-top: 0.5rem;
  animation: gp-fade-up 0.6s cubic-bezier(0.22, 1, 0.36, 1) 0.3s both;
  letter-spacing: 0.03em;
}

.gp-cover :deep(p:first-of-type) {
  font-size: 1.6rem;
  color: var(--gp-text);
  font-weight: 500;
}
</style>
