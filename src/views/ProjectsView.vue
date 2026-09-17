<template>
  <div class="projects-page">
    <div class="container py-5">
      <span class="eyebrow">
        <span class="dash"></span> Mis proyectos
      </span>
      <h1 class="projects-title">Proyectos</h1>
      <p class="projects-subtitle">
        Una selección de los trabajos en los que he aplicado mis conocimientos de desarrollo web.
      </p>

      <div class="projects-grid">
        <!-- Proyecto: Mundanza Segura -->
        <a href="https://www.mundanzasegura.com/" target="_blank" class="project-card">
          <div class="project-image-wrapper">
            <!-- Reemplaza esta imagen con una captura de pantalla de la web -->
            <img src="https://via.placeholder.com/600x400/FAFAFA/6C4CF1?text=Mundanza+Segura" alt="Mundanza Segura" class="project-image" />
            <div class="project-overlay">
              <span class="project-link-icon">→</span>
            </div>
          </div>
          <div class="project-info">
            <h3 class="project-name">Mundanza Segura</h3>
            <p class="project-description">
              Marketplace de transporte que conecta a usuarios con transportistas verificados. Permite publicar mudanzas, recibir propuestas, comparar precios y cerrar acuerdos de forma segura.
            </p>
            <div class="project-tags">
              <span class="tag">Vue.js</span>
              <span class="tag">Marketplace</span>
              <span class="tag">Web App</span>
            </div>
          </div>
        </a>
      </div>
    </div>
  </div>
</template>

<script setup>
// No se necesita lógica por ahora
</script>

<style scoped>
.projects-page {
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
.dash {
  width: 20px;
  height: 2px;
  background: currentColor;
}

.projects-title {
  font-size: clamp(2rem, 5vw, 3rem);
  font-weight: 800;
  color: #111111;
  line-height: 1.1;
  margin-bottom: 8px;
}
.projects-subtitle {
  color: #6B6B6B;
  max-width: 520px;
  line-height: 1.6;
  margin-bottom: 48px;
}

/* Grid de proyectos */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 32px;
}

/* Tarjeta de proyecto */
.project-card {
  display: block;
  background: #FFFFFF;
  border: 1px solid #EAEAEA;
  border-radius: 16px;
  overflow: hidden;
  text-decoration: none;
  transition: transform 0.3s, box-shadow 0.3s, border-color 0.3s;
}
.project-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 12px 30px rgba(108, 76, 241, 0.1);
  border-color: rgba(108, 76, 241, 0.3);
}

.project-image-wrapper {
  position: relative;
  aspect-ratio: 3 / 2;
  overflow: hidden;
  background: #F1EDFF;
}
.project-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s ease;
}
.project-card:hover .project-image {
  transform: scale(1.05);
}

/* Overlay que aparece al hacer hover */
.project-overlay {
  position: absolute;
  inset: 0;
  background: rgba(108, 76, 241, 0.85);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}
.project-card:hover .project-overlay {
  opacity: 1;
}
.project-link-icon {
  color: #FFFFFF;
  font-size: 2rem;
  font-weight: 700;
}

.project-info {
  padding: 24px;
}
.project-name {
  font-size: 1.25rem;
  font-weight: 700;
  color: #111111;
  margin-bottom: 8px;
}
.project-description {
  color: #6B6B6B;
  font-size: 0.9rem;
  line-height: 1.6;
  margin-bottom: 16px;
}
.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}
.tag {
  background: #F1EDFF;
  color: #6C4CF1;
  font-size: 0.75rem;
  font-weight: 600;
  padding: 4px 10px;
  border-radius: 100px;
}

@media (max-width: 576px) {
  .projects-grid {
    grid-template-columns: 1fr;
  }
}
</style>