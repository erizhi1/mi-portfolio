<template>
  <div ref="threeContainer" class="three-container"></div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import * as THREE from 'three'

const threeContainer = ref(null)
let scene, camera, renderer, particles, animationId

onMounted(() => {
  initThree()
  animate()
  window.addEventListener('resize', onWindowResize)
})

onUnmounted(() => {
  if (animationId) {
    cancelAnimationFrame(animationId)
  }
  if (renderer) {
    renderer.dispose()
  }
  window.removeEventListener('resize', onWindowResize)
})

const initThree = () => {
  // Escena
  scene = new THREE.Scene()
  
  // Cámara
  camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000)
  camera.position.z = 5
  
  // Renderer
  renderer = new THREE.WebGLRenderer({ alpha: true, antialias: true })
  renderer.setSize(window.innerWidth, window.innerHeight)
  renderer.setClearColor(0x000000, 0) // Transparente
  threeContainer.value.appendChild(renderer.domElement)
  
  // Crear partículas
  createParticles()
  
  // Crear geometrías flotantes
  createFloatingGeometries()
}

const createParticles = () => {
  const particleCount = 1000
  const positions = new Float32Array(particleCount * 3)
  const colors = new Float32Array(particleCount * 3)
  
  for (let i = 0; i < particleCount * 3; i += 3) {
    // Posiciones aleatorias
    positions[i] = (Math.random() - 0.5) * 20
    positions[i + 1] = (Math.random() - 0.5) * 20
    positions[i + 2] = (Math.random() - 0.5) * 20
    
    // Colores en tonos azul/morado
    colors[i] = Math.random() * 0.5 + 0.5     // R
    colors[i + 1] = Math.random() * 0.3 + 0.4 // G
    colors[i + 2] = Math.random() * 0.5 + 0.8 // B
  }
  
  const geometry = new THREE.BufferGeometry()
  geometry.setAttribute('position', new THREE.BufferAttribute(positions, 3))
  geometry.setAttribute('color', new THREE.BufferAttribute(colors, 3))
  
  const material = new THREE.PointsMaterial({
    size: 0.05,
    vertexColors: true,
    transparent: true,
    opacity: 0.8
  })
  
  particles = new THREE.Points(geometry, material)
  scene.add(particles)
}

const createFloatingGeometries = () => {
  // Crear algunos cubos y esferas flotantes que representen datos/código
  const geometries = [
    new THREE.BoxGeometry(0.3, 0.3, 0.3),
    new THREE.SphereGeometry(0.15, 8, 6),
    new THREE.OctahedronGeometry(0.2),
    new THREE.TetrahedronGeometry(0.2)
  ]
  
  const materials = [
    new THREE.MeshBasicMaterial({ color: 0xffd700, wireframe: true }),
    new THREE.MeshBasicMaterial({ color: 0x667eea, wireframe: true }),
    new THREE.MeshBasicMaterial({ color: 0x764ba2, wireframe: true }),
    new THREE.MeshBasicMaterial({ color: 0xf093fb, wireframe: true })
  ]
  
  for (let i = 0; i < 8; i++) {
    const geometry = geometries[i % geometries.length]
    const material = materials[i % materials.length]
    const mesh = new THREE.Mesh(geometry, material)
    
    // Posición aleatoria
    mesh.position.x = (Math.random() - 0.5) * 10
    mesh.position.y = (Math.random() - 0.5) * 10
    mesh.position.z = (Math.random() - 0.5) * 10
    
    // Rotación aleatoria
    mesh.rotation.x = Math.random() * Math.PI
    mesh.rotation.y = Math.random() * Math.PI
    
    // Agregar propiedades personalizadas para animación
    mesh.userData = {
      originalPosition: mesh.position.clone(),
      rotationSpeed: Math.random() * 0.02 + 0.01
    }
    
    scene.add(mesh)
  }
}

const animate = () => {
  animationId = requestAnimationFrame(animate)
  
  // Rotar partículas
  if (particles) {
    particles.rotation.y += 0.001
    particles.rotation.x += 0.0005
  }
  
  // Animar geometrías flotantes
  scene.children.forEach((child) => {
    if (child.userData && child.userData.rotationSpeed) {
      child.rotation.x += child.userData.rotationSpeed
      child.rotation.y += child.userData.rotationSpeed * 0.7
      
      // Movimiento flotante sutil
      child.position.y = child.userData.originalPosition.y + Math.sin(Date.now() * 0.001 + child.position.x) * 0.1
    }
  })
  
  renderer.render(scene, camera)
}

const onWindowResize = () => {
  camera.aspect = window.innerWidth / window.innerHeight
  camera.updateProjectionMatrix()
  renderer.setSize(window.innerWidth, window.innerHeight)
}

// Interactividad con el mouse
const onMouseMove = (event) => {
  const mouseX = (event.clientX / window.innerWidth) * 2 - 1
  const mouseY = -(event.clientY / window.innerHeight) * 2 + 1
  
  if (camera) {
    camera.position.x = mouseX * 0.5
    camera.position.y = mouseY * 0.5
  }
}

onMounted(() => {
  window.addEventListener('mousemove', onMouseMove)
})

onUnmounted(() => {
  window.removeEventListener('mousemove', onMouseMove)
})
</script>

<style scoped>
.three-container {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1;
  pointer-events: none;
}

.three-container canvas {
  display: block;
}
</style>
