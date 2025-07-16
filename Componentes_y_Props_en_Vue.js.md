# Manual: Componentes y Props en Vue.js

Este manual explica qué son los **componentes** y las **props** en Vue.js, cómo se utilizan y proporciona ejemplos prácticos.

---

## ¿Qué es un Componente en Vue.js?

Un **componente** es una pieza reutilizable de interfaz de usuario que puede contener HTML, CSS y lógica en JavaScript.

Los componentes ayudan a dividir la aplicación en bloques más pequeños y manejables.

---

## Estructura de un Componente

Un componente en Vue se define normalmente en un archivo `.vue` y tiene esta estructura:

```vue
<template>
  <div>
    <!-- HTML -->
  </div>
</template>

<script>
export default {
  name: 'MiComponente'
};
</script>

<style scoped>
/* CSS */
</style>
```

---

## Crear un Componente Personalizado

Archivo: `src/components/Saludo.vue`

```vue
<template>
  <div>
    <h2>¡Hola, {{ nombre }}!</h2>
  </div>
</template>

<script>
export default {
  name: 'Saludo',
  props: {
    nombre: {
      type: String,
      required: true
    }
  }
};
</script>

<style scoped>
h2 {
  color: #2c3e50;
}
</style>
```

---

## ¿Qué son las Props?

Las **props** son atributos personalizados que se utilizan para **pasar datos de un componente padre a un componente hijo**.

Se definen en el componente hijo usando la opción `props` y se pasan desde el componente padre como atributos HTML.

---

## Usar un Componente con Props

Archivo: `src/App.vue`

```vue
<script setup>
import Saludo from './components/Saludo.vue'
</script>

<template>
  <div>
    <Saludo nombre="Juan" />
    <Saludo nombre="Ana" />
  </div>
</template>
```

En este ejemplo:

* El componente `Saludo` recibe una **prop** llamada `nombre`.
* El contenido se renderiza de forma personalizada para cada valor.

---

## Validar Props

Puedes definir el tipo y si es requerida:

```js
props: {
  nombre: {
    type: String,
    required: true
  },
  edad: {
    type: Number,
    default: 18
  }
}
```

---

## Conclusión

* Los **componentes** ayudan a reutilizar código y estructurar mejor tu aplicación.
* Las **props** permiten comunicar datos entre componentes.
* Vue proporciona una forma sencilla y clara para crear componentes con props.

---

## Recursos Recomendados

* [Guía oficial de Componentes - Vue.js](https://vuejs.org/guide/essentials/component-basics.html)
* [Props en Vue.js](https://vuejs.org/guide/components/props.html)
* [Playground Vue para practicar](https://play.vuejs.org)
