# Manual Paso a Paso para Crear un Proyecto Vue.js

Este manual te guiará en la creación de un proyecto Vue.js desde cero, incluyendo la configuración inicial, estructura de carpetas y un ejemplo básico.

## Requisitos Previos

* Tener instalado Node.js (v16 o superior recomendado).
* Un editor de código como VS Code.
* Terminal (PowerShell, Git Bash, Terminal de macOS/Linux).

## Paso 1: Instalar Vue CLI (Opcional, pero recomendado)

Vue CLI es una herramienta oficial para crear y configurar proyectos Vue.

```bash
npm install -g @vue/cli
# o con yarn:
yarn global add @vue/cli
```

Verifica la instalación:

```bash
vue --version
```

## Paso 2: Crear un Proyecto Vue

### Opción A: Con Vue CLI (Recomendado)

Ejecuta en tu terminal:

```bash
vue create mi-proyecto-vue
```

Selecciona:

* `Default (Vue 3)` o `Manually select features` (para personalizar).
* Espera a que se instalen las dependencias.

### Opción B: Con Vite (Alternativa rápida)

```bash
npm create vue@latest
# o
yarn create vue
```

Sigue las instrucciones en pantalla.

## Paso 3: Navegar al Proyecto e Iniciarlo

Entra a la carpeta del proyecto y ejecuta el servidor de desarrollo:

```bash
cd mi-proyecto-vue
npm run dev
# o con yarn:
yarn dev
```

Abre tu navegador en `http://localhost:5173` (puerto puede variar).

## Paso 4: Estructura Básica del Proyecto

```
mi-proyecto-vue/
├── node_modules/       # Dependencias instaladas
├── public/             # Archivos estáticos (HTML, imágenes)
├── src/                # Código fuente principal
│   ├── assets/         # Recursos (CSS, imágenes)
│   ├── components/     # Componentes Vue (.vue)
│   ├── App.vue         # Componente raíz
│   └── main.js         # Punto de entrada de la app
├── package.json        # Configuración del proyecto y dependencias
└── vite.config.js      # Configuración de Vite (si usaste Vite)
```

## Paso 5: Crear tu Primer Componente

En `src/components/`, crea un archivo `HolaMundo.vue`:

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
      mensaje: "¡Hola Vue.js!"
    };
  },
  methods: {
    cambiarMensaje() {
      this.mensaje = "¡Aprendiendo Vue!";
    }
  }
};
</script>

<style scoped>
h1 {
  color: #42b983;
}
</style>
```

Usa el componente en `App.vue`:

```vue
<script setup>
import HolaMundo from './components/HolaMundo.vue'
</script>

<template>
  <HolaMundo />
</template>
```

## Paso 6: Instalar Dependencias Adicionales (Opcional)

Ejemplo: Instalar Vue Router para manejar rutas:

```bash
npm install vue-router
# o
yarn add vue-router
```

Configura `router/index.js` y define rutas.

## Paso 7: Construir para Producción

Genera archivos optimizados:

```bash
npm run build
```

Los archivos se guardan en `/dist`.

## Conclusión

¡Listo! Ahora tienes un proyecto Vue.js funcionando. Puedes:

* Añadir más componentes.
* Integrar librerías como Pinia (para estado global).
* Conectar con APIs usando Axios.

## Recursos Adicionales

* [Documentación Oficial de Vue](https://vuejs.org/)
* [Vue Router](https://router.vuejs.org/)
* [Vuex](https://vuex.vuejs.org/) / [Pinia](https://pinia.vuejs.org/)
