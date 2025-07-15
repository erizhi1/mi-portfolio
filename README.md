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

- **Vue.js 3.4.0** - Framework principal
- **Vite 5.4.0** - Build tool y desarrollo
- **CSS3** - Estilos y animaciones
- **JavaScript ES6+** - Lógica de la aplicación
- **HTML5** - Estructura semántica
- **GitHub Actions** - CI/CD automático
- **GitHub Pages** - Hosting

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

4. Abre tu navegador en `http://localhost:5176/mi-portfolio/`

> **Nota**: El puerto puede variar (5173, 5174, 5175, 5176...) dependiendo de cuáles estén disponibles.

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

public/
├── favicon.ico      # Ícono del sitio
└── 404.html         # Página de error para SPA routing

.github/
└── workflows/
    └── deploy.yml   # Configuración de GitHub Actions
```

## ⚙️ Configuración

### Vite Config
- **Base path**: `/mi-portfolio/` para GitHub Pages
- **Build output**: `dist/` 
- **Development server**: Puerto automático (5173+)

### GitHub Actions
- **Trigger**: Push a rama `main`
- **Node version**: 18
- **Build command**: `npm run build`
- **Deploy**: Automático a GitHub Pages

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

### GitHub Pages (Automático) ✅
El proyecto está configurado para desplegarse automáticamente en GitHub Pages usando GitHub Actions.

🌐 **Sitio en vivo**: https://erizhi1.github.io/mi-portfolio/

**Configuración automática:**
- Cada push a la rama `main` activa el workflow de GitHub Actions
- El proyecto se construye automáticamente con `npm run build`
- Los archivos se despliegan en GitHub Pages
- Tiempo de despliegue: ~2-3 minutos

**Requisitos:**
- GitHub Pages habilitado con source "GitHub Actions"
- Workflow configurado en `.github/workflows/deploy.yml`

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
