<template>
  <div ref="cubeContainer" class="cube-container"></div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import * as THREE from 'three'

const cubeContainer = ref(null)
let scene, camera, renderer, cube, animationId

onMounted(() => {
  initCube()
  animate()
  window.addEventListener('resize', onCubeResize)
})

onUnmounted(() => {
  if (animationId) {
    cancelAnimationFrame(animationId)
  }
  if (renderer) {
    renderer.dispose()
  }
  window.removeEventListener('resize', onCubeResize)
})

const initCube = () => {
  // Escena
  scene = new THREE.Scene()
  
  // Cámara
  camera = new THREE.PerspectiveCamera(75, 1, 0.1, 1000)
  camera.position.z = 3
  
  // Renderer
  renderer = new THREE.WebGLRenderer({ alpha: true, antialias: true })
  renderer.setSize(300, 300)
  renderer.setClearColor(0x000000, 0)
  cubeContainer.value.appendChild(renderer.domElement)
  
  // Crear cubo con tecnologías
  createTechCube()
  
  // Iluminación
  const ambientLight = new THREE.AmbientLight(0xffffff, 0.6)
  scene.add(ambientLight)
  
  const pointLight = new THREE.PointLight(0xffd700, 1, 100)
  pointLight.position.set(5, 5, 5)
  scene.add(pointLight)
}

const createTechCube = () => {
  // Crear texturas con nombres de tecnologías
  const canvas = document.createElement('canvas')
  canvas.width = 256
  canvas.height = 256
  const context = canvas.getContext('2d')
  
  const technologies = ['PHP', 'Laravel', 'MySQL', 'Oracle', 'PostgreSQL', 'JavaScript']
  const colors = ['#667eea', '#764ba2', '#ffd700', '#f093fb', '#667eea', '#ffbe0b']
  
  const materials = technologies.map((tech, index) => {
    context.fillStyle = colors[index]
    context.fillRect(0, 0, 256, 256)
    
    context.fillStyle = 'white'
    context.font = 'bold 36px Arial'
    context.textAlign = 'center'
    context.textBaseline = 'middle'
    context.fillText(tech, 128, 128)
    
    const texture = new THREE.CanvasTexture(canvas)
    return new THREE.MeshLambertMaterial({ map: texture })
  })
  
  // Crear cubo
  const geometry = new THREE.BoxGeometry(1.5, 1.5, 1.5)
  cube = new THREE.Mesh(geometry, materials)
  scene.add(cube)
}

const animate = () => {
  animationId = requestAnimationFrame(animate)
  
  // Rotación automática del cubo
  if (cube) {
    cube.rotation.x += 0.01
    cube.rotation.y += 0.01
  }
  
  renderer.render(scene, camera)
}

const onCubeResize = () => {
  // Mantener proporción cuadrada
  const size = Math.min(300, window.innerWidth * 0.3)
  renderer.setSize(size, size)
}

// Interactividad con el mouse para el cubo
const onMouseMove = (event) => {
  if (!cube) return
  
  const rect = cubeContainer.value.getBoundingClientRect()
  const x = ((event.clientX - rect.left) / rect.width) * 2 - 1
  const y = -((event.clientY - rect.top) / rect.height) * 2 + 1
  
  cube.rotation.y = x * 0.5
  cube.rotation.x = y * 0.5
}

onMounted(() => {
  cubeContainer.value.addEventListener('mousemove', onMouseMove)
  cubeContainer.value.addEventListener('mouseleave', () => {
    // Volver a la rotación automática cuando el mouse sale
  })
})

onUnmounted(() => {
  if (cubeContainer.value) {
    cubeContainer.value.removeEventListener('mousemove', onMouseMove)
  }
})
</script>

<style scoped>
.cube-container {
  width: 300px;
  height: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  transition: transform 0.3s ease;
}

.cube-container:hover {
  transform: scale(1.05);
}

.cube-container canvas {
  border-radius: 15px;
  box-shadow: 0 10px 30px rgba(255, 215, 0, 0.3);
}

@media (max-width: 768px) {
  .cube-container {
    width: 200px;
    height: 200px;
  }
}
</style>
