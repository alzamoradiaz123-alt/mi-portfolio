<template>
  <section id="hero" class="hero-section">
    <div class="container text-center">
      <span class="eyebrow">
        <span class="dot"></span> DESARROLLADOR WEB
      </span>

      <h1 class="hero-title">
        ALZAMORA<span class="dot-purple">.</span>
      </h1>

      <p class="hero-subtitle">
        Código limpio, soluciones creativas.
      </p>

      <a href="#passion" class="scroll-indicator">
        <span class="scroll-line"></span>
        Descubre más
      </a>
    </div>
  </section>
</template>

<style scoped>
.hero-section {
  min-height: 90vh;
  display: flex;
  align-items: center;
  background: #FAFAFA;
}

.eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  color: #6B6B6B;
  font-size: 0.85rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 2px;
  margin-bottom: 28px;
}
.dot {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: #6C4CF1;
}

.hero-title {
  font-size: clamp(2.5rem, 7vw, 5.5rem);
  font-weight: 800;
  color: #111111;
  letter-spacing: 0.3em;
  margin: 0;
}
.dot-purple {
  color: #6C4CF1;
}

.hero-subtitle {
  font-size: 1.1rem;
  color: #6B6B6B;
  margin-top: 24px;
}

.scroll-indicator {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  margin-top: 64px;
  color: #6B6B6B;
  font-size: 0.75rem;
  text-transform: uppercase;
  letter-spacing: 1px;
  text-decoration: none;
  transition: color 0.3s;
}
.scroll-indicator:hover {
  color: #6C4CF1;
}
.scroll-line {
  width: 1px;
  height: 40px;
  background: #D8D8D8;
}

@media (max-width: 768px) {
  .hero-title {
    letter-spacing: 0.15em;
  }
  .scroll-indicator {
    margin-top: 40px;
  }
}
</style>