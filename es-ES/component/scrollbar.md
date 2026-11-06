---
title: Scrollbar
lang: es-ES
---

# Scrollbar

Se utiliza para reemplazar la barra de desplazamiento nativa del navegador.

## Uso básico

:::demo Use la propiedad `height` para establecer la altura de la barra de desplazamiento, o si no se establece, se adapta de acuerdo a la altura del contenedor padre.

scrollbar/basic-usage

:::

## Desplazamiento horizontal

:::demo Cuando el ancho del elemento es mayor que el ancho de la barra de desplazamiento, se muestra la barra de desplazamiento horizontal.

scrollbar/horizontal-scroll

:::

## Scroll masks ^(2.14.8)

Use `mask` to indicate that more content can be scrolled to above, below, to the left, or to the right of the viewport. Masks are disabled by default.

| Valor      | Behavior                                                    |
| ---------- | ----------------------------------------------------------- |
| `false`    | Disable all masks (default).                                |
| `true`     | Enable all four masks, according to the available overflow. |
| `'top'`    | Enable only the top mask.                                   |
| `'bottom'` | Enable only the bottom mask.                                |
| `'left'`   | Enable only the left mask.                                  |
| `'right'`  | Enable only the right mask.                                 |

```vue
<template>
  <el-scrollbar height="240px" mask />
  <el-scrollbar height="240px" mask="top" />
  <el-scrollbar height="240px" mask="bottom" />
  <el-scrollbar mask="left" />
  <el-scrollbar mask="right" />
</template>
```

:::demo Scroll vertically or horizontally and change the mask mode. Each enabled mask appears only while there is more content in its direction. It disappears when that edge is reached. Masks stay hidden on axes without overflow; when both axes overflow, all four masks can appear together.

scrollbar/scroll-mask

:::

Masks fade in and out over `200ms` by default, using `--el-transition-duration-fast`. The animation is disabled when the user prefers reduced motion. Masks do not block pointer events or cover scrollbar controls, and also work with `native`.

`left` and `right` refer to the physical edges of the viewport, including when the scroll container uses `direction: rtl`.

The `distance` attribute only affects the `end-reached` event; it does not change when masks appear. When using `noresize`, call `update()` after changing the content or container size to refresh the masks.

### Customize masks

Use the following CSS variables on the Scrollbar component to customize each mask:

| CSS variable                        | Descripción                | Por defecto          |
| ----------------------------------- | -------------------------- | -------------------- |
| `--el-scrollbar-top-mask-height`    | Height of the top mask.    | `40px`               |
| `--el-scrollbar-bottom-mask-height` | Height of the bottom mask. | `40px`               |
| `--el-scrollbar-left-mask-width`    | Width of the left mask.    | `40px`               |
| `--el-scrollbar-right-mask-width`   | Width of the right mask.   | `40px`               |
| `--el-scrollbar-top-mask-color`     | Color of the top mask.     | `var(--el-bg-color)` |
| `--el-scrollbar-bottom-mask-color`  | Color of the bottom mask.  | `var(--el-bg-color)` |
| `--el-scrollbar-left-mask-color`    | Color of the left mask.    | `var(--el-bg-color)` |
| `--el-scrollbar-right-mask-color`   | Color of the right mask.   | `var(--el-bg-color)` |

The default color follows the light or dark theme. Set the mask colors to match the container background when using a custom background. The example above sets the vertical mask heights and horizontal mask widths to `48px`.

## Altura máxima

:::demo La barra de desplazamiento sólo se muestra cuando la altura del elemento excede la altura máxima.

scrollbar/max-height

:::

## Desplazamiento manual

:::demo Use los métodos `setScrollTop` y `setScrollLeft` para controlar manualmente la barra de desplazamiento.

scrollbar/manual-scroll

:::

## Infinite scroll ^(2.10.0)

:::demo `end-reached` is triggered when the scrollbar reaches the end. It can be used as an infinite scroll.

scrollbar/infinite-scroll

:::

## API

### Atributos

| Nombre                            | Descripción                                                                                                                                     | Tipo                                                                  | Por defecto |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- | ----------- |
| height                            | altura de la barra de desplazamiento                                                                                                            | ^[string] / ^[number]                                                 | —           |
| max-height                        | altura máxima de la barra de desplazamiento                                                                                                     | ^[string] / ^[number]                                                 | —           |
| native                            | si usar el estilo nativo de la barra de desplazamiento                                                                                          | ^[boolean]                                                            | false       |
| wrap-style                        | estilo del contenedor envoltorio                                                                                                                | ^[string] / ^[object]`CSSProperties \| CSSProperties[] \| string[]` | —           |
| wrap-class                        | clase del contenedor envoltorio                                                                                                                 | ^[string]                                                             | —           |
| view-style                        | estilo de la vista                                                                                                                              | ^[string] / ^[object]`CSSProperties \| CSSProperties[] \| string[]` | —           |
| view-class                        | clase de la vista                                                                                                                               | ^[string]                                                             | —           |
| noresize                          | no responder a los cambios de tamaño del contenedor, si el tamaño del contenedor no cambia, es mejor configurarlo para optimizar el rendimiento | ^[boolean]                                                            | false       |
| tag                               | etiqueta de elemento de la vista                                                                                                                | ^[string]                                                             | div         |
| always                            | si mostrar siempre la barra de desplazamiento                                                                                                   | ^[boolean]                                                            | false       |
| mask ^(2.14.8)                    | Gradient masks: `true` for all edges, a direction for one edge, and `false` to disable                                                          | ^[boolean] / ^[enum]`'top' \| 'bottom' \| 'left' \| 'right'`       | false       |
| min-size                          | tamaño mínimo de la barra de desplazamiento                                                                                                     | ^[number]                                                             | 20          |
| id ^(2.4.0)                       | id of view                                                                                                                                      | ^[string]                                                             | —           |
| role ^(2.4.0) ^(a11y)             | role of view                                                                                                                                    | ^[string]                                                             | —           |
| aria-label ^(2.4.0) ^(a11y)       | aria-label of view                                                                                                                              | ^[string]                                                             | —           |
| aria-orientation ^(2.4.0) ^(a11y) | aria-orientation of view                                                                                                                        | ^[enum]`'horizontal' \| 'vertical'`                                  | —           |
| tabindex ^(2.8.3)                 | tabindex of wrap container                                                                                                                      | ^[number] / ^[string]                                                 | —           |
| distance ^(2.10.5)                | trigger end-reached event distance(px)                                                                                                          | ^[number]                                                             | 0           |

### Eventos

| Nombre                | Descripción                                                          | Tipo                                                                           |
| --------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| scroll                | se activa cuando se desplaza, regresa la distancia de desplazamiento | ^[Function]`({ scrollLeft: number, scrollTop: number }) => void`            |
| end-reached ^(2.10.0) | triggers when the end of a scroll is triggered                       | ^[Function]`(direction: 'top' \| 'bottom' \| 'left' \| 'right') => void` |

### Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |

### Expuesto

| Nombre        | Descripción                                                   | Tipo                                                                           |
| ------------- | ------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| handleScroll  | maneja evento de desplazamiento                               | ^[Function]`() => void`                                                     |
| scrollTo      | desplaza a un conjunto particular de coordenadas              | ^[Function]`(options: ScrollToOptions \| number, yCoord?: number) => void` |
| setScrollTop  | Establece distancia hacia la parte superior                   | ^[Function]`(scrollTop: number) => void`                                    |
| setScrollLeft | Establece distancia hacia la izquierda                        | ^[Function]`(scrollLeft: number) => void`                                   |
| update        | actualiza el estado de la barra de desplazamiento manualmente | ^[Function]`() => void`                                                     |
| wrapRef       | referencia de la barra de desplazamiento                      | ^[object]`Ref<HTMLDivElement>`                                           |
