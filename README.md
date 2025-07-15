# Mi Portfolio Personal

Un portfolio moderno y responsivo desarrollado con Vue.js 3 y Vite, diseñado para mostrar mis habilidades, proyectos y experiencia como desarrollador.

## 🚀 Características

- ✨ Diseño moderno y atractivo
- 📱 Completamente responsivo
- 🎨 Animaciones suaves y transiciones
- 📧 Formulario de contacto funcional
- 🔍 Filtros de proyectos
- ⚡ Optimizado para rendimiento
- 🎯 SEO friendly

## 🛠️ Tecnologías Utilizadas

- **Vue.js 3** - Framework principal
- **Vite** - Build tool y desarrollo
- **CSS3** - Estilos y animaciones
- **JavaScript ES6+** - Lógica de la aplicación
- **HTML5** - Estructura semántica

## 📦 Instalación

1. Clona el repositorio:
```bash
git clone https://github.com/erizhi1/mi-portfolio.git
cd mi-portfolio
```

2. Instala las dependencias:
```bash
npm install
```

3. Inicia el servidor de desarrollo:
```bash
npm run dev
```

4. Abre tu navegador en `http://localhost:5173`

## 🏗️ Scripts Disponibles

- `npm run dev` - Inicia el servidor de desarrollo
- `npm run build` - Construye la aplicación para producción
- `npm run preview` - Previsualiza la build de producción

## 📁 Estructura del Proyecto

```
src/
├── assets/          # Imágenes, logos, íconos
├── components/      # Componentes reutilizables
│   ├── Hero.vue     # Sección principal/inicio
│   ├── About.vue    # Información personal y habilidades
│   ├── Projects.vue # Portfolio de proyectos
│   └── Contact.vue  # Formulario de contacto
├── App.vue          # Componente principal
└── main.js          # Punto de entrada
```

## 🎨 Secciones

### Hero
Sección de bienvenida con presentación personal y llamadas a la acción.

### Sobre Mí
Información personal, habilidades técnicas y estadísticas profesionales.

### Proyectos
Galería filtrable de proyectos con enlaces a demos y código fuente.

### Contacto
Formulario de contacto con validación e información de contacto.

## 🔧 Personalización

### Información Personal
Edita los siguientes archivos para personalizar tu información:

- `src/components/Hero.vue` - Nombre, título y descripción
- `src/components/About.vue` - Habilidades, experiencia y biografía
- `src/components/Contact.vue` - Información de contacto y redes sociales

### Proyectos
Modifica el array `projects` en `src/components/Projects.vue`

## 🚀 Despliegue

### GitHub Pages (Automático)
El proyecto está configurado para desplegarse automáticamente en GitHub Pages usando GitHub Actions.

🌐 **Sitio en vivo**: https://erizhi1.github.io/mi-portfolio/

Cada push a la rama `main` actualiza automáticamente el sitio.

### Netlify/Vercel (Manual)
1. Construye el proyecto: `npm run build`
2. Sube la carpeta `dist` al servicio de hosting

## 🔧 Desarrollo Local

Para trabajar en el proyecto localmente:

```bash
# Clonar e instalar
git clone https://github.com/erizhi1/mi-portfolio.git
cd mi-portfolio
npm install

# Desarrollo
npm run dev

# Construir para producción
npm run build

# Previsualizar build
npm run preview
```

## 📧 Contacto

Personaliza tu información de contacto en los componentes correspondientes.

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Por favor:

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto está bajo la Licencia MIT.

---

⭐ Si te gusta este proyecto, ¡dale una estrella en GitHub!

**Desarrollado con ❤️ por [erizhi1](https://github.com/erizhi1)**
