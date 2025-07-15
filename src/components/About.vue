<template>
  <section id="about" class="about">
    <div class="container">
      <h2 class="section-title">Sobre Mí</h2>
      
      <div class="about-content">
        <div class="about-text">
          <div class="intro">
            <h3>¡Hola! Soy un desarrollador apasionado por crear soluciones digitales</h3>
            <p>
              Con más de 3 años de experiencia en desarrollo web, me especializo en crear 
              aplicaciones modernas y funcionales utilizando las últimas tecnologías.
            </p>
          </div>
          
          <div class="skills-section">
            <h4>Mis Habilidades</h4>
            <div class="skills-grid">
              <div class="skill-category">
                <h5>Frontend</h5>
                <div class="skills">
                  <span class="skill">Vue.js</span>
                  <span class="skill">React</span>
                  <span class="skill">JavaScript</span>
                  <span class="skill">TypeScript</span>
                  <span class="skill">CSS3</span>
                  <span class="skill">SASS</span>
                </div>
              </div>
              
              <div class="skill-category">
                <h5>Backend</h5>
                <div class="skills">
                  <span class="skill">Node.js</span>
                  <span class="skill">Express</span>
                  <span class="skill">Python</span>
                  <span class="skill">MongoDB</span>
                  <span class="skill">PostgreSQL</span>
                  <span class="skill">API REST</span>
                </div>
              </div>
              
              <div class="skill-category">
                <h5>Herramientas</h5>
                <div class="skills">
                  <span class="skill">Git</span>
                  <span class="skill">Docker</span>
                  <span class="skill">Vite</span>
                  <span class="skill">Webpack</span>
                  <span class="skill">Figma</span>
                  <span class="skill">VS Code</span>
                </div>
              </div>
            </div>
          </div>
        </div>
        
        <div class="about-stats">
          <div class="stat-card">
            <div class="stat-number">50+</div>
            <div class="stat-label">Proyectos Completados</div>
          </div>
          
          <div class="stat-card">
            <div class="stat-number">3+</div>
            <div class="stat-label">Años de Experiencia</div>
          </div>
          
          <div class="stat-card">
            <div class="stat-number">20+</div>
            <div class="stat-label">Clientes Satisfechos</div>
          </div>
          
          <div class="stat-card">
            <div class="stat-number">100%</div>
            <div class="stat-label">Dedicación</div>
          </div>
        </div>
      </div>
      
      <div class="philosophy">
        <h4>Mi Filosofía</h4>
        <p>
          Creo que la tecnología debe servir a las personas, no al revés. 
          Mi enfoque se centra en crear soluciones que sean no solo técnicamente 
          sólidas, sino también intuitivas y accesibles para todos los usuarios.
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
// No se necesita lógica adicional para este componente
</script>

<style scoped>
.about {
  padding: 6rem 0;
  background: #f8fafc;
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
  margin-bottom: 3rem;
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

.about-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 4rem;
  margin-bottom: 4rem;
}

.intro h3 {
  font-size: 1.5rem;
  color: #2d3748;
  margin-bottom: 1rem;
}

.intro p {
  font-size: 1.1rem;
  color: #4a5568;
  line-height: 1.6;
  margin-bottom: 2rem;
}

.skills-section h4 {
  font-size: 1.3rem;
  color: #2d3748;
  margin-bottom: 1.5rem;
}

.skills-grid {
  display: grid;
  gap: 2rem;
}

.skill-category h5 {
  font-size: 1.1rem;
  color: #4a5568;
  margin-bottom: 1rem;
  font-weight: 600;
}

.skills {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.skill {
  background: linear-gradient(135deg, #667eea, #764ba2);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.9rem;
  font-weight: 500;
  transition: transform 0.3s ease;
}

.skill:hover {
  transform: translateY(-2px);
}

.about-stats {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1.5rem;
}

.stat-card {
  background: white;
  padding: 2rem;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.stat-card:hover {
  transform: translateY(-5px);
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 700;
  background: linear-gradient(135deg, #667eea, #764ba2);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.stat-label {
  color: #4a5568;
  font-weight: 500;
  margin-top: 0.5rem;
}

.philosophy {
  background: white;
  padding: 3rem;
  border-radius: 20px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.philosophy h4 {
  font-size: 1.5rem;
  color: #2d3748;
  margin-bottom: 1.5rem;
}

.philosophy p {
  font-size: 1.1rem;
  color: #4a5568;
  line-height: 1.6;
  max-width: 800px;
  margin: 0 auto;
}

@media (max-width: 768px) {
  .about {
    padding: 4rem 0;
  }
  
  .section-title {
    font-size: 2.5rem;
  }
  
  .about-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .skills-grid {
    grid-template-columns: 1fr;
  }
  
  .philosophy {
    padding: 2rem;
  }
  
  .philosophy h4 {
    font-size: 1.3rem;
  }
  
  .philosophy p {
    font-size: 1rem;
  }
}
</style>
