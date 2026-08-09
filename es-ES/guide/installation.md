---
title: Instalación
lang: es-ES
---

# Instalación

## Compatibility ^(2.5.0)

Element Plus can run on browsers that support last 2 versions.

If you really need to support outdated browsers, please add [Babel](https://babeljs.io/) and Polyfill yourself.

Since Vue 3 no longer supports IE11, Element Plus does not support IE either.

| version | ![Chrome](https://cdn.jsdelivr.net/npm/@browser-logos/chrome/chrome_32x32.png) <br> Chrome | ![IE](https://cdn.jsdelivr.net/npm/@browser-logos/edge/edge_32x32.png) <br> Edge | ![Firefox](https://cdn.jsdelivr.net/npm/@browser-logos/firefox/firefox_32x32.png) <br> Firefox | ![Safari](https://cdn.jsdelivr.net/npm/@browser-logos/safari/safari_32x32.png) <br> Safari |
| ------- | ------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| < 2.5.0 | Chrome ≥ 64                                                                                      | Edge ≥ 79                                                                              | Firefox ≥ 78                                                                                         | Safari ≥ 12                                                                                      |
| 2.5.0 + | Chrome ≥ 85                                                                                      | Edge ≥ 85                                                                              | Firefox ≥ 79                                                                                         | Safari ≥ 14.1                                                                                    |

### Sass

Version `2.8.5` and later, the minimum compatible version of [Sass](https://github.com/sass) is `1.79.0`.

If your terminal prompts `legacy JS API Deprecation Warning`, you can configure the following code in [vite.config.ts](https://vitejs.dev/config/shared-options.html#css-preprocessoroptions).

```ts [vite.config.ts]{7}
import { defineConfig } from 'vite'
// https://vitejs.dev/config/
export default defineConfig({
  // ...
  css: {
    preprocessorOptions: {
      scss: { api: 'modern-compiler' },
    },
  },
  // ...
})
```

### Versión

Element Plus is currently in a rapid development iteration. [![Insignia de versión ElementPlus](https://img.shields.io/npm/v/element-plus.svg?style=flat-square)](https://www.npmjs.org/package/element-plus)

In addition, every commit and PR on the dev branch will be published to [pkg.pr.new](https://github.com/stackblitz-labs/pkg.pr.new), if you want to use some unpublished content, you can refer to [here](https://github.com/element-plus/element-plus/issues/18433#issuecomment-2392618431).

## Gestor de paquetes

**We recommend using the package manager ([NPM](https://www.npmjs.com/), [Yarn](https://classic.yarnpkg.com/lang/en/), [PNPM](https://pnpm.io/)) to install Element Plus**, so that you can utilize bundlers like [Vite](https://vitejs.dev) and [Webpack](https://webpack.js.org/).

Choose a package manager you like.

::: code-group

```shell [npm]
$ npm install element-plus --save
```

```shell [yarn]
$ yarn add element-plus
```

```shell [pnpm]
$ pnpm install element-plus
```

```shell [deno]
$ deno add element-plus
```

:::

If your network environment is not good, it is recommended to use a mirror registry [cnpm](https://github.com/cnpm/cnpm) or [npmmirror](https://npmmirror.com/).

```shell
npm config set registry https://registry.npmmirror.com
```

## Importar en el navegador

Puede importar Element Plus directamente a las etiquetas HTML del navegador y utilizar la variable global `ElementPlus`.

Según los diferentes proveedores de **CDN** hay diferentes URLs de importación. Aquí usamos [unpkg](https://unpkg.com) y [jsDelivr](https://jsdelivr.com) como ejemplo. También puede utilizar otros proveedores CDN.

::: code-group

```html [unpkg]
<head>
  <!-- Import style -->
  <link rel="stylesheet" href="//unpkg.com/element-plus/dist/index.css" />
  <!-- Import Vue 3 -->
  <script src="//unpkg.com/vue@3"></script>
  <!-- Import component library -->
  <script src="//unpkg.com/element-plus"></script>
</head>
```

```html [jsDelivr]
<head>
  <!-- Import style -->
  <link
    rel="stylesheet"
    href="//cdn.jsdelivr.net/npm/element-plus/dist/index.css"
  />
  <!-- Import Vue 3 -->
  <script src="//cdn.jsdelivr.net/npm/vue@3"></script>
  <!-- Import component library -->
  <script src="//cdn.jsdelivr.net/npm/element-plus"></script>
</head>
```

:::

::: consejo

Recomendamos usar CDN para importar Element Plus. Empleándolo podrá bloquear la versión en la dirección del enlace, y no verse afectado por actualizaciones incompatibles cuando Element Plus se actualice en el futuro. Por favor, consulte [unpkg.com](https://unpkg.com) para ver cómo fijar una determinada versión.

Due to the limitations of native HTML parsing behavior, single-closed tags may cause some exceptions, so please use double-closed tags, [reference](https://vuejs.org/guide/essentials/component-basics.html#in-dom-template-parsing-caveats)

```html
<!-- examples -->
<el-table>
  <el-table-column></el-table-column>
  <el-table-column></el-table-column>
</el-table>
```

:::

## Hello World

Con CDN, podemos usar Element Plus fácilmente para escribir una página de Hola Mundo. [Online Demo](https://codepen.io/iamkun/pen/YzWMaVr)

<iframe height="469" style="width: 100%;" scrolling="no" title="YzWMaVr" src="https://codepen.io/iamkun/embed/YzWMaVr?height=469&theme-id=light&default-tab=html,result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/iamkun/pen/YzWMaVr'>YzWMaVr</a> by iamkun
  (<a href='https://codepen.io/iamkun'>@iamkun</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

Si se ha instalado a través del gestor de paquetes y quiere usarlo con una herramienta de empaquetado, por favor lea la siguiente sección: [Inicio rápido](/en-US/guide/quickstart).
