---
title: Slider
lang: es-ES
---

# Slider

Desliza el slider dentro de un rango fijo.

## Uso básico

El valor actual se muestra cuando se inicia el arrastre del slider.

:::demo Personalice el valor inicial del slider configurando el valor vinculado.

slider/basic-usage

:::

## Valores discretos

Las opciones pueden ser discretas.

:::demo Configure el tamaño del paso con el atributo `step`. Puede visualizar los puntos de ruptura configurando el atributo `show-stops`.

slider/discrete-values

:::

## Slider con input

Establecer valor a través de una casilla de entrada.

:::demo Establece el atributo `show-input` para mostrar un cuadro de entrada a la derecha.

slider/slider-with-input-box

:::

## Tamaños

:::demo

slider/sizes

:::

## Posición

Puede personalizar el posicionamiento del tooltip.

:::demo

slider/placement

:::

## Selección de rangos

La selección de un rango de valores es soportado.

:::demo Configurando el atributo `range` activa el modo de rango, donde el valor de enlace es un arreglo formado por dos valores límites.

slider/range-selection

:::

## Modo Vertical

:::demo Configurando el atributo `vertical` a `true` habilita el modo vertical. En modo vertical, se requiere el atributo `height`.

slider/vertical-mode

:::

## Mostrar marcas

:::demo Use el atributo `marks` para mostrar marcas en el slider.

slider/show-marks

:::

## Restrict value ^(2.13.6)

:::demo Set `step="mark"` to restrict the slider value to marks.

slider/restrict-value

:::

## API

### Atributos

| Nombre                      | Descrición                                                                                                                                          | Tipo                                                                                                                                                                                   | Default |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| model-value / v-model       | valor vinculado                                                                                                                                     | ^[number] / ^[array]`number[]`                                                                                                                                                         | 0       |
| min                         | valor mínimo                                                                                                                                        | ^[number]                                                                                                                                                                              | 0       |
| max                         | valor máximo                                                                                                                                        | ^[number]                                                                                                                                                                              | 100     |
| disabled                    | si el Slider esta deshabitado                                                                                                                       | ^[boolean]                                                                                                                                                                             | false   |
| step                        | step size, can be a number or `'mark'` ^(2.13.6) to restrict values to marks. When set to `'mark'`, the `marks` attribute must be set               | ^[number] / ^[string]`'mark'`                                                                                                                                                          | 1       |
| show-input                  | whether to display an input box, works when `range` is false and `step` is not `'mark'`                                                             | ^[boolean]                                                                                                                                                                             | false   |
| show-input-controls         | si se muestran los botones de control cuando`show-input`es true                                                                                     | ^[boolean]                                                                                                                                                                             | true    |
| size                        | el tamaño del envoltorio del slider no funcionará en modo vertical                                                                                  | ^[enum]`'' \| 'large' \| 'default' \| 'small'`                                                                                                                                      | default |
| input-size                  | tamaño del input, cuando se establece `size`, el valor por defecto es `size`                                                                        | ^[enum]`'' \| 'large' \| 'default' \| 'small'`                                                                                                                                      | default |
| show-stops                  | si se muestran los puntos de ruptura (breakpoints)                                                                                                  | ^[boolean]                                                                                                                                                                             | false   |
| show-tooltip                | si se muestra el valor en un tooltip                                                                                                                | ^[boolean]                                                                                                                                                                             | true    |
| format-tooltip              | formato para mostrar el valor del tooltip                                                                                                           | ^[Function]`(value: number) => number \| string`                                                                                                                                   | —       |
| range                       | si se usaran un rango                                                                                                                               | ^[boolean]                                                                                                                                                                             | false   |
| vertical                    | modo vertical                                                                                                                                       | ^[boolean]                                                                                                                                                                             | false   |
| height                      | slider height, required in vertical mode                                                                                                            | ^[string]                                                                                                                                                                              | —       |
| aria-label ^(a11y) ^(2.7.2) | native `aria-label` attribute                                                                                                                       | ^[string]                                                                                                                                                                              | —       |
| range-start-label           | cuando `range` es true, etiqueta el lector de pantalla hacia el inicio del rango                                                                    | ^[string]                                                                                                                                                                              | —       |
| range-end-label             | cuando `range` es true, etiqueta el lector de pantalla hacia el final del rango                                                                     | ^[string]                                                                                                                                                                              | —       |
| format-value-text           | formato para mostrar el atributo `aria-valuenow` para lectores de pantalla                                                                          | ^[Function]`(value: number) => string`                                                                                                                                              | —       |
| tooltip-class               | nombre personalizado de clase para el tooltip                                                                                                       | ^[string]                                                                                                                                                                              | —       |
| placement                   | posición del Tooltip                                                                                                                                | ^[enum]`'top' \| 'top-start' \| 'top-end' \| 'bottom' \| 'bottom-start' \| 'bottom-end' \| 'left' \| 'left-start' \| 'left-end' \| 'right' \| 'right-start' \| 'right-end'` | top     |
| marks                       | marcas, tipo de clave debe ser `number` y debe estar en intervalo cerrado `[min, max]`, cada marca puede tener estilo personalizado                 | ^[object]`SliderMarks`                                                                                                                                                                 | —       |
| validate-event              | si se debe activar la validación del formulario                                                                                                     | ^[boolean]                                                                                                                                                                             | true    |
| persistent ^(2.9.5)         | when slider tooltip inactive and `persistent` is `false` , tooltip will be destroyed. `persistent` always be `false` when `show-tooltip` is `false` | ^[boolean]                                                                                                                                                                             | true    |
| label ^(a11y) ^(deprecated) | native `aria-label` attribute                                                                                                                       | ^[string]                                                                                                                                                                              | —       |

### Eventos

| Nombre | Descripción                                                                                                                         | Type                                                     |
| ------ | ----------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- |
| change | se dispara cuando el valor cambia (si el ratón está comenzando el arrastre este evento sólo se disparara cuando se suelte el ratón) | ^[Function]`(value: Arrayable<number>) => void` |
| input  | se dispara cuando los datos cambian (se emitirá en tiempo real durante el deslizamiento)                                            | ^[Function]`(value: Arrayable<number>) => void` |

## Type Declarations

<details>
  <summary>Show declarations</summary>

```ts
type SliderMarks = Record<number, string | { style: CSSProperties; label: any }>
type Arrayable<T> = T | T[]
```

</details>
