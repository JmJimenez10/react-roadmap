# 🚀 01. CLI Tools: Vite

## 📋 Introducción
Vite es una herramienta moderna y eficiente para crear proyectos frontend, especialmente recomendada para aplicaciones con React. Su principal ventaja es la rapidez, gracias a su servidor de desarrollo ultrarrápido y un sistema de construcción optimizado que mejora los tiempos de carga y actualización.

Con Vite, puedes iniciar un proyecto React en cuestión de segundos, disfrutando de recargas en caliente (hot module replacement) instantáneas, lo que hace que el proceso de desarrollo sea fluido y eficiente.

## 📦 Instalación de Vite con React

1. Crea el proyecto  
`npm create vite@latest`  
* Añadir nombre del proyecto
* Escoger `React` como framework
* Elegir `JavaScript + SWC` como variante
+ Una vez hecho esto, ir al directorio del proyecto  
`cd nombre-proyecto`

2. Instalar dependencias  
`npm install`

3. Ejecutar el servidor  
`npm run dev`

## 📁 Estructura básica de archivos
Al crear el proyecto, se genera una estructura de carpetas como esta:
```
nombre-proyecto/
├── public/
└── src/
    ├── App.jsx
    ├── index.css
    └── main.jsx
```
- **public/:** Contiene recursos estáticos.
- **src/:** Carpeta principal del código de tu aplicación.
    - `App.jsx`: Componente principal.
    - `index.css`: Archivo de estilos.
    - `main.jsx`: Punto de entrada de la aplicación.    
  
Esta organización es simple y fácil de entender, lo que te permite comenzar a programar rápidamente.