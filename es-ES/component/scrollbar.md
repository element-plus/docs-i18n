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
