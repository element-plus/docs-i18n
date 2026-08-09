---
title: SSR
lang: es-ES
---

# Renderización del lado del servidor (SSR)

Al utilizar Element Plus para el desarrollo de SSR, es necesario llevar a cabo una manipulación especial durante SSR para evitar errores de hidratación.

:::tip

Para los usuarios de Nuxt, proporcionamos un [módulo Nuxt](https://github.com/element-plus/element-plus-nuxt) que contiene estos procesos especiales. Basta con instalarlo.

:::

## Proporcionar un ID

El valor proporcionado se utiliza para generar el ID único en Element Plus. Debido a que los diferentes IDs son propensos a hidratar errores en SSR, para asegurar que la parte del servidor y la parte del cliente generen el mismo ID, necesitamos inyectar el `ID_injection_key` en Vue.

```ts [main.ts]
// irrelevant code omitted
import { createApp } from 'vue'
import { ID_INJECTION_KEY } from 'element-plus'
import App from './App.vue'

const app = createApp(App)
app.provide(ID_INJECTION_KEY, {
  prefix: 1024,
  current: 0,
})
```

## Provide ZIndex

When you using SSR for development, you may encounter hydration errors caused by `z-index`. In this case, we recommend injecting an initial value to avoid such errors.

```ts [main.ts]
// irrelevant code omitted
import { createApp } from 'vue'
import { ZINDEX_INJECTION_KEY } from 'element-plus'
import App from './App.vue'

const app = createApp(App)
app.provide(ZINDEX_INJECTION_KEY, { current: 0 })
```

## Teleports

[Teleport](https://vuejs.org/guide/scaling-up/ssr.html#teleports) es utilizado internamente por varios componentes en Element Plus (por ejemplo. ElDialog, ElDrawer, ElTooltip, ElDropdown, ElSelect, ElDatePicker ...), por lo que es necesario un manejo especial durante SSR.

### Procesa el teletransporte en el montaje (onMounted)

Una solución más fácil es hacer el Teleport condicionalmente en el montaje.

Por ejemplo, utilice el componente `ClientOnly` en Nuxt.

```html
<client-only>
  <el-tooltip content="the tooltip content">
    <el-button>tooltip</el-button>
  </el-tooltip>
</client-only>
```

o

```vue
<script setup>
import { ref } from 'vue'

const isClient = ref(false)

onMounted(() => {
  isClient.value = true
})
</script>

<template>
  <el-tooltip v-if="isClient" content="the tooltip content">
    <el-button>tooltip</el-button>
  </el-tooltip>
</template>
```

### Inyectar el marcado de teletransporte

Otra forma es inyectar el marcado de teletransporte en la ubicación correcta del HTML al final de la página.

Necesitas inyectar el marcado de teletransporte cerca de la etiqueta `<body>`.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Element Plus</title>
    <!--preload-links-->
  </head>
  <body>
    <!--app-teleports-->
    <div id="app"><!--app-html--></div>
    <script type="module" src="/src/entry-client.js"></script>
  </body>
</html>
```

:::tip

Si modifica el atributo [Namespace](./namespace.md) o `append-to`, necesita ajustar el valor `#el-popper-container-`.

:::

```js [src/entry-server.js]
// irrelevant code omitted
import { renderToString } from 'vue/server-renderer'
import { createApp } from './main'

export async function render(url, manifest) {
  // ...
  const ctx = {}
  const html = await renderToString(app, ctx)
  const preloadLinks = renderPreloadLinks(ctx.modules, manifest)
  const teleports = renderTeleports(ctx.teleports)

  return [html, preloadLinks, teleports]
}

function renderTeleports(teleports) {
  if (!teleports) return ''
  return Object.entries(teleports).reduce((all, [key, value]) => {
    if (key.startsWith('#el-popper-container-')) {
      return `${all}<div id="${key.slice(1)}">${value}</div>`
    }
    return all
  }, teleports.body || '')
}
```

```js [server.js or prerender.js]
// irrelevant code omitted
const [appHtml, preloadLinks, teleports] = await render(url, manifest)

const html = template
  .replace('<!--preload-links-->', preloadLinks)
  .replace('<!--app-html-->', appHtml)
  .replace(/(\n|\r\n)\s*<!--app-teleports-->/, teleports)
```
