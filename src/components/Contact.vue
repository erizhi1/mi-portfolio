<template>
  <section id="contact" class="contact">
    <div class="container">
      <h2 class="section-title">Contacto</h2>
      <p class="section-subtitle">
        ¿Tienes un proyecto en mente? ¡Hablemos!
      </p>
      
      <div class="contact-content">
        <div class="contact-info">
          <h3>¡Conectemos!</h3>
          <p>
            Estoy siempre abierto a discutir nuevas oportunidades, 
            proyectos interesantes o simplemente tomar un café virtual.
          </p>
          
          <div class="contact-methods">
            <div class="contact-method">
              <div class="method-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                  <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
                  <polyline points="22,6 12,13 2,6"></polyline>
                </svg>
              </div>
              <div class="method-info">
                <h4>Email</h4>
                <p>tu.email@ejemplo.com</p>
              </div>
            </div>
            
            <div class="contact-method">
              <div class="method-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                  <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"></path>
                </svg>
              </div>
              <div class="method-info">
                <h4>Teléfono</h4>
                <p>+1 (555) 123-4567</p>
              </div>
            </div>
            
            <div class="contact-method">
              <div class="method-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                  <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
                  <circle cx="12" cy="10" r="3"></circle>
                </svg>
              </div>
              <div class="method-info">
                <h4>Ubicación</h4>
                <p>Ciudad, País</p>
              </div>
            </div>
          </div>
          
          <div class="social-links">
            <h4>Sígueme en:</h4>
            <div class="social-icons">
              <a href="#" class="social-link">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                  <path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path>
                </svg>
              </a>
              <a href="#" class="social-link">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                  <path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path>
                  <rect x="2" y="9" width="4" height="12"></rect>
                  <circle cx="4" cy="4" r="2"></circle>
                </svg>
              </a>
              <a href="#" class="social-link">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                  <path d="M23 3a10.9 10.9 0 0 1-3.14 1.53 4.48 4.48 0 0 0-7.86 3v1A10.66 10.66 0 0 1 3 4s-4 9 5 13a11.64 11.64 0 0 1-7 2c9 5 20 0 20-11.5a4.5 4.5 0 0 0-.08-.83A7.72 7.72 0 0 0 23 3z"></path>
                </svg>
              </a>
            </div>
          </div>
        </div>
        
        <form @submit.prevent="submitForm" class="contact-form">
          <div class="form-group">
            <label for="name">Nombre Completo</label>
            <input 
              type="text" 
              id="name" 
              v-model="form.name" 
              required
              :class="{ error: errors.name }"
            />
            <span v-if="errors.name" class="error-message">{{ errors.name }}</span>
          </div>
          
          <div class="form-group">
            <label for="email">Email</label>
            <input 
              type="email" 
              id="email" 
              v-model="form.email" 
              required
              :class="{ error: errors.email }"
            />
            <span v-if="errors.email" class="error-message">{{ errors.email }}</span>
          </div>
          
          <div class="form-group">
            <label for="subject">Asunto</label>
            <input 
              type="text" 
              id="subject" 
              v-model="form.subject" 
              required
              :class="{ error: errors.subject }"
            />
            <span v-if="errors.subject" class="error-message">{{ errors.subject }}</span>
          </div>
          
          <div class="form-group">
            <label for="message">Mensaje</label>
            <textarea 
              id="message" 
              v-model="form.message" 
              rows="5" 
              required
              :class="{ error: errors.message }"
            ></textarea>
            <span v-if="errors.message" class="error-message">{{ errors.message }}</span>
          </div>
          
          <button type="submit" class="submit-btn" :disabled="isSubmitting">
            <span v-if="!isSubmitting">Enviar Mensaje</span>
            <span v-else>Enviando...</span>
          </button>
          
          <div v-if="successMessage" class="success-message">
            {{ successMessage }}
          </div>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, reactive } from 'vue'

const form = reactive({
  name: '',
  email: '',
  subject: '',
  message: ''
})

const errors = ref({})
const isSubmitting = ref(false)
const successMessage = ref('')

const validateForm = () => {
  errors.value = {}
  
  if (!form.name.trim()) {
    errors.value.name = 'El nombre es requerido'
  }
  
  if (!form.email.trim()) {
    errors.value.email = 'El email es requerido'
  } else if (!/\S+@\S+\.\S+/.test(form.email)) {
    errors.value.email = 'El email no es válido'
  }
  
  if (!form.subject.trim()) {
    errors.value.subject = 'El asunto es requerido'
  }
  
  if (!form.message.trim()) {
    errors.value.message = 'El mensaje es requerido'
  } else if (form.message.trim().length < 10) {
    errors.value.message = 'El mensaje debe tener al menos 10 caracteres'
  }
  
  return Object.keys(errors.value).length === 0
}

const submitForm = async () => {
  if (!validateForm()) {
    return
  }
  
  isSubmitting.value = true
  
  try {
    // Simular envío del formulario
    await new Promise(resolve => setTimeout(resolve, 2000))
    
    // Aquí iría la lógica real de envío (API, emailjs, etc.)
    console.log('Formulario enviado:', form)
    
    successMessage.value = '¡Mensaje enviado correctamente! Te responderé pronto.'
    
    // Limpiar formulario
    Object.keys(form).forEach(key => {
      form[key] = ''
    })
    
    // Limpiar mensaje de éxito después de 5 segundos
    setTimeout(() => {
      successMessage.value = ''
    }, 5000)
    
  } catch (error) {
    console.error('Error al enviar formulario:', error)
    // Aquí podrías mostrar un mensaje de error
  } finally {
    isSubmitting.value = false
  }
}
</script>

<style scoped>
.contact {
  padding: 6rem 0;
  background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.section-title {
  text-align: center;
  font-size: 3rem;
  color: #2d3748;
  margin-bottom: 1rem;
  position: relative;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 4px;
  background: linear-gradient(90deg, #667eea, #764ba2);
  border-radius: 2px;
}

.section-subtitle {
  text-align: center;
  font-size: 1.2rem;
  color: #4a5568;
  margin-bottom: 4rem;
}

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
}

.contact-info h3 {
  font-size: 2rem;
  color: #2d3748;
  margin-bottom: 1rem;
}

.contact-info > p {
  font-size: 1.1rem;
  color: #4a5568;
  line-height: 1.6;
  margin-bottom: 2rem;
}

.contact-methods {
  margin-bottom: 3rem;
}

.contact-method {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1.5rem;
  padding: 1rem;
  background: white;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.method-icon {
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, #667eea, #764ba2);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
}

.method-info h4 {
  font-size: 1.1rem;
  color: #2d3748;
  margin-bottom: 0.25rem;
}

.method-info p {
  color: #4a5568;
}

.social-links h4 {
  font-size: 1.2rem;
  color: #2d3748;
  margin-bottom: 1rem;
}

.social-icons {
  display: flex;
  gap: 1rem;
}

.social-link {
  width: 50px;
  height: 50px;
  background: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #4a5568;
  text-decoration: none;
  transition: all 0.3s ease;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.social-link:hover {
  background: linear-gradient(135deg, #667eea, #764ba2);
  color: white;
  transform: translateY(-3px);
}

.contact-form {
  background: white;
  padding: 3rem;
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group label {
  display: block;
  font-weight: 600;
  color: #2d3748;
  margin-bottom: 0.5rem;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 1rem;
  border: 2px solid #e2e8f0;
  border-radius: 10px;
  font-size: 1rem;
  transition: border-color 0.3s ease;
  background: #f8fafc;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #667eea;
  background: white;
}

.form-group input.error,
.form-group textarea.error {
  border-color: #e53e3e;
}

.error-message {
  color: #e53e3e;
  font-size: 0.9rem;
  margin-top: 0.25rem;
  display: block;
}

.submit-btn {
  width: 100%;
  padding: 1rem 2rem;
  background: linear-gradient(135deg, #667eea, #764ba2);
  color: white;
  border: none;
  border-radius: 10px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
}

.submit-btn:hover:not(:disabled) {
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(102, 126, 234, 0.3);
}

.submit-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.success-message {
  background: #48bb78;
  color: white;
  padding: 1rem;
  border-radius: 10px;
  margin-top: 1rem;
  text-align: center;
}

@media (max-width: 768px) {
  .contact {
    padding: 4rem 0;
  }
  
  .section-title {
    font-size: 2.5rem;
  }
  
  .contact-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .contact-form {
    padding: 2rem;
  }
  
  .contact-method {
    flex-direction: column;
    text-align: center;
  }
}
</style>
