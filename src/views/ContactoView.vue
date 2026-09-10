<template>
  <div class="contact-page">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-lg-7 text-center">

          <h1 class="contact-title">Hablemos<span class="dot-purple">.</span></h1>
          <p class="contact-subtitle">Cuéntame tu idea y veamos cómo podemos colaborar.</p>

          <form class="contact-form" @submit.prevent="enviarMensaje">
            <div class="row g-4 mb-4">
              <div class="col-md-6 text-start">
                <label class="field-label">Nombre</label>
                <input
                  v-model="form.nombre"
                  type="text"
                  placeholder="Tu nombre"
                  class="field-input"
                  required
                />
              </div>
              <div class="col-md-6 text-start">
                <label class="field-label">Correo</label>
                <input
                  v-model="form.correo"
                  type="email"
                  placeholder="tu@email.com"
                  class="field-input"
                  required
                />
              </div>
            </div>

            <div class="text-start mb-4">
              <label class="field-label">Consulta</label>
              <textarea
                v-model="form.consulta"
                placeholder="Describe brevemente tu proyecto..."
                class="field-input field-textarea"
                rows="2"
                required
              ></textarea>
            </div>

            <button type="submit" class="btn-submit" :disabled="enviando">
                <span v-if="enviando">Enviando...</span>
                <span v-else-if="enviado">✓ ¡Mensaje enviado!</span>
                <span v-else>
                    Enviar Mensaje
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
                    <path d="M15.854.146a.5.5 0 0 1 .11.54l-5.819 14.547a.75.75 0 0 1-1.329.124l-3.178-4.995L.643 7.184a.75.75 0 0 1 .124-1.33L15.314.037a.5.5 0 0 1 .54.11ZM6.636 10.07l2.761 4.338L14.13 2.576zm6.787-8.201L1.591 6.602l4.339 2.76z"/>
                    </svg>
                </span>
            </button>

            <!-- Mensajes de feedback -->
            <p v-if="enviado" class="feedback success">Tu mensaje se ha enviado correctamente. Te responderé lo antes posible.</p>
            <p v-if="error" class="feedback error">{{ error }}</p>
          </form>

          <p class="contact-alt">
            También puedes escribirme a:<br />
            <a :href="'mailto:' + personal.email" class="contact-email">{{ personal.email }}</a>
          </p>

        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue'
import { portfolioData } from '@/data/portfolioData.js'

const personal = portfolioData.personal

// Tu Access Key de Web3Forms
const ACCESS_KEY = '35288bde-2b64-4a76-9928-f5e27838f38a'

const form = reactive({
  nombre: '',
  correo: '',
  consulta: ''
})

const enviando = ref(false)
const enviado = ref(false)
const error = ref('')

const enviarMensaje = async () => {
  enviando.value = true
  error.value = ''

  try {
    const response = await fetch('https://api.web3forms.com/submit', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        'Accept': 'application/json'
      },
      body: JSON.stringify({
        access_key: ACCESS_KEY,
        name: form.nombre,
        email: form.correo,
        message: form.consulta,
        subject: `Nuevo mensaje de ${form.nombre} desde tu portfolio`,
        from_name: 'Portfolio Bryan Alzamora'
      })
    })

    const data = await response.json()

    if (data.success) {
      enviado.value = true
      form.nombre = ''
      form.correo = ''
      form.consulta = ''
      // Ocultar el mensaje de éxito después de 5 segundos
      setTimeout(() => { enviado.value = false }, 5000)
    } else {
      error.value = 'Hubo un problema al enviar el mensaje. Inténtalo de nuevo.'
    }
  } catch (e) {
    error.value = 'Error de conexión. Comprueba tu internet e inténtalo de nuevo.'
  } finally {
    enviando.value = false
  }
}
</script>

<style scoped>
.contact-page {
  background-color: #FAFAFA;
  flex: 1;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 40px 0;
}

.contact-title {
  font-size: clamp(2.5rem, 6vw, 4rem);
  font-weight: 800;
  color: #111111;
  margin-bottom: 12px;
}
.dot-purple {
  color: #6C4CF1;
}

.contact-subtitle {
  color: #6B6B6B;
  font-size: 1.1rem;
  margin-bottom: 56px;
}

.contact-form {
  text-align: left;
}

.field-label {
  display: block;
  font-size: 0.8rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1px;
  color: #111111;
  margin-bottom: 12px;
}

.field-input {
  width: 100%;
  border: none;
  border-bottom: 1px solid #D8D8D8;
  background: transparent;
  padding: 8px 0;
  font-size: 1rem;
  color: #111111;
  transition: border-color 0.3s;
}
.field-input::placeholder {
  color: #C4C4C4;
}
.field-input:focus {
  outline: none;
  border-bottom-color: #6C4CF1;
}

.field-textarea {
  resize: none;
  font-family: inherit;
}

.btn-submit {
  width: 100%;
  background: #111111;
  color: #fff;
  border: none;
  border-radius: 10px;
  padding: 16px;
  font-weight: 700;
  font-size: 1rem;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  transition: background 0.3s;
}
.btn-submit:hover {
  background: #6C4CF1;
}

.contact-alt {
  margin-top: 48px;
  color: #6B6B6B;
  font-size: 0.95rem;
  line-height: 1.8;
}
.contact-email {
  color: #111111;
  font-weight: 700;
  text-decoration: none;
}
.contact-email:hover {
  color: #6C4CF1;
}

.btn-submit:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.feedback {
  margin-top: 20px;
  padding: 12px 16px;
  border-radius: 8px;
  font-size: 0.9rem;
  font-weight: 500;
}
.feedback.success {
  background: #E8F5E9;
  color: #2E7D32;
  border: 1px solid #A5D6A7;
}
.feedback.error {
  background: #FFEBEE;
  color: #C62828;
  border: 1px solid #EF9A9A;
}

@media (max-width: 576px) {
  .contact-page {
    padding: 30px 0;
  }
}
</style>