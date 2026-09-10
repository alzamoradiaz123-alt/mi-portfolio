<template>
  <section id="passion" class="passion-section fade-up">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-lg-9 text-center">

          <div class="section-label">
            <span class="line"></span>
            <span class="label-badge">Perfil</span>
            <span class="line"></span>
          </div>

          <h2 class="passion-title">{{ perfil.titulo }}</h2>

          <p class="passion-subtitle">{{ perfil.subtitulo }}</p>

          <div class="features-row">
            <div
              v-for="(feature, index) in perfil.features"
              :key="feature.texto"
              class="feature-item"
              :class="{ 'with-divider': index !== 0 }"
            >
              <img :src="feature.logo" :alt="feature.texto" class="feature-logo" />
              <span>{{ feature.texto }}</span>
            </div>
          </div>

          <div class="underline"></div>

        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { portfolioData } from '@/data/portfolioData.js'
const perfil = portfolioData.perfil
</script>

<style scoped>
.passion-section {
  background-color: #FFFFFF;
  border-top: 1px solid #EAEAEA;
  border-bottom: 1px solid #EAEAEA;
  padding: 120px 0;
}

.section-label {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
  margin-bottom: 32px;
}
.section-label .line {
  width: 40px;
  height: 1px;
  background: #D8D8D8;
}
.label-badge {
  background: none;
  padding: 0;
  border-radius: 0;
  color: #6B6B6B;
  font-size: 0.75rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 4px;
}

.passion-title {
  font-size: clamp(2.2rem, 5vw, 3.4rem);
  font-weight: 800;
  color: #111111;
  line-height: 1.15;
  margin-bottom: 28px;
}

.passion-subtitle {
  font-size: 1.15rem;
  color: #6B6B6B;
  line-height: 1.6;
  max-width: 560px;
  margin: 0 auto;
}

.features-row {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 20px;
  margin-top: 56px;
}

.feature-item {
  display: flex;
  align-items: center;
  gap: 1px;
  color: #111111;
  font-weight: 500;
  font-size: 1rem;
  padding: 0 16px;
}
.feature-logo {
  width: 40px;
  height: 40px;
  object-fit: contain;
}
.feature-item.with-divider {
  border-left: 1px solid #EAEAEA;
}

.underline {
  width: 60px;
  height: 3px;
  background: #6C4CF1;
  border-radius: 2px;
  margin: 40px auto 0;
}

@media (max-width: 576px) {
  .features-row {
    flex-direction: column;
    gap: 16px;
  }
  .feature-item.with-divider {
    border-left: none;
    border-top: 1px solid #EAEAEA;
    padding-top: 16px;
  }
}
</style>