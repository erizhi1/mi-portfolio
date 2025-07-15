<template>
  <section class="hero">
    <div class="hero-container">
      <div class="hero-content">
        <h1 class="hero-title">
          Hola, soy <span class="highlight">Tu Nombre</span>
        </h1>
        <p class="hero-subtitle">
          Desarrollador Full Stack especializado en Vue.js y tecnologías modernas
        </p>
        <p class="hero-description">
          Creo experiencias web únicas y funcionales que conectan personas con tecnología
        </p>
        <div class="hero-buttons">
          <button class="btn btn-primary" @click="scrollToSection('projects')">
            Ver Proyectos
          </button>
          <button class="btn btn-secondary" @click="scrollToSection('contact')">
            Contactar
          </button>
        </div>
      </div>
      <div class="hero-image">
        <div class="avatar">
          <img src="../assets/logo.svg" alt="Avatar" class="avatar-img" />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId);
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' });
  }
}
</script>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding: 2rem 0;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
}

.hero-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.hero-content {
  animation: slideInLeft 1s ease-out;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
  line-height: 1.2;
}

.highlight {
  color: #ffd700;
  position: relative;
}

.hero-subtitle {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  opacity: 0.9;
}

.hero-description {
  font-size: 1.1rem;
  margin-bottom: 2rem;
  opacity: 0.8;
  line-height: 1.6;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.btn {
  padding: 1rem 2rem;
  border: none;
  border-radius: 50px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  text-decoration: none;
  display: inline-block;
}

.btn-primary {
  background: #ffd700;
  color: #333;
}

.btn-primary:hover {
  background: #ffed4e;
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(255, 215, 0, 0.3);
}

.btn-secondary {
  background: transparent;
  color: white;
  border: 2px solid white;
}

.btn-secondary:hover {
  background: white;
  color: #333;
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(255, 255, 255, 0.3);
}

.hero-image {
  display: flex;
  justify-content: center;
  animation: slideInRight 1s ease-out;
}

.avatar {
  width: 300px;
  height: 300px;
  border-radius: 50%;
  background: linear-gradient(45deg, #ffd700, #ffed4e);
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  position: relative;
  overflow: hidden;
}

.avatar-img {
  width: 80%;
  height: 80%;
  object-fit: cover;
  border-radius: 50%;
}

@keyframes slideInLeft {
  from {
    opacity: 0;
    transform: translateX(-50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes slideInRight {
  from {
    opacity: 0;
    transform: translateX(50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@media (max-width: 768px) {
  .hero-container {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 2rem;
  }
  
  .hero-title {
    font-size: 2.5rem;
  }
  
  .hero-subtitle {
    font-size: 1.2rem;
  }
  
  .avatar {
    width: 200px;
    height: 200px;
  }
  
  .hero-buttons {
    justify-content: center;
  }
}
</style>
