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
                <a href="mailto:erich.gomez.aguilera@gmail.com" class="contact-link">
                  erich.gomez.aguilera@gmail.com
                </a>
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
                <a href="tel:+56912345678" class="contact-link">
                  +56 9 1234 5678
                </a>
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
                <p>Chile</p>
              </div>
            </div>
          </div>
          
          <div class="social-links">
            <h4>Sígueme en:</h4>
            <div class="social-icons">
              <a href="https://github.com/erizhi1" class="social-link" target="_blank" rel="noopener">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                  <path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path>
                </svg>
                <span>GitHub</span>
              </a>
              <a href="https://linkedin.com/in/erich-gomez-aguilera" class="social-link" target="_blank" rel="noopener">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                  <path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path>
                  <rect x="2" y="9" width="4" height="12"></rect>
                  <circle cx="4" cy="4" r="2"></circle>
                </svg>
                <span>LinkedIn</span>
              </a>
              <a href="https://twitter.com/erik_zhindon" class="social-link" target="_blank" rel="noopener">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                  <path d="M23 3a10.9 10.9 0 0 1-3.14 1.53 4.48 4.48 0 0 0-7.86 3v1A10.66 10.66 0 0 1 3 4s-4 9 5 13a11.64 11.64 0 0 1-7 2c9 5 20 0 20-11.5a4.5 4.5 0 0 0-.08-.83A7.72 7.72 0 0 0 23 3z"></path>
                </svg>
                <span>Twitter</span>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// No necesitamos JavaScript para esta versión simplificada
</script>

<style scoped>
.contact {
  padding: 6rem 0;
  background: linear-gradient(135deg, #1a1a2e 0%, #0f0f23 100%);
  color: white;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.section-title {
  text-align: center;
  font-size: 3rem;
  color: #ffffff;
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
  display: flex;
  justify-content: center;
}

.contact-info {
  max-width: 600px;
  text-align: center;
}

.contact-info h3 {
  font-size: 2rem;
  color: #2d3748;
  margin-bottom: 1rem;
}

.contact-info > p {
  font-size: 1.1rem;
  color: #4a5568;
  margin-bottom: 3rem;
  line-height: 1.6;
}

.contact-methods {
  display: grid;
  gap: 2rem;
  margin-bottom: 3rem;
}

.contact-method {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1.5rem;
  background: white;
  border-radius: 15px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.contact-method:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
}

.method-icon {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: linear-gradient(135deg, #667eea, #764ba2);
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  flex-shrink: 0;
}

.method-info {
  text-align: left;
  flex-grow: 1;
}

.method-info h4 {
  font-size: 1.2rem;
  color: #2d3748;
  margin-bottom: 0.5rem;
}

.method-info p {
  color: #4a5568;
  margin: 0;
}

.contact-link {
  color: #667eea;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}

.contact-link:hover {
  color: #764ba2;
}

.social-links {
  margin-top: 2rem;
}

.social-links h4 {
  font-size: 1.3rem;
  color: #2d3748;
  margin-bottom: 1rem;
}

.social-icons {
  display: flex;
  justify-content: center;
  gap: 1rem;
}

.social-link {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.8rem 1.5rem;
  background: white;
  color: #4a5568;
  text-decoration: none;
  border-radius: 50px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
  font-weight: 500;
}

.social-link:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15);
  background: linear-gradient(135deg, #667eea, #764ba2);
  color: white;
}

.social-link svg {
  width: 20px;
  height: 20px;
}

@media (max-width: 768px) {
  .contact {
    padding: 4rem 0;
  }
  
  .container {
    padding: 0 1rem;
  }
  
  .section-title {
    font-size: 2.5rem;
  }
  
  .section-subtitle {
    font-size: 1.1rem;
    margin-bottom: 3rem;
  }
  
  .contact-info h3 {
    font-size: 1.8rem;
  }
  
  .contact-method {
    padding: 1rem;
  }
  
  .method-icon {
    width: 40px;
    height: 40px;
  }
  
  .social-icons {
    flex-direction: column;
    align-items: center;
  }
  
  .social-link {
    width: 200px;
    justify-content: center;
  }
}
</style>