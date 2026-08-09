---
title: Skeleton
lang: es-ES
---

# Skeleton

Cuando se cargan los datos, y se necesita una experiencia rica en visualización e interacción para los usuarios finales, se puede elegir `skeleton`.

## Uso básico

El esqueleto básico.

:::demo

skeleton/basic-usage

:::

## Filas configurables

Puede configurar los números de fila usted mismo, para un efecto de renderizado más preciso, el número de fila real renderizado siempre será 1 fila más que el número dado, esto es porque estamos renderizando una fila de títulos con un 33% de ancho de las otras.

:::demo

skeleton/configurable-rows

:::

## Animaciones

Hemos proporcionado una bandera de conmutación indicando si se muestra la animación de carga, llamada `animated` cuando esto es true, todos los hijos de `el-skeleton` mostrarán una animación

:::demo

skeleton/animation

:::

## Plantilla personalizada

Element Plus solo proporciona la plantilla más común, a veces eso podría ser un problema. así que tiene un slot con nombre `template` para hacer ese trabajo.

También hemos proporcionado diferentes tipos de unidad esqueleto que puedes elegir, para obtener información más detallada, por favor desplácese hacia la parte inferior de esta página para ver la descripción de la API. Además, al construir tu propia estructura esquelética personalizada, debería estructurarlas lo más cerca posible del DOM real, que evita que el DOM tenga un efecto de rebote causado por la diferencia de altura.

:::demo

skeleton/customized-template

:::

## Estado de carga

Cuando `Loading` termina, siempre necesitamos mostrar la interfaz real con datos a nuestros usuarios finales. con el atributo `loading` podemos controlar si se muestra el DOM. También puede usar el slot `default` para estructurar el elemento DOM real.

:::demo

skeleton/loading-state

:::

## Renderizando una lista de datos

La mayoría de las veces, el esqueleto se utiliza como indicadores de la representación de una lista de datos que no se han recuperado del servidor todavía, entonces tenemos que crear una lista de esqueleto de la nada para que parezca que se está cargando, con el atributo `count`, se puede controlar el número de estas plantillas que necesita para representar al navegador.

:::tip

No recomendamos procesar mucha interfaz falsa en el navegador, causará problemas de rendimiento y también costará más tiempo destruir el esqueleto. Mantenga `count` tan pequeño como pueda ser para mejorar la experiencia del usuario.

:::

:::demo

skeleton/rendering-with-data

:::

## Evitar el efecto rebotar del renderizado.

A veces la API responde muy rápidamente, cuando eso sucede, el esqueleto solo se renderiza en el DOM y luego tiene que volver a cambiar al DOM real, lo que provoca un destello repentino. Para evitar esto, puede usar el atributo `throttle`.

:::tip

Since ^(2.8.8), the `throttle` attribute supports two values: `number` and `object`. When passing a `number`, it is equivalent to `{leading: xxx}`, controlling the throttling of the skeleton screen display. Of course, you can also control the throttling of the skeleton screen disappearance by passing `{trailing: xxx}`

:::

:::demo

skeleton/avoiding-rendering-bouncing

:::

## Initial rendering loading ^(2.8.8)

When the initial value of loading is true, you can set `throttle: {initVal: true, leading: xxx}` to control the immediate display of the initial skeleton screen without throttling.

:::demo

skeleton/initial-rendering-loading

:::

## Toggle show/hide without rending bouncing ^(2.8.8)

:::tip

You can set `throttle: {initVal: true, leading: xxx, trailing: xxx}` to control the initial display of the skeleton effect and to make the transition of the skeleton more smooth when switching loading states.

:::

Sometimes you want to render the business components more smoothly when loading toggle show or hide. You can use set the `throttle: {leading: xxx, trailing:xxx}` to control the rendering bouncing.

:::demo

skeleton/leading-trailing-without-bouncing

:::

##

## Skeleton API

### Skeleton Attributes

| Nombre   | Descripción                                                                                                                                                                                                                                 | Tipo                                                                              | Por defecto |
| -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | ----------- |
| animated | si se muestra la animación                                                                                                                                                                                                                  | ^[boolean]                                                                        | false       |
| count    | cuántos elementos falsos procesar en el DOM                                                                                                                                                                                                 | ^[number]                                                                         | 1           |
| loading  | si se muestra el DOM real                                                                                                                                                                                                                   | ^[boolean]                                                                        | false       |
| rows     | números de la fila, solo útiles cuando no se ha dado ninguna plantilla de slot                                                                                                                                                              | ^[number]                                                                         | 3           |
| throttle | rendering delay in milliseconds. Numbers represent delayed display, and can also be set to delay hide, for example `{ leading: 500, trailing: 500 }`. When needing to control the initial value of loading, you can set `{ initVal: true }` | ^[number] / ^[object]`{ leading?: number, trailing?: number, initVal?: boolean }` | 0           |

### Skeleton Slots

| Nombre   | Descripción                                       | Tipo                       |
| -------- | ------------------------------------------------- | -------------------------- |
| default  | DOM renderizado real                              | ^[object]`$attrs`          |
| template | contenido como renderizado plantilla de esqueleto | ^[object]`{ key: number }` |

## SkeletonItem API

### SkeletonItem Attributes

| Nombre  | Descripción                                  | Tipo                                                                                                     | Por defecto |
| ------- | -------------------------------------------- | -------------------------------------------------------------------------------------------------------- | ----------- |
| variant | el tipo de esqueleto de procesamiento actual | ^[enum]`'p' \| 'text' \| 'h1' \| 'h3' \| 'caption' \| 'button' \| 'image' \| 'circle' \| 'rect'` | text        |
