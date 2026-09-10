<template>
  <section id="value" class="value-section fade-up">
    <div class="container">

      <div class="section-label">
        <span class="line"></span>
        <span class="label-badge">Mis servicios</span>
        <span class="line"></span>
      </div>

      <h2 class="value-title">¿Dónde puedo aportar valor?</h2>
      <p class="value-subtitle">
        Trabajo con tecnologías modernas para crear soluciones eficientes,
        escalables y adaptadas a tus necesidades.
      </p>

      <div class="row">
        <div class="col-md-4 mb-4" v-for="(item, index) in valueItems" :key="index">
          <div class="card-custom h-100" :style="{ '--accent': item.color }">
            <div class="card-top-bar"></div>
            <div class="card-body">
              <div class="icon-box" v-html="item.icon"></div>
              <h5 class="card-title">{{ item.title }}</h5>
              <p class="card-text">{{ item.description }}</p>
              <button type="button" class="arrow-btn" aria-label="Ver más">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-arrow-right" viewBox="0 0 16 16">
                  <path fill-rule="evenodd" d="M1 8a.5.5 0 0 1 .5-.5h11.793l-3.147-3.146a.5.5 0 0 1 .708-.708l4 4a.5.5 0 0 1 0 .708l-4 4a.5.5 0 0 1-.708-.708L13.293 8.5H1.5A.5.5 0 0 1 1 8"/>
                </svg>
              </button>
            </div>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const valueItems = ref([
  {
    color: '#6C63FF',
    icon: `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor" viewBox="0 0 16 16"><path d="M10.478 1.647a.5.5 0 1 0-.956-.294l-4 13a.5.5 0 0 0 .956.294zM4.854 4.146a.5.5 0 0 1 0 .708L1.707 8l3.147 3.146a.5.5 0 0 1-.708.708l-3.5-3.5a.5.5 0 0 1 0-.708l3.5-3.5a.5.5 0 0 1 .708 0m6.292 0a.5.5 0 0 0 0 .708L14.293 8l-3.147 3.146a.5.5 0 0 0 .708.708l3.5-3.5a.5.5 0 0 0 0-.708l-3.5-3.5a.5.5 0 0 0-.708 0"/></svg>`,
    title: 'Desarrollo Full Stack',
    description: 'Construyo aplicaciones web completas con Java, Spring Boot y Vue.js, desde el backend hasta el frontend.'
  },
  {
    color: '#22C55E',
    icon: `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor" viewBox="0 0 16 16"><path d="M4.318 2.687C5.234 2.271 6.536 2 8 2s2.766.27 3.682.687C12.644 3.125 13 3.627 13 4c0 .374-.356.875-1.318 1.313C10.766 5.729 9.464 6 8 6s-2.766-.27-3.682-.687C3.356 4.875 3 4.373 3 4c0-.374.356-.875 1.318-1.313M13 5.698V7c0 .374-.356.875-1.318 1.313C10.766 8.729 9.464 9 8 9s-2.766-.27-3.682-.687C3.356 7.875 3 7.373 3 7V5.698c.271.202.58.378.904.525C4.978 6.711 6.427 7 8 7s3.022-.289 4.096-.777A5 5 0 0 0 13 5.698M14 4c0-1.007-.875-1.755-1.904-2.223C11.022 1.289 9.573 1 8 1s-3.022.289-4.096.777C2.875 2.245 2 2.993 2 4v9c0 1.007.875 1.755 1.904 2.223C4.978 15.71 6.427 16 8 16s3.022-.289 4.096-.777C13.125 14.755 14 14.007 14 13zm-1 4.698V10c0 .374-.356.875-1.318 1.313C10.766 11.729 9.464 12 8 12s-2.766-.27-3.682-.687C3.356 10.875 3 10.373 3 10V8.698c.271.202.58.378.904.525C4.978 9.71 6.427 10 8 10s3.022-.289 4.096-.777A5 5 0 0 0 13 8.698m0 3V13c0 .374-.356.875-1.318 1.313C10.766 14.729 9.464 15 8 15s-2.766-.27-3.682-.687C3.356 13.875 3 13.373 3 13v-1.302c.271.202.58.378.904.525C4.978 12.71 6.427 13 8 13s3.022-.289 4.096-.777c.324-.147.633-.323.904-.525"/></svg>`,
    title: 'Bases de datos y lógica',
    description: 'Diseño y optimizo esquemas SQL y consultas complejas, garantizando rendimiento y eficiencia.'
  },
  {
    color: '#F97316',
    icon: `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor" viewBox="0 0 16 16"><path d="M7 14s-1 0-1-1 1-4 5-4 5 3 5 4-1 1-1 1zm4-6a3 3 0 1 0 0-6 3 3 0 0 0 0 6m-5.784 6A2.24 2.24 0 0 1 5 13c0-1.355.68-2.75 1.936-3.72A6.3 6.3 0 0 0 5 9c-4 0-5 3-5 4s1 1 1 1zM4.5 8a2.5 2.5 0 1 0 0-5 2.5 2.5 0 0 0 0 5"/></svg>`,
    title: 'Trabajo en equipo',
    description: 'Colaboro con equipos ágiles, comunicación clara y código limpio para lograr mejores resultados.'
  }
])
</script>

<style scoped>
.value-section {
  background-color: #FFFFFF;
  padding: 100px 0;
  text-align: center;
}

.section-label {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
  margin-bottom: 20px;
}
.section-label .line {
  width: 40px;
  height: 1px;
  background: #D8D8D8;
}
.label-badge {
  color: #6B6B6B;
  font-size: 0.8rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 3px;
}

.value-title {
  font-size: clamp(2rem, 5vw, 3rem);
  font-weight: 800;
  color: #111111;
  margin-bottom: 20px;
}

.value-subtitle {
  color: #6B6B6B;
  font-size: 1.05rem;
  max-width: 600px;
  margin: 0 auto 56px;
  line-height: 1.6;
}

.card-custom {
  background-color: #FFFFFF;
  border: 1px solid #EAEAEA;
  border-radius: 16px;
  overflow: hidden;
  text-align: left;
  transition: transform 0.3s, box-shadow 0.3s;
}
.card-custom:hover {
  transform: translateY(-6px);
  box-shadow: 0 16px 32px rgba(0,0,0,0.06);
}

.card-top-bar {
  height: 4px;
  background: var(--accent);
}

.card-body {
  padding: 32px;
}

.icon-box {
  width: 48px;
  height: 48px;
  border-radius: 12px;
  background: color-mix(in srgb, var(--accent) 15%, white);
  color: var(--accent);
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 24px;
}

.card-title {
  font-weight: 700;
  font-size: 1.2rem;
  color: #111111;
  margin-bottom: 12px;
}

.card-text {
  color: #6B6B6B;
  font-size: 0.95rem;
  line-height: 1.6;
  margin-bottom: 24px;
}

.arrow-btn {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  border: none;
  background: color-mix(in srgb, var(--accent) 15%, white);
  color: var(--accent);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: default;
  transition: background 0.3s, color 0.3s;
}
.arrow-btn:hover {
  background: var(--accent);
  color: #fff;
}
</style>