---
title: Input
lang: es-ES
---

# Input Number

Input de valores numéricos con un rango personalizable.

## Uso básico

:::demo Vincule una variable con `v-model` en el elemento `<el-input-number>` y estará listo.

input-number/basic

:::

:::tip

Si se introduce una cadena no válida en el input, el valor de entrada emitirá `NaN` a la capa superior como resultado de error

:::

## Deshabilitar

:::demo El atributo `disabled` acepta un valor `boolean`, y si el valor es `true`, el componente queda deshabilitado. Si necesita controlar el valor dentro de un rango, puede añadir un atributo `min` para establecer el valor mínimo y un valor `max` para establecer el valor máximo. By default, the minimum value is `Number.MIN_SAFE_INTEGER`.

input-number/disabled

:::

## Steps

Le permite definir el nivel de incremento de los saltos.

:::demo Añada el atributo `step` para establecer el salto.

input-number/steps

:::

## Step estricto

:::demo El atributo `step-strictly` acepta un valor `boolean`. si este atributo es `true`, el valor de entrada solo puede ser múltiplo de step.

input-number/step-strictly

:::

## Precisión

:::demo El atributo `precision` aplica precisión al valor del value.

input-number/precision

:::

:::tip

El valor de `precision` debe ser un número entero positivo que no debe ser inferior a los decimales del `step`.

:::

## Tamaño

Use el atributo `size` para aplicar tamaños adicionales con `large` o `small`.

:::demo

input-number/size

:::

## Posición de los controles

:::demo Establezca `controls-position` para decidir la posición de los botones de control.

input-number/controlled

:::

## Custom Icon ^(2.6.3)

:::demo Use `decrease-icon` and `increase-icon` to set custom icons.

input-number/custom

:::

## With prefix and suffix ^(2.8.4)

:::demo Use the prefix and suffix named slots.

input-number/with-prefix-suffix

:::

:::tip

For precision purposes, the input number is limited from [Number.MIN_SAFE_INTEGER](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/MIN_SAFE_INTEGER) to [Number.MAX_SAFE_INTEGER](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/MAX_SAFE_INTEGER).

:::

## Formatter ^(2.14.0)

Display the value with `formatter`, and typically use `parser` alongside it.

When `formatter` is set, the inner input `type` changes to `text`, which allows non-numeric characters to be entered. Internally, the component processes input with `Number.parseFloat`: when parsing succeeds, the parsed number is written to `model-value`; when parsing returns `NaN`, `model-value` is set to `null`.

:::demo

input-number/formatter

:::

## API

### Atributos

| Nombre                        | Descripción                                              | Tipo                                           | Por defecto               |
| ----------------------------- | -------------------------------------------------------- | ---------------------------------------------- | ------------------------- |
| model-value / v-model         | valor vinculado                                          | ^[number] / ^[null]                            | —                         |
| min                           | el valor mínimo permitido                                | ^[number]                                      | Number.MIN_SAFE_INTEGER |
| max                           | el valor maximo permitido                                | ^[number]                                      | Number.MAX_SAFE_INTEGER |
| step                          | incremento (salto)                                       | ^[number]                                      | 1                         |
| step-strictly                 | si el valor del input puede ser solo un múltiplo de step | ^[boolean]                                     | false                     |
| precision                     | precisión del valor del input                            | ^[number]                                      | —                         |
| size                          | tamaño del componente                                    | ^[enum]`'large' \| 'default' \| 'small'`     | default                   |
| readonly ^(2.2.16)            | igual que `readonly` en el input nativo                  | ^[boolean]                                     | false                     |
| disabled                      | si el componente está deshabilitado                      | ^[boolean]                                     | false                     |
| controls                      | si desea activar los botones de control                  | ^[boolean]                                     | true                      |
| controls-position             | posición de los botones de control                       | ^[enum]`'' \| 'right'`                        | —                         |
| name                          | como `name` en el input nativo                           | ^[string]                                      | —                         |
| aria-label ^(a11y) ^(2.7.2)   | same as `aria-label` in native input                     | ^[string]                                      | —                         |
| placeholder                   | igual que `placeholder` en input nativo                  | ^[string]                                      | —                         |
| id                            | igual que `id` en el input nativo                        | ^[string]                                      | —                         |
| value-on-clear ^(2.2.0)       | el valor a establecerse cuando el input se limpia        | ^[number] / ^[null] / ^[enum]`'min' \| 'max'` | —                         |
| validate-event                | si se debe lanzar la validación de formulario            | ^[boolean]                                     | true                      |
| label ^(a11y) ^(deprecated)   | same as `aria-label` in native input                     | ^[string]                                      | —                         |
| inputmode ^(2.10.3)           | same as `inputmode` in native input                      | ^[string]                                      | —                         |
| align ^(2.10.5)               | alignment for the inner input text                       | ^[enum]`'left' \| 'center' \| 'right'`       | 'center'                  |
| disabled-scientific ^(2.10.5) | disables input of scientific notation (e.g. 'e')         | ^[boolean]                                     | false                     |
| tabindex ^(2.14.0)            | same as `tabindex` in native input                       | ^[string] / ^[number]                          | 0                         |
| formatter ^(2.14.0)           | specifies the format of the value presented in the input | ^[Function]`(value: string) => string`      | —                         |
| parser ^(2.14.0)              | specifies the value extracted from the formatted input   | ^[Function]`(value: string) => string`      | —                         |

### Slots

| Nombre                 | Descripción                           |
| ---------------------- | ------------------------------------- |
| decrease-icon ^(2.6.3) | custom input box button decrease icon |
| increase-icon ^(2.6.3) | custom input box button increase icon |
| prefix ^(2.8.4)        | content as Input prefix               |
| suffix ^(2.8.4)        | content as Input suffix               |

### Eventos

| Nombre | Descripción                          | Tipo                                                                                         |
| ------ | ------------------------------------ | -------------------------------------------------------------------------------------------- |
| change | se dispara cuando el valor cambia    | ^[Function]`(currentValue: number \| undefined, oldValue: number \| undefined) => void` |
| blur   | se dispara cuando se pierde el foco  | ^[Function]`(event: FocusEvent) => void`                                                  |
| focus  | se dispara cuando se obtiene el foco | ^[Function]`(event: FocusEvent) => void`                                                  |

### Expuesto

| Name  | Description                          | Tipo                       |
| ----- | ------------------------------------ | -------------------------- |
| focus | coloca el foco en el elemento actual | ^[Function]`() => void` |
| blur  | quita el foco del elemento actual    | ^[Function]`() => void` |
