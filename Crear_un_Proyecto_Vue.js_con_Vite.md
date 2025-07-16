# Manual Paso a Paso para Crear un Proyecto Vue.js con Vite

Este manual te guiará paso a paso para crear un proyecto Vue.js utilizando **Vite**, una herramienta moderna y rápida para desarrollo frontend.

## Requisitos Previos

* Tener instalado **Node.js** (v16 o superior).
* Tener instalado **npm** o **yarn**.
* Editor de código como Visual Studio Code.
* Terminal (PowerShell, Git Bash, etc).

## Paso 1: Crear Proyecto con Vite

Ejecuta el siguiente comando en tu terminal:

```bash
npm create vue@latest
# o con yarn
yarn create vue
```

### Durante el proceso:

* Elige el nombre de tu proyecto.
* Selecciona **Vue**.
* Elige **JavaScript** o **TypeScript** según tu preferencia.
* Opcionalmente activa funcionalidades como Router, Pinia, etc.

## Paso 2: Instalar Dependencias

Accede a la carpeta del proyecto y ejecuta:

```bash
cd nombre-del-proyecto
npm install
# o
yarn
```

## Paso 3: Ejecutar el Servidor de Desarrollo

```bash
npm run dev
# o
yarn dev
```

Esto iniciará el servidor en `http://localhost:5173` (puerto puede variar).

## Paso 4: Estructura del Proyecto

```
nombre-del-proyecto/
├── public/             # Archivos estáticos
├── src/                # Código fuente principal
│   ├── assets/         # Recursos (imágenes, estilos)
│   ├── components/     # Componentes Vue
│   ├── App.vue         # Componente principal
│   └── main.js         # Punto de entrada
├── index.html          # HTML principal
├── package.json        # Configuración del proyecto
└── vite.config.js      # Configuración de Vite
```

## Paso 5: Crear un Componente

Crea `HolaMundo.vue` en `src/components/`:

```vue
<template>
  <div>
    <h1>{{ mensaje }}</h1>
    <button @click="cambiarMensaje">Cambiar Mensaje</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mensaje: "¡Hola desde Vite y Vue!"
    }
  },
  methods: {
    cambiarMensaje() {
      this.mensaje = "¡Vue con Vite es rápido!"
    }
  }
}
</script>

<style scoped>
h1 {
  color: #42b983;
}
</style>
```

Incluye el componente en `App.vue`:

```vue
<script setup>
import HolaMundo from './components/HolaMundo.vue'
</script>

<template>
  <HolaMundo />
</template>
```

## Paso 6: Crear Build para Producción

```bash
npm run build
# o
yarn build
```

Esto generará la carpeta `dist/` con los archivos optimizados para despliegue.

## Paso 7: Recursos Adicionales

* [Documentación Oficial Vue.js](https://vuejs.org/)
* [Documentación Vite](https://vitejs.dev/)
* [Pinia - Manejo de Estado](https://pinia.vuejs.org/)
* [Vue Router](https://router.vuejs.org/)

## Conclusión

Con estos pasos ya tienes un proyecto Vue con Vite configurado y listo para desarrollo moderno, rápido y escalable.
