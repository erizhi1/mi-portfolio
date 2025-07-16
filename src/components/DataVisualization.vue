<template>
  <div ref="dataVizContainer" class="data-viz-container"></div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import * as THREE from 'three'

const dataVizContainer = ref(null)
let scene, camera, renderer, dataPoints = [], animationId

onMounted(() => {
  initDataViz()
  animate()
  window.addEventListener('resize', onDataVizResize)
})

onUnmounted(() => {
  if (animationId) {
    cancelAnimationFrame(animationId)
  }
  if (renderer) {
    renderer.dispose()
  }
  window.removeEventListener('resize', onDataVizResize)
})

const initDataViz = () => {
  // Escena
  scene = new THREE.Scene()
  
  // Cámara
  camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000)
  camera.position.set(0, 0, 8)
  
  // Renderer
  renderer = new THREE.WebGLRenderer({ alpha: true, antialias: true })
  renderer.setSize(window.innerWidth, 400)
  renderer.setClearColor(0x000000, 0)
  dataVizContainer.value.appendChild(renderer.domElement)
  
  // Crear visualización de datos
  createDataVisualization()
  
  // Iluminación
  const ambientLight = new THREE.AmbientLight(0xffffff, 0.6)
  scene.add(ambientLight)
  
  const directionalLight = new THREE.DirectionalLight(0xffffff, 0.8)
  directionalLight.position.set(5, 5, 5)
  scene.add(directionalLight)
}

const createDataVisualization = () => {
  // Crear puntos de datos que representen proyectos/tecnologías - SynthWave '84 Style
  const projects = [
    { name: 'PHP', value: 95, color: 0xff006e },          // Magenta vibrante
    { name: 'Laravel', value: 90, color: 0xff4081 },      // Rosa neón
    { name: 'MySQL', value: 88, color: 0x00ffff },        // Cyan brillante
    { name: 'Oracle', value: 75, color: 0x8338ec },       // Púrpura eléctrico
    { name: 'PostgreSQL', value: 80, color: 0x3a86ff },   // Azul neón
    { name: 'JavaScript', value: 85, color: 0xffbe0b },   // Amarillo neón
    { name: 'Docker', value: 65, color: 0xff5722 },       // Naranja cyber
    { name: 'Git', value: 85, color: 0x00ff88 }           // Verde neón
  ]
  
  projects.forEach((project, index) => {
    // Crear geometría basada en el valor
    const height = (project.value / 100) * 3
    const geometry = new THREE.CylinderGeometry(0.3, 0.3, height, 8)
    const material = new THREE.MeshLambertMaterial({ 
      color: project.color,
      transparent: true,
      opacity: 0.8
    })
    
    const cylinder = new THREE.Mesh(geometry, material)
    
    // Posicionar en círculo
    const angle = (index / projects.length) * Math.PI * 2
    const radius = 4
    cylinder.position.x = Math.cos(angle) * radius
    cylinder.position.z = Math.sin(angle) * radius
    cylinder.position.y = height / 2 - 1.5
    
    // Agregar datos personalizados
    cylinder.userData = {
      originalY: cylinder.position.y,
      name: project.name,
      value: project.value,
      hovered: false
    }
    
    scene.add(cylinder)
    dataPoints.push(cylinder)
    
    // Crear etiqueta (text geometry sería complejo, usamos sprites)
    createLabel(project.name, cylinder.position.x, cylinder.position.y + height/2 + 0.5, cylinder.position.z)
  })
  
  // Crear líneas conectoras
  createConnections()
}

const createLabel = (text, x, y, z) => {
  const canvas = document.createElement('canvas')
  const context = canvas.getContext('2d')
  canvas.width = 256
  canvas.height = 64
  
  // Fondo SynthWave con gradiente
  const gradient = context.createLinearGradient(0, 0, 256, 64)
  gradient.addColorStop(0, 'rgba(139, 69, 19, 0.9)')  // Marrón oscuro
  gradient.addColorStop(0.5, 'rgba(75, 0, 130, 0.9)') // Púrpura oscuro
  gradient.addColorStop(1, 'rgba(25, 25, 112, 0.9)')  // Azul medianoche
  
  context.fillStyle = gradient
  context.fillRect(0, 0, 256, 64)
  
  // Borde neón
  context.strokeStyle = '#ff006e'
  context.lineWidth = 2
  context.strokeRect(2, 2, 252, 60)
  
  // Texto estilo SynthWave con glow
  context.shadowColor = '#00ffff'
  context.shadowOffsetX = 0
  context.shadowOffsetY = 0
  context.shadowBlur = 10
  
  context.fillStyle = '#00ffff'
  context.font = 'bold 24px "Courier New", monospace'
  context.textAlign = 'center'
  context.textBaseline = 'middle'
  context.fillText(text, 128, 32)
  
  // Segundo glow para mayor intensidad
  context.shadowBlur = 20
  context.fillText(text, 128, 32)
  
  const texture = new THREE.CanvasTexture(canvas)
  const spriteMaterial = new THREE.SpriteMaterial({ 
    map: texture,
    transparent: true
  })
  const sprite = new THREE.Sprite(spriteMaterial)
  
  sprite.position.set(x, y, z)
  sprite.scale.set(1.4, 0.35, 1)
  
  scene.add(sprite)
}

const createConnections = () => {
  // Crear líneas que conecten algunos puntos para simular red de datos
  const geometry = new THREE.BufferGeometry()
  const positions = []
  
  for (let i = 0; i < dataPoints.length; i++) {
    const current = dataPoints[i].position
    const next = dataPoints[(i + 1) % dataPoints.length].position
    
    positions.push(current.x, current.y, current.z)
    positions.push(next.x, next.y, next.z)
  }
  
  geometry.setAttribute('position', new THREE.Float32BufferAttribute(positions, 3))
  
  const material = new THREE.LineBasicMaterial({ 
    color: 0xff006e,  // Magenta neón
    transparent: true, 
    opacity: 0.6 
  })
  
  const lines = new THREE.LineSegments(geometry, material)
  scene.add(lines)
}

const animate = () => {
  animationId = requestAnimationFrame(animate)
  
  // Rotar toda la visualización lentamente
  scene.rotation.y += 0.005
  
  // Animar los puntos de datos
  dataPoints.forEach((point, index) => {
    // Flotación sutil
    point.position.y = point.userData.originalY + Math.sin(Date.now() * 0.001 + index) * 0.1
    
    // Efecto hover/pulse
    if (point.userData.hovered) {
      point.scale.setScalar(1.2)
    } else {
      point.scale.setScalar(1)
    }
  })
  
  renderer.render(scene, camera)
}

const onDataVizResize = () => {
  camera.aspect = window.innerWidth / 400
  camera.updateProjectionMatrix()
  renderer.setSize(window.innerWidth, 400)
}

// Interactividad con raycasting
const raycaster = new THREE.Raycaster()
const mouse = new THREE.Vector2()

const onMouseMove = (event) => {
  const rect = dataVizContainer.value.getBoundingClientRect()
  mouse.x = ((event.clientX - rect.left) / rect.width) * 2 - 1
  mouse.y = -((event.clientY - rect.top) / rect.height) * 2 + 1
  
  raycaster.setFromCamera(mouse, camera)
  const intersects = raycaster.intersectObjects(dataPoints)
  
  // Reset all hover states
  dataPoints.forEach(point => point.userData.hovered = false)
  
  // Set hover state for intersected objects
  if (intersects.length > 0) {
    intersects[0].object.userData.hovered = true
    dataVizContainer.value.style.cursor = 'pointer'
  } else {
    dataVizContainer.value.style.cursor = 'default'
  }
}

onMounted(() => {
  dataVizContainer.value.addEventListener('mousemove', onMouseMove)
})

onUnmounted(() => {
  if (dataVizContainer.value) {
    dataVizContainer.value.removeEventListener('mousemove', onMouseMove)
  }
})
</script>

<style scoped>
.data-viz-container {
  width: 100%;
  height: 400px;
  position: relative;
  overflow: hidden;
  border-radius: 15px;
  background: linear-gradient(135deg, 
    rgba(25, 25, 112, 0.8) 0%,     /* Azul medianoche */
    rgba(75, 0, 130, 0.8) 50%,     /* Púrpura */
    rgba(139, 69, 19, 0.8) 100%    /* Marrón oscuro */
  );
  border: 2px solid #ff006e;
  box-shadow: 
    0 0 20px rgba(255, 0, 110, 0.5),
    inset 0 0 20px rgba(0, 255, 255, 0.1);
}

.data-viz-container canvas {
  display: block;
  border-radius: 15px;
}
</style>
