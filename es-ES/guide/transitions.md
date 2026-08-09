---
title: Built-in Transitions
lang: es-ES
---

# Transición incorporada

Puede usar directamente las transiciones incorporadas en Element. Antes de eso, por favor lea los [documentos de transición](https://vuejs.org/guide/built-ins/transition.html).

## Fade

:::demo Tenemos dos efectos de fading: `el-fade-in-linear` y `el-fade-in`.

transitions/fade

:::

## Zoom

:::demo `el-zoom-in-left`, `el-zoom-in-center`, `el-zoom-in-top` and `el-zoom-in-bottom` are provided.

transitions/zoom

:::

## Colapsar

Para efectos de colapsado use el componente `el-collapse-transition`.

:::demo

transitions/collapse

:::

## Importar a petición

```ts [main.ts]
// collapse
import { ElCollapseTransition } from 'element-plus'
// fade/zoom
import 'element-plus/theme-chalk/base.css'
import App from './App.vue'

const app = createApp(App)
app.component(ElCollapseTransition.name, ElCollapseTransition)
```
