<template>
  <section id="projects" class="projects">
    <div class="container">
      <h2 class="section-title">Mis Proyectos</h2>
      <p class="section-subtitle">
        Algunos de los proyectos en los que he trabajado recientemente
      </p>
      
      <div class="projects-filter">
        <button 
          v-for="category in categories" 
          :key="category"
          :class="['filter-btn', { active: activeFilter === category }]"
          @click="filterProjects(category)"
        >
          {{ category }}
        </button>
      </div>
      
      <div class="projects-grid">
        <div 
          v-for="project in filteredProjects" 
          :key="project.id"
          class="project-card"
          @click="openProject(project)"
        >
          <div class="project-image">
            <img :src="project.image" :alt="project.title" />
            <div class="project-overlay">
              <div class="project-links">
                <button class="link-btn" @click.stop="openDemo(project.demo)">
                  <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                    <polyline points="15,3 21,3 21,9"></polyline>
                    <line x1="10" y1="14" x2="21" y2="3"></line>
                  </svg>
                  Demo
                </button>
                <button class="link-btn" @click.stop="openCode(project.github)">
                  <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                    <path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path>
                  </svg>
                  Código
                </button>
              </div>
            </div>
          </div>
          
          <div class="project-content">
            <h3 class="project-title">{{ project.title }}</h3>
            <p class="project-description">{{ project.description }}</p>
            
            <div class="project-tech">
              <span 
                v-for="tech in project.technologies" 
                :key="tech"
                class="tech-tag"
              >
                {{ tech }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'

const activeFilter = ref('Todos')

const categories = ['Todos', 'Web Apps', 'E-commerce', 'Landing Pages', 'APIs']

const projects = ref([
  {
    id: 1,
    title: 'E-commerce Moderno',
    description: 'Plataforma completa de comercio electrónico con carrito de compras, pagos y gestión de inventario.',
    image: 'https://picsum.photos/400/300?random=1',
    technologies: ['Vue.js', 'Node.js', 'MongoDB', 'Stripe'],
    category: 'E-commerce',
    demo: 'https://demo-ecommerce.com',
    github: 'https://github.com/usuario/ecommerce'
  },
  {
    id: 2,
    title: 'Dashboard Analytics',
    description: 'Panel de control con métricas en tiempo real, gráficos interactivos y reportes automatizados.',
    image: 'https://picsum.photos/400/300?random=2',
    technologies: ['React', 'D3.js', 'Express', 'PostgreSQL'],
    category: 'Web Apps',
    demo: 'https://demo-dashboard.com',
    github: 'https://github.com/usuario/dashboard'
  },
  {
    id: 3,
    title: 'Landing Page Creativa',
    description: 'Sitio web promocional con animaciones CSS, diseño responsivo y optimización SEO.',
    image: 'https://picsum.photos/400/300?random=3',
    technologies: ['HTML5', 'CSS3', 'JavaScript', 'GSAP'],
    category: 'Landing Pages',
    demo: 'https://demo-landing.com',
    github: 'https://github.com/usuario/landing'
  },
  {
    id: 4,
    title: 'API REST Completa',
    description: 'API robusta con autenticación JWT, documentación Swagger y tests automatizados.',
    image: 'https://picsum.photos/400/300?random=4',
    technologies: ['Node.js', 'Express', 'JWT', 'Swagger'],
    category: 'APIs',
    demo: 'https://api-demo.com/docs',
    github: 'https://github.com/usuario/api'
  },
  {
    id: 5,
    title: 'App de Gestión de Tareas',
    description: 'Aplicación web para gestión de proyectos con colaboración en tiempo real y notificaciones.',
    image: 'https://picsum.photos/400/300?random=5',
    technologies: ['Vue.js', 'Socket.io', 'Firebase', 'Vuetify'],
    category: 'Web Apps',
    demo: 'https://demo-tasks.com',
    github: 'https://github.com/usuario/tasks'
  },
  {
    id: 6,
    title: 'Tienda de Ropa Online',
    description: 'E-commerce especializado en moda con filtros avanzados, wishlist y recomendaciones.',
    image: 'https://picsum.photos/400/300?random=6',
    technologies: ['Next.js', 'Prisma', 'Stripe', 'TailwindCSS'],
    category: 'E-commerce',
    demo: 'https://demo-fashion.com',
    github: 'https://github.com/usuario/fashion'
  }
])

const filteredProjects = computed(() => {
  if (activeFilter.value === 'Todos') {
    return projects.value
  }
  return projects.value.filter(project => project.category === activeFilter.value)
})

const filterProjects = (category) => {
  activeFilter.value = category
}

const openProject = (project) => {
  // Aquí podrías abrir un modal con más detalles del proyecto
  console.log('Abriendo proyecto:', project.title)
}

const openDemo = (url) => {
  window.open(url, '_blank')
}

const openCode = (url) => {
  window.open(url, '_blank')
}
</script>

<style scoped>
.projects {
  padding: 6rem 0;
  background: white;
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
  margin-bottom: 3rem;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.projects-filter {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-bottom: 3rem;
  flex-wrap: wrap;
}

.filter-btn {
  padding: 0.8rem 1.5rem;
  border: 2px solid #e2e8f0;
  background: white;
  color: #4a5568;
  border-radius: 25px;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.3s ease;
}

.filter-btn:hover,
.filter-btn.active {
  background: linear-gradient(135deg, #667eea, #764ba2);
  color: white;
  border-color: transparent;
  transform: translateY(-2px);
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
}

.project-card {
  background: white;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
  cursor: pointer;
}

.project-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

.project-image {
  position: relative;
  height: 200px;
  overflow: hidden;
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.project-card:hover .project-image img {
  transform: scale(1.1);
}

.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(102, 126, 234, 0.9);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.project-links {
  display: flex;
  gap: 1rem;
}

.link-btn {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.8rem 1.5rem;
  background: white;
  color: #667eea;
  border: none;
  border-radius: 25px;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
}

.link-btn:hover {
  background: #667eea;
  color: white;
  transform: translateY(-2px);
}

.project-content {
  padding: 2rem;
}

.project-title {
  font-size: 1.5rem;
  color: #2d3748;
  margin-bottom: 1rem;
  font-weight: 600;
}

.project-description {
  color: #4a5568;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tech-tag {
  background: #f7fafc;
  color: #4a5568;
  padding: 0.5rem 1rem;
  border-radius: 15px;
  font-size: 0.9rem;
  font-weight: 500;
  border: 1px solid #e2e8f0;
}

@media (max-width: 768px) {
  .projects {
    padding: 4rem 0;
  }
  
  .section-title {
    font-size: 2.5rem;
  }
  
  .projects-grid {
    grid-template-columns: 1fr;
  }
  
  .project-content {
    padding: 1.5rem;
  }
  
  .projects-filter {
    gap: 0.5rem;
  }
  
  .filter-btn {
    padding: 0.6rem 1rem;
    font-size: 0.9rem;
  }
}
</style>
