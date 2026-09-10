<template>
  <div>
    <FirstPage />
    <SecondPage />
    <ThirdPage id="lenguajes" title="Lenguajes de programación" :skills="skills.lenguajes" />
    <ThirdPage id="frameworks" title="Frameworks" :skills="skills.frameworks" />
    <ThirdPage id="ias" title="Inteligencia Artificial" :skills="skills.ias" />
    <FourthPage />
    <!-- AQUÍ NO PONGAS NINGÚN FOOTER, YA ESTÁ EN App.vue -->
  </div>
</template>

<script setup>
import FirstPage from '@/components/sections/FirstPage.vue'
import SecondPage from '@/components/sections/SecondPage.vue'
import ThirdPage from '@/components/sections/ThirdPage.vue'
import FourthPage from '@/components/sections/FourthPage.vue'
import { portfolioData } from '@/data/portfolioData.js'
import { onMounted } from 'vue'

const skills = portfolioData.skills

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible')
      }
    })
  }, { threshold: 0.2 })

  document.querySelectorAll('.fade-up').forEach(el => observer.observe(el))
})
</script>