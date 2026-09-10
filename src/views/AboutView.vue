<template>
  <div class="about-page">
    <div class="container py-5">

      <!-- Encabezado -->
      <span class="eyebrow">
        <span class="dash"></span> Sobre mí
      </span>
      <h1 class="about-title">{{ personal.nombre }}</h1>
      <h2 class="about-subtitle">{{ personal.titulo }}</h2>
      <p class="about-tagline">{{ fraseCreativa }}</p>

      <div class="action-row">
        <a :href="'https://github.com/' + personal.github" target="_blank" class="btn-solid">
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8"/></svg>
          GitHub
        </a>
        <a :href="personal.linkedin" target="_blank" class="btn-outline">
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16"><path d="M0 1.146C0 .513.526 0 1.175 0h13.65C15.474 0 16 .513 16 1.146v13.708c0 .633-.526 1.146-1.175 1.146H1.175C.526 16 0 15.487 0 14.854zm4.943 12.248V6.169H2.542v7.225zm-1.2-8.212c.837 0 1.358-.554 1.358-1.248-.015-.709-.52-1.248-1.342-1.248S2.4 3.226 2.4 3.934c0 .694.521 1.248 1.327 1.248zm4.908 8.212V9.359c0-.216.016-.432.08-.586.173-.431.568-.878 1.232-.878.869 0 1.216.662 1.216 1.634v3.865h2.401V9.25c0-2.22-1.184-3.252-2.764-3.252-1.274 0-1.845.7-2.165 1.193v.025h-.016l.016-.025V6.169h-2.4c.03.678 0 7.225 0 7.225z"/></svg>
          LinkedIn
        </a>
        <a href="/Bryan_Alzamora_CV.pdf" download class="btn-outline">
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16"><path d="M.5 9.9a.5.5 0 0 1 .5.5v2.5a1 1 0 0 0 1 1h12a1 1 0 0 0 1-1v-2.5a.5.5 0 0 1 1 0v2.5a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2v-2.5a.5.5 0 0 1 .5-.5"/><path d="M7.646 11.854a.5.5 0 0 0 .708 0l3-3a.5.5 0 0 0-.708-.708L8.5 10.293V1.5a.5.5 0 0 0-1 0v8.793L5.354 8.146a.5.5 0 1 0-.708.708z"/></svg>
          Descargar CV
        </a>
      </div>

      <!-- Sobre mí (con datos a la derecha) -->
      <div class="about-card mt-4">
        <div class="card-header">
          <span class="icon-badge">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16"><path d="M8 8a3 3 0 1 0 0-6 3 3 0 0 0 0 6m2-3a2 2 0 1 1-4 0 2 2 0 0 1 4 0m4 8c0 1-1 1-1 1H3s-1 0-1-1 1-4 6-4 6 3 6 4m-1-.004c-.001-.246-.154-.986-.832-1.664C11.516 10.68 10.289 10 8 10s-3.516.68-4.168 1.332c-.678.678-.83 1.418-.832 1.664z"/></svg>
          </span>
          <h3>Sobre mí</h3>
        </div>
        <div class="sobre-mi-row">
          <p class="block-text" v-html="sobreMi"></p>
          <div class="info-list">
            <div class="info-item">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-geo-alt" viewBox="0 0 16 16">
                    <path d="M12.166 8.94c-.524 1.062-1.234 2.12-1.96 3.07A32 32 0 0 1 8 14.58a32 32 0 0 1-2.206-2.57c-.726-.95-1.436-2.008-1.96-3.07C3.304 7.867 3 6.862 3 6a5 5 0 0 1 10 0c0 .862-.305 1.867-.834 2.94M8 16s6-5.686 6-10A6 6 0 0 0 2 6c0 4.314 6 10 6 10"/>
                    <path d="M8 8a2 2 0 1 1 0-4 2 2 0 0 1 0 4m0 1a3 3 0 1 0 0-6 3 3 0 0 0 0 6"/>
                </svg>
                <span>{{ personal.direccion.split(',').pop().trim() }}, España</span>
            </div>
            <div class="info-item">
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16"><path d="M8.211 2.047a.5.5 0 0 0-.422 0l-7.5 3.5a.5.5 0 0 0 .025.917l7.5 3a.5.5 0 0 0 .372 0L14 7.14V13a1 1 0 0 0-1 1v2h3v-2a1 1 0 0 0-1-1V6.739l.686-.275a.5.5 0 0 0 .025-.917zM8 8.46 1.758 5.965 8 3.052l6.242 2.913z"/></svg>
              <span>En formación</span>
            </div>
            <div class="info-item">
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16"><path d="M10.478 1.647a.5.5 0 1 0-.956-.294l-4 13a.5.5 0 0 0 .956.294zM4.854 4.146a.5.5 0 0 1 0 .708L1.707 8l3.147 3.146a.5.5 0 0 1-.708.708l-3.5-3.5a.5.5 0 0 1 0-.708l3.5-3.5a.5.5 0 0 1 .708 0m6.292 0a.5.5 0 0 0 0 .708L14.293 8l-3.147 3.146a.5.5 0 0 0 .708.708l3.5-3.5a.5.5 0 0 0 0-.708l-3.5-3.5a.5.5 0 0 0-.708 0"/></svg>
              <span>{{ personal.titulo }}</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Experiencia -->
      <div class="about-card mt-4">
        <div class="card-header">
          <span class="icon-badge">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16"><path d="M5 2a2 2 0 0 1 2-2h2a2 2 0 0 1 2 2h3.5A1.5 1.5 0 0 1 16 3.5v9a1.5 1.5 0 0 1-1.5 1.5H14a.5.5 0 0 1-1 0H3a.5.5 0 0 1-1 0h-.5A1.5 1.5 0 0 1 0 12.5v-9A1.5 1.5 0 0 1 1.5 2zm1 0h4a1 1 0 0 0-1-1H7a1 1 0 0 0-1 1M1.5 3a.5.5 0 0 0-.5.5v9a.5.5 0 0 0 .5.5H3V3zM15 12.5v-9a.5.5 0 0 0-.5-.5H13v10h1.5a.5.5 0 0 0 .5-.5m-3 .5V3H4v10z"/></svg>
          </span>
          <h3>Experiencia laboral</h3>
        </div>
        <div class="timeline">
          <div v-for="job in experiencia" :key="job.empresa" class="timeline-item">
            <div class="timeline-dot"></div>
            <div>
              <p class="job-meta">{{ job.fecha }} · {{ job.tipo }}</p>
              <h5 class="item-title">
                {{ job.puesto }} <span class="text-purple">| {{ job.empresa }}</span>
              </h5>
              <p class="block-text">{{ job.descripcion }}</p>
            </div>
          </div>
        </div>
      </div>

      <!-- Formación -->
      <div class="about-card mt-4">
        <div class="card-header">
          <span class="icon-badge">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16"><path d="M8.211 2.047a.5.5 0 0 0-.422 0l-7.5 3.5a.5.5 0 0 0 .025.917l7.5 3a.5.5 0 0 0 .372 0L14 7.14V13a1 1 0 0 0-1 1v2h3v-2a1 1 0 0 0-1-1V6.739l.686-.275a.5.5 0 0 0 .025-.917zM8 8.46 1.758 5.965 8 3.052l6.242 2.913z"/><path d="M4.176 9.032a.5.5 0 0 0-.656.327l-.5 1.7a.5.5 0 0 0 .294.605l4.5 1.8a.5.5 0 0 0 .372 0l4.5-1.8a.5.5 0 0 0 .294-.605l-.5-1.7a.5.5 0 0 0-.656-.327L8 10.466zm-.068 1.873.22-.748 3.496 1.311a.5.5 0 0 0 .352 0l3.496-1.311.22.748L8 12.46z"/></svg>
          </span>
          <h3>Formación académica</h3>
        </div>
        <div class="timeline">
            <div v-for="edu in educacion" :key="edu.institucion" class="timeline-item">
                <div class="timeline-dot"></div>
                <div>
                    <h5 class="item-title">{{ edu.titulo }}</h5>
                    <p class="job-meta">{{ edu.institucion }} · {{ edu.fecha }}</p>
                </div>
            </div>
        </div>
      </div>

      <!-- Habilidades técnicas -->
      <div class="about-card mt-4">
        <div class="card-header">
          <span class="icon-badge">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
                <path d="M10.478 1.647a.5.5 0 1 0-.956-.294l-4 13a.5.5 0 0 0 .956.294zM4.854 4.146a.5.5 0 0 1 0 .708L1.707 8l3.147 3.146a.5.5 0 0 1-.708.708l-3.5-3.5a.5.5 0 0 1 0-.708l3.5-3.5a.5.5 0 0 1 .708 0m6.292 0a.5.5 0 0 0 0 .708L14.293 8l-3.147 3.146a.5.5 0 0 0 .708.708l3.5-3.5a.5.5 0 0 0 0-.708l-3.5-3.5a.5.5 0 0 0-.708 0"/>
            </svg>
          </span>
          <h3>Habilidades técnicas</h3>
        </div>
        <div class="skills-grid">
          <div v-for="(items, category) in skills" :key="category">
            <h5 class="item-title">{{ formatCategory(category) }}</h5>
            <div class="skills-chips">
                <span v-for="skill in items" :key="skill.nombre" class="chip">{{ skill.nombre }}</span>
            </div>
          </div>
        </div>
      </div>

      <!-- CTA -->
      <div class="cta-banner mt-4">
        <div class="cta-content">
          <span class="eyebrow light">
            <span class="dash"></span> Trabajamos juntos
          </span>
          <h2 class="cta-title">Escríbeme y hablemos de tu proyecto.</h2>
          <p class="cta-text">Estoy disponible para nuevas oportunidades, colaboraciones y proyectos.</p>
        </div>
        <router-link to="/contacto" class="btn-solid">Hablemos →</router-link>
      </div>

    </div>
  </div>
</template>

<script setup>
import { portfolioData } from '@/data/portfolioData.js'
const { personal, sobreMi, idiomas, experiencia, educacion, skills, fraseCreativa } = portfolioData

const categoryLabels = {
  lenguajes: 'Lenguajes',
  frameworks: 'Frameworks',
  herramientas: 'Herramientas',
  ias: 'IA'
}

const formatCategory = (key) => categoryLabels[key] || key
</script>

<style scoped>
.about-page {
  background-color: #FAFAFA;
  padding: 40px 0 60px;
}

.eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  color: #6C4CF1;
  font-size: 0.8rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 2px;
  margin-bottom: 12px;
}
.eyebrow.light {
  color: rgba(255,255,255,0.85);
}
.dash {
  width: 20px;
  height: 2px;
  background: currentColor;
}

.about-title {
  font-size: clamp(2rem, 5vw, 3rem);
  font-weight: 800;
  color: #111111;
  line-height: 1.1;
  margin-bottom: 4px;
}
.about-subtitle {
  font-size: 1.15rem;
  font-weight: 500;
  color: #6B6B6B;
  margin-bottom: 12px;
}
.about-tagline {
  color: #6B6B6B;
  max-width: 520px;
  line-height: 1.6;
  margin-bottom: 24px;
}

.action-row {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  margin-bottom: 8px;
}
.btn-solid, .btn-outline {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  border-radius: 10px;
  font-weight: 600;
  font-size: 0.9rem;
  padding: 10px 18px;
  text-decoration: none;
  transition: all 0.25s;
  white-space: nowrap;
}
.btn-solid {
  background: #6C4CF1;
  color: #fff;
  border: 1px solid #6C4CF1;
}
.btn-solid:hover { background: #5a3fd6; }
.btn-outline {
  background: #FFFFFF;
  color: #111111;
  border: 1px solid #EAEAEA;
}
.btn-outline:hover { border-color: #6C4CF1; color: #6C4CF1; }

.mt-4 { margin-top: 24px; }

.about-card {
  background: #FFFFFF;
  border: 1px solid #EAEAEA;
  border-radius: 16px;
  padding: 32px;
}

.card-header {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 24px;
}
.card-header h3 {
  font-size: 1.05rem;
  font-weight: 700;
  color: #111111;
  margin: 0;
}
.icon-badge {
  width: 32px;
  height: 32px;
  border-radius: 8px;
  background: #F1EDFF;
  color: #6C4CF1;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.sobre-mi-row {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 40px;
}

.info-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
  border-left: 1px solid #EAEAEA;
  padding-left: 32px;
}
.info-item {
  display: flex;
  align-items: center;
  gap: 10px;
  color: #111111;
  font-size: 0.9rem;
  font-weight: 500;
}
.info-item svg,
.info-item i {
  color: #6C4CF1;
}

.block-text {
  color: #6B6B6B;
  line-height: 1.65;
  font-size: 0.95rem;
}

.text-purple { color: #6C4CF1; font-weight: 600; }

.timeline {
  position: relative;
  padding-left: 20px;
}
.timeline::before {
  content: '';
  position: absolute;
  left: 4px;
  top: 6px;
  bottom: 6px;
  width: 1px;
  background: #EAEAEA;
}
.timeline-item {
  position: relative;
  padding-bottom: 24px;
  margin-bottom: 24px;
  border-bottom: 1px solid #F0F0F0;
}
.timeline-item:last-child {
  margin-bottom: 0;
  padding-bottom: 0;
  border-bottom: none;
}
.timeline-dot {
  position: absolute;
  left: -20px;
  top: 6px;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #6C4CF1;
}
.item-title {
  color: #111111;
  font-weight: 700;
  font-size: 0.98rem;
  margin: 4px 0;
}
.job-meta {
  color: #8B949E;
  font-size: 0.85rem;
  margin-bottom: 0;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 32px;
}
.skills-chips {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-top: 12px;
}
.chip {
  background: #F1EDFF;
  color: #6C4CF1;
  font-size: 0.82rem;
  font-weight: 600;
  padding: 6px 12px;
  border-radius: 100px;
}

.cta-banner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;
  flex-wrap: wrap;
  background: #F1EDFF;
  border-radius: 20px;
  padding: 40px;
}
.cta-content {
  max-width: 560px;
}
.cta-title {
  font-size: clamp(1.4rem, 3vw, 1.9rem);
  font-weight: 800;
  color: #111111;
  margin-bottom: 8px;
}
.cta-text {
  color: #6B6B6B;
  margin: 0;
}

@media (max-width: 768px) {
  .sobre-mi-row {
    grid-template-columns: 1fr;
  }
  .info-list {
    border-left: none;
    border-top: 1px solid #EAEAEA;
    padding-left: 0;
    padding-top: 20px;
  }
  .skills-grid {
    grid-template-columns: 1fr;
  }
  .cta-banner {
    padding: 28px;
  }
}
</style>