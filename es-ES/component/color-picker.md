---
title: ColorPicker
lang: es-ES
---

# ColorPicker

ColorPicker es un selector de color que soporta varios formatos de color.

## Uso básico

:::demo ColorPicker requiere que una variable de tipo cadena esté vinculada al v-model.

color-picker/basic

:::

## Alfa

:::demo ColorPicker soporta la selección de canales alfa. Para activar la selección alfa, simplemente añada el atributo `show-alpha`.

color-picker/alpha

:::

## Colores predefinidos

:::demo ColorPicker soporta opciones de color predefinidas

color-picker/predefined-color

:::

## Tamaños

:::demo

color-picker/sizes

:::

## API

### Atributos

| Nombre                      | Descripción                                                                                        | Tipo                                                                                                           | Por defecto                                                                   |
| --------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| model-value / v-model       | valor enlazado                                                                                     | ^[string]                                                                                                      | —                                                                             |
| disabled                    | especifica si se deshabilita el ColorPicker                                                        | ^[boolean]                                                                                                     | false                                                                         |
| clearable ^(2.13.1)         | si desea mostrar el botón de borrar                                                                | ^[boolean]                                                                                                     | true                                                                          |
| size                        | tamaño del ColorPicker                                                                             | ^[enum]`'large' \| 'default' \| 'small'`                                                                     | —                                                                             |
| show-alpha                  | específica si se muestra el control deslizante para el valor alfa                                  | ^[boolean]                                                                                                     | false                                                                         |
| color-format                | formato de color del `v-model`                                                                     | ^[enum]`'rgb' \| 'prgb' \| 'hex' \| 'hex3' \| 'hex4' \| 'hex6' \| 'hex8' \| 'name' \| 'hsl' \| 'hsv'` | ^[enum]`'hex' (when show-alpha is false) \| 'rgb' (when show-alpha is true)` |
| popper-class                | nombre de clase para el dropdown del ColorPicker                                                   | ^[string] / ^[object]                                                                                          | ''                                                                            |
| popper-style ^(2.11.4)      | custom style for ColorPicker's dropdown                                                            | ^[string] / ^[object]                                                                                          | —                                                                             |
| predefine                   | opciones de colores predefinidas                                                                   | ^[array]`string[]`                                                                                             | —                                                                             |
| validate-event              | si se activa la validación del formulario                                                          | ^[boolean]                                                                                                     | true                                                                          |
| tabindex                    | ColorPicker tabindex                                                                               | ^[string] / ^[number]                                                                                          | 0                                                                             |
| aria-label ^(a11y) ^(2.7.2) | ColorPicker aria-label                                                                             | ^[string]                                                                                                      | —                                                                             |
| empty-values ^(2.10.3)      | empty values of component, [see config-provider](./config-provider.md#empty-values-configurations) | ^[array]                                                                                                       | —                                                                             |
| value-on-clear ^(2.10.3)    | clear return value, [see config-provider](./config-provider.md#empty-values-configurations)        | ^[string] / ^[number] / ^[boolean] / ^[Function]                                                               | —                                                                             |
| id                          | ColorPicker id                                                                                     | ^[string]                                                                                                      | —                                                                             |
| teleported ^(2.7.2)         | whether color-picker popper is teleported to the body                                              | ^[boolean]                                                                                                     | true                                                                          |
| label ^(a11y) ^(deprecated) | ColorPicker aria-label                                                                             | ^[string]                                                                                                      | —                                                                             |
| persistent ^(2.10.5)        | when color-picker inactive and persistent is false, the color panel will be destroyed              | ^[boolean]                                                                                                     | true                                                                          |
| append-to ^(2.10.5)         | which element the color-picker panel appends to                                                    | ^[CSSSelector] / ^[HTMLElement]                                                                                | -                                                                             |

### Eventos

| Nombre          | Descripción                                     | Tipo                                        |
| --------------- | ----------------------------------------------- | ------------------------------------------- |
| change          | se dispara cuando el valor del input cambia     | ^[Function]`(value: string) => void`     |
| active-change   | se dispara cuando el actual color activo cambia | ^[Function]`(value: string) => void`     |
| focus ^(2.4.0)  | triggers when Component focuses                 | ^[Function]`(event: FocusEvent) => void` |
| blur ^(2.4.0)   | triggers when Component blurs                   | ^[Function]`(event: FocusEvent) => void` |
| clear ^(2.13.1) | triggers when the clear button is clicked       | ^[Function]`() => void`                  |

### Expuesto

| Nombre          | Descripción                        | Tipo                       |
| --------------- | ---------------------------------- | -------------------------- |
| color           | objeto de color actual             | ^[object]`Color`           |
| show ^(2.3.3)   | mostrar manualmente ColorPicker    | ^[Function]`() => void` |
| hide ^(2.3.3)   | ocultar manualmente el ColorPicker | ^[Function]`() => void` |
| focus ^(2.3.13) | focus the picker element           | ^[Function]`() => void` |
| blur ^(2.3.13)  | blur the picker element            | ^[Function]`() => void` |
