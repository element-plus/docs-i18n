---
title: Quick Start
lang: es-ES
---

# Inicio Rápido

Esta sección describe cómo utilizar Element Plus en su proyecto.

## Uso

### Importación completa

Si no le importa tanto el tamaño del paquete, es más conveniente utilizar la importación completa.

```ts [main.ts]
import { createApp } from 'vue'
import ElementPlus from 'element-plus'
import 'element-plus/dist/index.css'
import App from './App.vue'

const app = createApp(App)

app.use(ElementPlus)
app.mount('#app')
```

#### Soporte Volar

Si utiliza volar, agregue la definición global a `compilerOptions.types` en `tsconfig.json`.

```json [tsconfig.json]
{
  "compilerOptions": {
    // ...
    "types": ["element-plus/global"]
  }
}
```

### Importación a petición

Necesita usar un plugin adicional para importar componentes que haya utilizado.

#### Autoimportación <el-tag type="primary" style="vertical-align: middle;" effect="dark" size="small">Recomendado</el-tag>

Primero necesita instalar `unplugin-vue-components` y `unplugin-auto-import`.

::: code-group

```shell [npm]
$ npm install -D unplugin-vue-components unplugin-auto-import
```

```shell [yarn]
$ yarn add -D unplugin-vue-components unplugin-auto-import
```

```shell [pnpm]
$ pnpm install -D unplugin-vue-components unplugin-auto-import
```

:::

Then add the code below into your `Vite` or `Webpack` config file.

::: code-group

```ts [vite.config.ts]
import { defineConfig } from 'vite'
import AutoImport from 'unplugin-auto-import/vite'
import Components from 'unplugin-vue-components/vite'
import { ElementPlusResolver } from 'unplugin-vue-components/resolvers'

export default defineConfig({
  // ...
  plugins: [
    // ...
    AutoImport({
      resolvers: [ElementPlusResolver()],
    }),
    Components({
      resolvers: [ElementPlusResolver()],
    }),
  ],
})
```

```js [webpack.config.js]
const AutoImport = require('unplugin-auto-import/webpack')
const Components = require('unplugin-vue-components/webpack')
const { ElementPlusResolver } = require('unplugin-vue-components/resolvers')

module.exports = {
  // ...
  plugins: [
    AutoImport({
      resolvers: [ElementPlusResolver()],
    }),
    Components({
      resolvers: [ElementPlusResolver()],
    }),
  ],
}
```

:::

Para más paquetes ([Rollup](https://rollupjs.org/), [Vue CLI](https://cli.vuejs.org/)) y configuraciones, por favor consulte [unplugin-vue-components](https://github.com/antfu/unplugin-vue-components#installation) y [unplugin-auto-import](https://github.com/antfu/unplugin-auto-import#install).

#### Nuxt

Para usuarios de Nuxt, solo necesita instalar `@element-plus/nuxt`.

::: code-group

```shell [npm]
$ npm install -D @element-plus/nuxt
```

```shell [yarn]
$ yarn add -D @element-plus/nuxt
```

```shell [pnpm]
$ pnpm install -D @element-plus/nuxt
```

:::

Luego añada el código de abajo en su archivo de configuración.

```ts [nuxt.config.ts]
export default defineNuxtConfig({
  modules: ['@element-plus/nuxt'],
})
```

Consulte los [documentos](https://github.com/element-plus/element-plus-nuxt#readme) para saber cómo configurarlo.

### Importar manualmente

Element Plus proporciona funcionalidades de [Tree Shaking](https://webpack.js.org/guides/tree-shaking/) basada en los Módulos ES.

Pero necesita instalar [unplugin-element-plus](https://github.com/element-plus/unplugin-element-plus) para importar estilo. Y consulte la [documentación](https://github.com/element-plus/unplugin-element-plus#readme) para saber cómo configurarla.

```vue [App.vue]
<template>
  <el-button>I am ElButton</el-button>
</template>

<script setup lang="ts">
import { ElButton } from 'element-plus'
</script>
```

```ts [vite.config.ts]
import { defineConfig } from 'vite'
import ElementPlus from 'unplugin-element-plus/vite'

export default defineConfig({
  // ...
  plugins: [ElementPlus()],
})
```

## Plantilla de inicio

Proporcionamos una [Plantilla de Vite](https://github.com/element-plus/element-plus-vite-starter).

Para los usuarios de Nuxt tenemos una [Plantilla de Nuxt](https://github.com/element-plus/element-plus-nuxt-starter).

Para los usuarios de Laravel tenemos una [Plantilla de Laravel](https://github.com/element-plus/element-plus-in-laravel-starter).

## Configuración global

Al registrar Element Plus, se puede pasar un objeto de configuración global. Este objeto soporta actualmente los campos `size` y `zIndex` `size` se utiliza para cambiar el tamaño por defecto del componente y `zIndex` establece el `z-indez` inicial de la caja emergente, valor por defecto `2000`.

Importación completa:

```ts [main.ts]
import { createApp } from 'vue'
import ElementPlus from 'element-plus'
import App from './App.vue'

const app = createApp(App)
app.use(ElementPlus, { size: 'small', zIndex: 3000 })
```

Bajo demanda:

```vue [App.vue]
<template>
  <el-config-provider :size="size" :z-index="zIndex">
    <app />
  </el-config-provider>
</template>

<script setup lang="ts">
import { ElConfigProvider } from 'element-plus'

const zIndex = 3000
const size = 'small'
</script>
```

## Usando Nuxt.js

We can also use [Nuxt.js](https://nuxt.com). Please refer to [Element Plus Nuxt.js starter template](https://github.com/element-plus/element-plus-nuxt-starter) for more details.

## Empecemos

Puede arrancar su proyecto a partir de ahora. For each components usage, please refer to [the individual component documentation](../component/button.md).
