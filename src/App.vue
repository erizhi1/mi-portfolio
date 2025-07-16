<script setup>
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'
</script>

<template>
  <div id="app">
    <!-- Navegación -->
    <nav class="navbar">
      <div class="nav-container">
        <div class="nav-logo">
          <span>Erich</span>
        </div>
        <ul class="nav-menu">
          <li><a href="#hero" @click="scrollToSection('hero')">Inicio</a></li>
          <li><a href="#about" @click="scrollToSection('about')">Sobre Mí</a></li>
          <li><a href="#projects" @click="scrollToSection('projects')">Proyectos</a></li>
          <li><a href="#contact" @click="scrollToSection('contact')">Contacto</a></li>
        </ul>
        <div class="nav-toggle" @click="toggleMenu">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>
    </nav>

    <!-- Contenido principal -->
    <main>
      <section id="hero">
        <Hero />
      </section>
      
      <section id="about">
        <About />
      </section>
      
      <section id="projects">
        <Projects />
      </section>
      
      <section id="contact">
        <Contact />
      </section>
    </main>

    <!-- Footer -->
    <footer class="footer">
      <div class="footer-container">
        <p>&copy; 2025 Mi Portfolio. Hecho con ❤️ y Vue.js</p>
        <div class="footer-links">
          <a href="#" class="footer-link">Política de Privacidad</a>
          <a href="#" class="footer-link">Términos de Uso</a>
        </div>
      </div>
    </footer>
  </div>
</template>

<style scoped>
/* Reset y estilos base */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
  line-height: 1.6;
  color: #2d3748;
}

/* Navegación */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(0, 0, 0, 0.1);
  z-index: 1000;
  transition: all 0.3s ease;
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 1rem 2rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.nav-logo span {
  font-size: 1.5rem;
  font-weight: 700;
  background: linear-gradient(135deg, #667eea, #764ba2);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.nav-menu {
  display: flex;
  list-style: none;
  gap: 2rem;
}

.nav-menu a {
  text-decoration: none;
  color: #4a5568;
  font-weight: 500;
  transition: color 0.3s ease;
  cursor: pointer;
}

.nav-menu a:hover {
  color: #667eea;
}

.nav-toggle {
  display: none;
  flex-direction: column;
  cursor: pointer;
  gap: 4px;
}

.nav-toggle span {
  width: 25px;
  height: 3px;
  background: #4a5568;
  transition: all 0.3s ease;
}

/* Contenido principal */
main {
  padding-top: 80px; /* Espacio para navbar fija */
}

/* Footer */
.footer {
  background: #2d3748;
  color: white;
  padding: 2rem 0;
  text-align: center;
}

.footer-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
}

.footer-links {
  display: flex;
  gap: 2rem;
}

.footer-link {
  color: #a0aec0;
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-link:hover {
  color: white;
}

/* Scroll suave */
html {
  scroll-behavior: smooth;
}

/* Responsive */
@media (max-width: 768px) {
  .nav-menu {
    position: fixed;
    top: 80px;
    left: -100%;
    width: 100%;
    height: calc(100vh - 80px);
    background: white;
    flex-direction: column;
    align-items: center;
    justify-content: start;
    padding-top: 2rem;
    transition: left 0.3s ease;
  }

  .nav-menu.active {
    left: 0;
  }

  .nav-toggle {
    display: flex;
  }

  .footer-container {
    flex-direction: column;
    text-align: center;
  }

  .footer-links {
    justify-content: center;
  }
}

/* Animaciones de entrada */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Utilidades */
.section {
  padding: 6rem 0;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}
</style>

<script>
export default {
  methods: {
    scrollToSection(sectionId) {
      const element = document.getElementById(sectionId);
      if (element) {
        const navHeight = 80;
        const elementPosition = element.offsetTop - navHeight;
        window.scrollTo({
          top: elementPosition,
          behavior: 'smooth'
        });
      }
    },
    
    toggleMenu() {
      const navMenu = document.querySelector('.nav-menu');
      navMenu.classList.toggle('active');
    }
  },
  
  mounted() {
    // Cerrar menú móvil al hacer click en un enlace
    const navLinks = document.querySelectorAll('.nav-menu a');
    navLinks.forEach(link => {
      link.addEventListener('click', () => {
        const navMenu = document.querySelector('.nav-menu');
        navMenu.classList.remove('active');
      });
    });
    
    // Cambiar estilo de navbar al hacer scroll
    window.addEventListener('scroll', () => {
      const navbar = document.querySelector('.navbar');
      if (window.scrollY > 50) {
        navbar.style.background = 'rgba(255, 255, 255, 0.98)';
        navbar.style.boxShadow = '0 2px 20px rgba(0, 0, 0, 0.1)';
      } else {
        navbar.style.background = 'rgba(255, 255, 255, 0.95)';
        navbar.style.boxShadow = 'none';
      }
    });
  }
}
</script>
