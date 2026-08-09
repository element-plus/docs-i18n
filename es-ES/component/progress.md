---
title: Progress
lang: es-ES
---

# Progreso

Progress es usado para mostrar el estado de la operación actual e informar al usuario acerca de esta.

## Barra de progreso lineal

:::demo Use el atributo `percentage` para asignar el porcentaje. Este es **requerido** y tiene que ser un valor entre `0-100`. Puede personalizar el formato de texto configurando `format`.

progress/linear-progress-bar

:::

## Porcentaje interno

En este caso, el porcentaje no necesita espacio adicional.

:::demo El atributo `stroke-width` decide el `width` de la barra de progreso, y usa el atributo `text-inside` para poner la descripción dentro de la misma.

progress/internal-percentage

:::

## Color personalizado

Puede usar `color` para establecer el color de la barra de progreso. acepta string, función o array.

:::demo

progress/custom-color

:::

## Barra de progreso circular

:::demo Puede asignar el atributo `type` como `circle` para usar la barra circular de progreso, y usar el atributo `width` para cambiar el tamaño del círculo.

progress/circular-progress-bar

:::

## Barra de progreso del panel de control

También puede especificar el atributo `type` a `dashboard` para usar la barra de progreso del panel de control.

:::demo

progress/dashboard-progress-bar

:::

## Contenido personalizado

:::demo Use el default slot para añadir contenido personalizado.

progress/customized-content

:::

## Progreso indeterminado

:::demo Use el atributo `indeterminate` para establecer el progreso indeterminado, con `duration` para controlar la duración de la animación.

progress/indeterminate-progress

:::

## Progreso con rayas

:::demo Use el atributo `striped` para establecer el progreso con rayas. Puede usar `striped-flow` para hacer que fluyan los rayos, con `duration` para controlar la duración de la animación.

progress/striped-progress

:::

## API

### Atributos

| Nombre                 | Descripción                                                                                    | Tipo                                                                                                           | Por defecto |
| ---------------------- | ---------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | ----------- |
| percentage ^(required) | percentage                                                                                     | ^[number]`(0-100)`                                                                                             | 0           |
| type                   | el tipo de barra de progreso                                                                   | ^[enum]`'line' \| 'circle' \| 'dashboard'`                                                                   | line        |
| stroke-width           | el ancho de la barra de progreso                                                               | ^[number]                                                                                                      | 6           |
| text-inside            | si colocar el porcentaje dentro de la barra de progreso, solo funciona cuando `type` es 'line' | ^[boolean]                                                                                                     | false       |
| status                 | estado actual de la barra de progreso                                                          | ^[enum]`'success' \| 'exception' \| 'warning'`                                                               | —           |
| indeterminate          | establecer progreso indeterminado                                                              | ^[boolean]                                                                                                     | false       |
| duration               | controlar la duración de la animación del progreso indeterminado o del progreso con rayas      | ^[number]                                                                                                      | 3           |
| color                  | color de fondo de la barra de progreso. Sobreescribe la propiedad `status`                     | ^[string] / ^[function]`(percentage: number) => string` / ^[Array]`{ color: string; percentage: number }[]` | ''          |
| width                  | ancho del canvas que contiene la barra de progreso circular                                    | ^[number]                                                                                                      | 126         |
| show-text              | si mostrar porcentaje                                                                          | ^[boolean]                                                                                                     | true        |
| stroke-linecap         | forma del círculo/dashboard en la ruta final                                                   | ^[enum]`'butt' \| 'round' \| 'square'`                                                                       | round       |
| format                 | formato de texto personalizado                                                                 | ^[Function]`(percentage: number) => string`                                                                 | —           |
| striped ^(2.3.4)       | rayas sobre el color de la barra de progreso                                                   | ^[boolean]                                                                                                     | false       |
| striped-flow ^(2.3.4)  | consigue que fluyan las rayas                                                                  | ^[boolean]                                                                                                     | false       |

### Slots

| Nombre  | Descripción        | Type                              |
| ------- | ------------------ | --------------------------------- |
| default | Customized content | ^[object]`{ percentage: number }` |
