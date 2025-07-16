<template>
  <div 
    ref="cardContainer" 
    class="project-card-3d"
    @mousemove="onMouseMove"
    @mouseleave="onMouseLeave"
    :style="cardStyle"
  >
    <div class="card-content" :style="contentStyle">
      <div class="project-image">
        <img :src="project.image" :alt="project.title" />
        <div class="tech-overlay">
          <div 
            v-for="tech in project.technologies" 
            :key="tech"
            class="tech-badge"
          >
            {{ tech }}
          </div>
        </div>
      </div>
      
      <div class="project-details">
        <h3 class="project-title">{{ project.title }}</h3>
        <p class="project-description">{{ project.description }}</p>
        
        <div class="project-actions">
          <a :href="project.demo" target="_blank" rel="noopener" class="btn btn-demo">
            <span>Ver Demo</span>
            <div class="btn-glow"></div>
          </a>
          <a :href="project.github" target="_blank" rel="noopener" class="btn btn-code">
            <span>Ver Código</span>
            <div class="btn-glow"></div>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const props = defineProps({
  project: {
    type: Object,
    required: true
  }
})

const cardContainer = ref(null)
const rotateX = ref(0)
const rotateY = ref(0)
const translateZ = ref(0)

const cardStyle = computed(() => ({
  transform: `perspective(1000px) rotateX(${rotateX.value}deg) rotateY(${rotateY.value}deg) translateZ(${translateZ.value}px)`,
  transition: 'transform 0.1s ease-out'
}))

const contentStyle = computed(() => ({
  transform: `translateZ(${translateZ.value * 0.5}px)`,
  transition: 'transform 0.1s ease-out'
}))

const onMouseMove = (event) => {
  if (!cardContainer.value) return
  
  const rect = cardContainer.value.getBoundingClientRect()
  const centerX = rect.left + rect.width / 2
  const centerY = rect.top + rect.height / 2
  
  const mouseX = event.clientX - centerX
  const mouseY = event.clientY - centerY
  
  const rotateXValue = (mouseY / rect.height) * -10
  const rotateYValue = (mouseX / rect.width) * 10
  
  rotateX.value = rotateXValue
  rotateY.value = rotateYValue
  translateZ.value = 20
}

const onMouseLeave = () => {
  rotateX.value = 0
  rotateY.value = 0
  translateZ.value = 0
}
</script>

<style scoped>
.project-card-3d {
  background: linear-gradient(145deg, #ffffff, #f0f0f0);
  border-radius: 20px;
  padding: 0;
  box-shadow: 
    0 10px 30px rgba(0, 0, 0, 0.1),
    0 1px 8px rgba(0, 0, 0, 0.2);
  overflow: hidden;
  cursor: pointer;
  position: relative;
  transform-style: preserve-3d;
}

.project-card-3d:hover {
  box-shadow: 
    0 20px 60px rgba(0, 0, 0, 0.15),
    0 5px 20px rgba(0, 0, 0, 0.1);
}

.card-content {
  transform-style: preserve-3d;
}

.project-image {
  position: relative;
  height: 200px;
  overflow: hidden;
  border-radius: 20px 20px 0 0;
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.project-card-3d:hover .project-image img {
  transform: scale(1.1);
}

.tech-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(45deg, rgba(102, 126, 234, 0.8), rgba(118, 75, 162, 0.8));
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  gap: 0.5rem;
  padding: 1rem;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.project-card-3d:hover .tech-overlay {
  opacity: 1;
}

.tech-badge {
  background: rgba(255, 255, 255, 0.9);
  color: #333;
  padding: 0.3rem 0.8rem;
  border-radius: 15px;
  font-size: 0.8rem;
  font-weight: 600;
  transform: translateY(10px);
  animation: slideInTech 0.3s ease forwards;
}

.tech-badge:nth-child(2) { animation-delay: 0.1s; }
.tech-badge:nth-child(3) { animation-delay: 0.2s; }
.tech-badge:nth-child(4) { animation-delay: 0.3s; }
.tech-badge:nth-child(5) { animation-delay: 0.4s; }

@keyframes slideInTech {
  to {
    transform: translateY(0);
  }
}

.project-details {
  padding: 1.5rem;
  transform: translateZ(20px);
}

.project-title {
  font-size: 1.3rem;
  font-weight: 700;
  color: #2d3748;
  margin-bottom: 0.8rem;
}

.project-description {
  color: #4a5568;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.project-actions {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.btn {
  position: relative;
  padding: 0.8rem 1.5rem;
  border: none;
  border-radius: 25px;
  text-decoration: none;
  font-weight: 600;
  cursor: pointer;
  overflow: hidden;
  transition: all 0.3s ease;
  transform: translateZ(10px);
}

.btn span {
  position: relative;
  z-index: 2;
}

.btn-glow {
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
  transition: left 0.5s ease;
}

.btn:hover .btn-glow {
  left: 100%;
}

.btn-demo {
  background: linear-gradient(45deg, #667eea, #764ba2);
  color: white;
}

.btn-demo:hover {
  transform: translateZ(15px) translateY(-2px);
  box-shadow: 0 10px 25px rgba(102, 126, 234, 0.4);
}

.btn-code {
  background: linear-gradient(45deg, #ffd700, #ffed4e);
  color: #333;
}

.btn-code:hover {
  transform: translateZ(15px) translateY(-2px);
  box-shadow: 0 10px 25px rgba(255, 215, 0, 0.4);
}

@media (max-width: 768px) {
  .project-actions {
    flex-direction: column;
  }
  
  .btn {
    text-align: center;
  }
}
</style>
