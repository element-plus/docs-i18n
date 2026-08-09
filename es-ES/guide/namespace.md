---
title: Custom Namespace
lang: es-ES
---

## Espacio de nombres personalizado ^(2.2.0)

:::tip

Le proporcionamos un ejemplo en [element-plus-vite-starter](https://github.com/element-plus/element-plus-vite-starter). Simplemente compruébelo.

:::

El espacio de nombres predeterminado es `el`. En casos especiales, es posible que necesitemos personalizar el espacio de nombres.

Ya que usamos sass para escribir estilos, puede personalizar todos los espacios de nombres. Tenemos que asumir que usted ya utiliza sass.

Debe establecer `ElConfigProvider` y scss `$namespace` al mismo tiempo.

### Establecer `ElConfigProvider`

Utilice `ElConfigProvider` para envolver su componente raíz.

```vue [App.vue]
<template>
  <el-config-provider namespace="ep">
    <!-- ... -->
  </el-config-provider>
</template>
```

### Establecer Scss & variables Css

Debe crear `styles/element/index.scss`:

```scss [styles/element/index.scss]
// we can add this to custom namespace, default is 'el'
@forward 'element-plus/theme-chalk/src/mixins/config.scss' with (
  $namespace: 'ep'
);
// ...
```

Importar `styles/element/index.scss` en `vite.config.ts`:

> Lo mismo es válido para webpack, que debe establecerse en `preprocessorOptions`.

```ts [vite.config.ts]
import { defineConfig } from 'vite'
// https://vitejs.dev/config/
export default defineConfig({
  // ...
  css: {
    preprocessorOptions: {
      scss: {
        additionalData: `@use "~/styles/element/index.scss" as *;`,
      },
    },
  },
  // ...
})
```

Eso es todo.
