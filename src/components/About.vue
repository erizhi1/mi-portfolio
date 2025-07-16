<template>
  <section id="about" class="about">
    <div class="container">
      <h2 class="section-title">Sobre Mí</h2>
      
      <div class="a.about {
  padding: 6rem 0;
  background: #f7fafc;
  overflow-x: hidden; /* Previene el desbordamiento horizontal */
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}nt">
        <div class="about-text">
          <div class="intro">
            <h3>¡Hola! Soy Erich, Ingeniero de Software apasionado por el desarrollo backend</h3>
            <p>
              Ingeniero en Informática y Programador por la Universidad Tecnológica de Chile, 
              especializado en desarrollo backend, gestión de bases de datos y resolución de problemas 
              complejos con tecnología. Tengo experiencia en diversos sectores como el área forestal, 
              facturación electrónica y servicio público.
            </p>
          </div>

          <div class="experience-section">
            <h4>Experiencia Destacada</h4>
            <div class="experience-grid">
              <div class="experience-item">
                <div class="experience-icon">🌲</div>
                <h5>Sector Forestal</h5>
                <p>Optimización de procesos y gestión de inventarios</p>
              </div>
              <div class="experience-item">
                <div class="experience-icon">💼</div>
                <h5>Facturación Electrónica</h5>
                <p>Implementación de soluciones robustas para empresas</p>
              </div>
              <div class="experience-item">
                <div class="experience-icon">⚖️</div>
                <h5>Servicio Público</h5>
                <p>Desarrollo para Poder Judicial de Chile y Servicio de Salud Araucanía Sur</p>
              </div>
            </div>
          </div>
          
          <div class="skills-section">
            <h4>Mis Habilidades</h4>
            <div class="skills-grid">
              <div class="skill-category">
                <h5>Backend</h5>
                <div class="skills">
                  <span class="skill">PHP</span>
                  <span class="skill">Laravel</span>
                  <span class="skill">CodeIgniter</span>
                  <span class="skill">Python</span>
                  <span class="skill">API REST</span>
                  <span class="skill">JWT</span>
                </div>
              </div>
              
              <div class="skill-category">
                <h5>Bases de Datos</h5>
                <div class="skills">
                  <span class="skill">MySQL</span>
                  <span class="skill">Oracle</span>
                  <span class="skill">PostgreSQL</span>
                  <span class="skill">SQL</span>
                  <span class="skill">Optimización de Consultas</span>
                  <span class="skill">Modelado de Datos</span>
                </div>
              </div>

              <div class="skill-category">
                <h5>Frontend Complementario</h5>
                <div class="skills">
                  <span class="skill">Vue.js</span>
                  <span class="skill">Bootstrap</span>
                  <span class="skill">jQuery</span>
                  <span class="skill">JavaScript</span>
                  <span class="skill">CSS3</span>
                  <span class="skill">HTML5</span>
                </div>
              </div>
              
              <div class="skill-category">
                <h5>Análisis de Datos</h5>
                <div class="skills">
                  <span class="skill">Pentaho</span>
                  <span class="skill">Power BI</span>
                  <span class="skill">Chart.js</span>
                  <span class="skill">Análisis de Datos</span>
                  <span class="skill">Reporting</span>
                  <span class="skill">KPIs</span>
                </div>
              </div>
              
              <div class="skill-category">
                <h5>Herramientas</h5>
                <div class="skills">
                  <span class="skill">Docker</span>
                  <span class="skill">Git</span>
                  <span class="skill">Composer</span>
                  <span class="skill">Swagger</span>
                  <span class="skill">Postman</span>
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
            <div class="stat-label">Proyectos</div>
          </div>
          
          <div class="stat-card">
            <div class="stat-number">3+</div>
            <div class="stat-label">Años Experiencia</div>
          </div>
          
          <div class="stat-card">
            <div class="stat-number">20+</div>
            <div class="stat-label">Clientes</div>
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
          "La tecnología no solo transforma la manera en que hacemos las cosas, 
          sino también la manera en que pensamos y vivimos." Mi enfoque se centra 
          en crear soluciones backend robustas y sistemas de bases de datos eficientes 
          que soporten el crecimiento y evolución de las organizaciones.
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
  background: linear-gradient(135deg, #0f0f23 0%, #1a1a2e 100%);
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
  color: #ffffff;
  margin-bottom: 1rem;
}

.intro p {
  font-size: 1.1rem;
  color: #e2e8f0;
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
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
  margin: 3rem 0;
}

.stat-card {
  background: white;
  padding: 1.5rem;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
  min-width: 0; /* Permite que el contenido se encoja */
}

.stat-card:hover {
  transform: translateY(-5px);
}

.stat-number {
  font-size: 2.2rem;
  font-weight: 700;
  background: linear-gradient(135deg, #667eea, #764ba2);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 0.5rem;
}

.stat-label {
  color: #4a5568;
  font-weight: 500;
  font-size: 0.95rem;
  line-height: 1.3;
  word-wrap: break-word;
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
  
  .about-stats {
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }
  
  .stat-card {
    padding: 1.2rem;
  }
  
  .stat-number {
    font-size: 1.8rem;
  }
  
  .stat-label {
    font-size: 0.85rem;
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
  
  .experience-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .experience-item {
    padding: 1.5rem;
    text-align: center;
  }
  
  .experience-icon {
    font-size: 2rem;
  }
}

@media (max-width: 480px) {
  .about-stats {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  
  .stat-card {
    padding: 1rem;
  }
  
  .stat-number {
    font-size: 1.6rem;
  }
  
  .stat-label {
    font-size: 0.8rem;
  }
}

/* Estilos para la sección de experiencia */
.experience-section {
  margin-bottom: 3rem;
}

.experience-section h4 {
  font-size: 1.3rem;
  color: #2d3748;
  margin-bottom: 1.5rem;
  text-align: center;
}

.experience-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.experience-item {
  background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
  padding: 2rem;
  border-radius: 15px;
  text-align: center;
  color: white;
  transition: transform 0.3s ease;
}

.experience-item:hover {
  transform: translateY(-5px);
}

.experience-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.experience-item h5 {
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
  font-weight: 600;
}

.experience-item p {
  font-size: 0.95rem;
  opacity: 0.95;
  line-height: 1.4;
}
</style>
