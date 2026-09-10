<template>
  <section :id="id" class="skills-section fade-up">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-lg-9">

          <div class="section-mark"></div>
          <h2 class="skills-title">{{ title }}</h2>

          <div class="skills-list">
            <div v-for="skill in skills" :key="skill.nombre" class="skill-row">
              <div class="skill-info">
                <span class="skill-name">{{ skill.nombre }}</span>
                <div class="progress">
                  <div
                    class="progress-bar"
                    role="progressbar"
                    :style="{ width: skill.nivel + '%' }"
                    :aria-valuenow="skill.nivel"
                    aria-valuemin="0"
                    aria-valuemax="100"
                  ></div>
                </div>
              </div>
              <span class="skill-percent">{{ skill.nivel }}%</span>
            </div>
          </div>

        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
defineProps({
  id: String,
  title: String,
  skills: Array
})
</script>

<style scoped>
.skills-section {
  background-color: #FAFAFA;
  padding: 100px 0;
}
.skills-section:nth-child(even) {
  background-color: #FFFFFF;
  border-top: 1px solid #EAEAEA;
  border-bottom: 1px solid #EAEAEA;
}

.section-mark {
  width: 40px;
  height: 3px;
  background: #6C4CF1;
  border-radius: 2px;
  margin-bottom: 24px;
}

.skills-title {
  font-weight: 500;
  font-size: clamp(1.8rem, 4vw, 2.6rem);
  color: #111111;
  margin-bottom: 56px;
}

.skills-list {
  display: flex;
  flex-direction: column;
  gap: 32px;
}

.skill-row {
  display: flex;
  align-items: center;
  gap: 24px;
}

.skill-info {
  flex: 1;
}

.skill-name {
  display: block;
  color: #111111;
  font-weight: 500;
  font-size: 1.05rem;
  margin-bottom: 10px;
}

.progress {
  height: 4px !important;
  background-color: #EAEAEA !important;
  border-radius: 2px;
}
.progress-bar {
  background-color: #6C4CF1 !important;
  border-radius: 2px;
}

.skill-percent {
  color: #8B949E;
  font-size: 0.95rem;
  font-weight: 500;
  min-width: 44px;
  text-align: right;
}

@media (max-width: 576px) {
  .skill-row {
    gap: 12px;
  }
  .skill-percent {
    min-width: 36px;
    font-size: 0.85rem;
  }
}
</style>