---
title: Theming
lang: es-ES
---

# Tema personalizado

Element Plus utiliza la metodología BEM en CSS con la finalidad de que pueda sobrescribir los estilos fácilmente. Pero si necesita reemplazar estilos a gran escala, p.ej. cambiar el color del tema de azul a naranja o verde, tal vez sobreescribirlos uno por uno no es una buena idea.

Proporcionamos cuatro maneras de cambiar las variables de estilo.

## Cambia el color del tema

Estos son ejemplos sobre temas personalizados.

- Importación completa: [elemento-plus-vite-starter](https://github. com/element-plus/element-plus-vite-starter)
- A demanda: [unplugin-element-plus/examples/vite](https://github. com/element-plus/unplugin-element-plus)

### Por variables SCSS

`theme-chalk` está escrito en SCSS. Puede encontrar las variables SCSS en [`packages/theme-chalk/src/common/var.scss`](https://github.com/element-plus/element-plus/blob/dev/packages/theme-chalk/src/common/var.scss).

:::warning

Utilizamos módulos sass ([sass:map](https://sass-lang.com/documentation/values/maps)...) y `@use` para refactorizar todas las variables SCSS. Y usar `@use` para todas las variables SCSS, resuelve el problema de salida duplicada causado por `@import`.

> [Introducción de los módulos Sass | CSS-TRICKS](https://css-tricks.com/introducing-sass-modules/)

Por ejemplo, usamos `$colors` como mapa para preservar diferentes tipos de colores.

`$notification` es un mapa donde todas las variables del componente `notification`.

En el futuro, escribiremos documentación para variables que pueden ser personalizadas para cada componente. También puede consultar directamente el código fuente [var.scss](https://github.com/element-plus/element-plus/blob/dev/packages/theme-chalk/src/common/var.scss).

:::

```scss
$colors: () !default;
$colors: map.deep-merge(
  (
    'white': #ffffff,
    'black': #000000,
    'primary': (
      'base': #409eff,
    ),
    'success': (
      'base': #67c23a,
    ),
    'warning': (
      'base': #e6a23c,
    ),
    'danger': (
      'base': #f56c6c,
    ),
    'error': (
      'base': #f56c6c,
    ),
    'info': (
      'base': #909399,
    ),
  ),
  $colors
);
```

### ¿Cómo anularlo?

Si su proyecto también utiliza SCSS, puede cambiar directamente las variables de estilo Element Plus. Cree un nuevo archivo de estilo, p. ej., `styles/element/index.scss`:

:::warning

Debería usar `@use 'xxx.scss' as *;` en lugar de `@import 'xxx.scss';`.

Debido a que el equipo de sass dijo que eliminarán `@import` eventualmente.

> [Sass: @use](https://sass-lang.com/documentation/at-rules/use) vs [Sass: @import](https://sass-lang.com/documentation/at-rules/import)

:::

```scss [styles/element/index.scss]
/* just override what you need */
@forward 'element-plus/theme-chalk/src/common/var.scss' with (
  $colors: (
    'primary': (
      'base': green,
    ),
  )
);

// If you just import on demand, you can ignore the following content.
// if you want to import all styles:
// @use "element-plus/theme-chalk/src/index.scss" as *;
```

Luego, en el archivo de entrada de su proyecto, importe este archivo de estilo en lugar del CSS construido por Element:

:::tip

Importe `element/index.scss` antes del scss de element-plus para evitar el problema de las variables mixtas sass porque necesitamos generar light-x para sus variables personalizadas.

:::

Cree un `element/index.scss` para combinar sus variables y variables de element-plus. (Si los importa en ts, no se combinarán.)

:::tip

Además, hay que distinguir su scss de las variables de los elementos scss. Si se combinan entre sí, cada actualización caliente de `element-plus` necesita compilar un gran número de archivos scss, lo que resulta ser un proceso lento.

:::

```ts [main.ts]
import { createApp } from 'vue'
import './styles/element/index.scss'
import ElementPlus from 'element-plus'
import App from './App.vue'

const app = createApp(App)
app.use(ElementPlus)
```

Si está utilizando vite, y desea personalizar el tema al importar bajo demanda.

Use `scss.additionalData` para compilar variables con scss de cada componente.

```ts [vite.config.ts]
import path from 'path'
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'
// You can also use unplugin-vue-components
// import Components from 'unplugin-vue-components/vite'
// import { ElementPlusResolver } from 'unplugin-vue-components/resolvers'
// or use unplugin-element-plus
import ElementPlus from 'unplugin-element-plus/vite'

export default defineConfig({
  resolve: {
    alias: {
      '~/': `${path.resolve(__dirname, 'src')}/`,
    },
  },
  css: {
    preprocessorOptions: {
      scss: {
        additionalData: `@use "~/styles/element/index.scss" as *;`,
      },
    },
  },
  plugins: [
    vue(),
    // use unplugin-vue-components
    // Components({
    //   resolvers: [
    //     ElementPlusResolver({
    //       importStyle: "sass",
    //       // directives: true,
    //       // version: "2.1.5",
    //     }),
    //   ],
    // }),
    // or use unplugin-element-plus
    ElementPlus({
      useSource: true,
    }),
  ],
})
```

Si está utilizando webpack, y desea personalizar el tema al importar bajo demanda.

```js [webpack.config.js]
// use unplugin-element-plus

import ElementPlus from 'unplugin-element-plus/webpack'

export default defineConfig({
  css: {
    loaderOptions: {
      scss: {
        additionalData: `@use "~/styles/element/index.scss" as *;`,
      },
    },
  },
  plugins: [
    ElementPlus({
      useSource: true,
    }),
  ],
})
```

### Por variables CSS

Las variables CSS son una característica muy útil, ya soportada por casi todos los navegadores. (IE: Wait?)

> Aprenda más de [Uso de propiedades personalizadas (variables) en CSS | MDN](https://developer. mozilla. org/es/docs/Web/CSS/Using_CSS_custom_properties)

Hemos utilizado variables css para reconstruir el sistema de estilo de casi todos los componentes.

:::tip

Es compatible con el sistema de variables SCSS. Utilizamos la función de SCSS para generar automáticamente variables CSS para su uso.

:::

Esto significa que puede cambiar dinámicamente variables individuales dentro del componente para personalizarlo mejor sin tener que modificar scss y recompilarlo.

> En el futuro, se escribirán en cada componente los nombres de variables y la documentación del rol de cada componente.

Como esto:

```css
:root {
  --el-color-primary: green;
}
```

Si sólo desea personalizar un componente en particular, simplemente añada estilos en línea para ciertos componentes individualmente.

```html
<el-tag style="--el-tag-bg-color: red">Tag</el-tag>
```

Por razones de rendimiento, es más recomendable personalizar las variables css bajo una clase que el global `:root`.

```css
.custom-class {
  --el-tag-bg-color: red;
}
```

Si desea controlar las variables css por script, pruebe esto:

```ts
// document.documentElement is global
const el = document.documentElement
// const el = document.getElementById('xxx')

// get css var
getComputedStyle(el).getPropertyValue(`--el-color-primary`)

// set css var
el.style['--el-color-primary'] = 'red'
```

Si desea una forma más elegante, compruebe esto. [useCssVar | VueUse](https://vueuse.org/core/usecssvar/)
