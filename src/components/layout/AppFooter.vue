<template>
  <footer class="footer">
    <div class="container footer-row">
      <div class="footer-left">
        <span class="text-ink">BRYAN.</span>
        <span class="divider">|</span>
        <span class="text-muted-custom">Tecnología y código con criterio — Desde Vitoria-Gasteiz.</span>
      </div>
      <div class="footer-right text-muted-custom">
        Portfolio
        <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" fill="currentColor" class="bi bi-c-circle" viewBox="0 0 16 16">
          <path d="M1 8a7 7 0 1 0 14 0A7 7 0 0 0 1 8m15 0A8 8 0 1 1 0 8a8 8 0 0 1 16 0M8.146 4.992c-1.212 0-1.927.92-1.927 2.502v1.06c0 1.571.703 2.462 1.927 2.462.979 0 1.641-.586 1.729-1.418h1.295v.093c-.1 1.448-1.354 2.467-3.03 2.467-2.091 0-3.269-1.336-3.269-3.603V7.482c0-2.261 1.201-3.638 3.27-3.638 1.681 0 2.935 1.054 3.029 2.572v.088H9.875c-.088-.879-.768-1.512-1.729-1.512"/>
        </svg>
        {{ year }} Bryan Alzamora.
      </div>
    </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue'
const year = ref(new Date().getFullYear())
</script>

<style scoped>
.footer {
  background-color: #FAFAFA !important;
  border-top: 1px solid #EAEAEA;
  padding: 20px 0;
  position: static;
  bottom: 0;
  z-index: 1050;
}

.footer-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 8px;
  font-size: 0.9rem;
}

.footer-left {
  display: flex;
  align-items: center;
  gap: 12px;
  flex-wrap: wrap;
}

.footer-right {
  display: flex;
  align-items: center;
  gap: 6px;
  font-size: 0.85rem;
}

.text-ink {
  color: #111111;
  font-weight: 700;
  letter-spacing: 0.3px;
}
.text-muted-custom {
  color: #6B6B6B;
}
.divider {
  color: #D8D8D8;
  font-weight: 300;
}

@media (min-width: 992px) {
  .footer {
    position: sticky;
    bottom: 0;
  }
}
</style>