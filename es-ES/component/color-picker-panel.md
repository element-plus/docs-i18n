---
title: ColorPickerPanel
lang: es-ES
---

# ColorPickerPanel ^(beta)

`ColorPickerPanel` is the core component of `ColorPicker`.

## Uso básico

:::demo ColorPickerPanel requires a string typed variable to be bound to v-model.

color-picker-panel/basic

:::

## Alfa

:::demo ColorPickerPanel supports alpha channel selecting. To activate alpha selecting, just add the `show-alpha` attribute.

color-picker-panel/alpha

:::

## Colores predefinidos

:::demo ColorPickerPanel supports predefined color options

color-picker-panel/predefined-color

:::

## Border

By default the color-picker-panel is bordered but in some case you don't want it.

:::demo

color-picker-panel/border

:::

## Deshabilitar

The `disabled` attribute determines if the color picker is fully disabled.

:::demo

color-picker-panel/disabled

:::

## API

### Personalizable

| Nombre                                                                        | Descripción                                                       | Parámetros                                                                                                                                                | Valore por defecto                                                                                                               |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| model-value / v-model                                                         | valor vinculado                                                   | ^[string]                                                                                             | —                                                                                                                                |
| border                                                                        | whether the color picker panel is bordered                        | ^[boolean]                                                                                            | true                                                                                                                             |
| disabled                                                                      | whether to disable the color picker                               | ^[boolean]                                                                                            | false                                                                                                                            |
| show-alpha                                                                    | específica si se muestra el control deslizante para el valor alfa | ^[boolean]                                                                                            | false                                                                                                                            |
| color-format                                                                  | formato de color del <code>v-model</code>                         | ^[enum]`'rgb' \| 'prgb' \| 'hex' \| 'hex3' \| 'hex4' \| 'hex6' \| 'hex8' \| 'name' \| 'hsl' \| 'hsv'` | ^[enum]`'hex' (when show-alpha is false) \| 'rgb' (when show-alpha is true)` |
| predefine                                                                     | opciones de colores predefinidas                                  | ^[array]`string[]`                                                                                    | —                                                                                                                                |
| validate-event ^(2.11.7)   | si se debe activar la validación del formulario                   | ^[boolean]                                                                                            | true                                                                                                                             |
| hue-slider-class ^(2.13.6) | class names will be passed to hue-slider                          | ^[object]`string \| string[] \| Record<string, boolean>`                                              | —                                                                                                                                |
| hue-slider-style ^(2.13.6) | styles will be passed to hue-slider                               | ^[string] / ^[object]`StyleValue`                 | —                                                                                                                                |

### Slots

| Nombre | Descripción                       |
| ------ | --------------------------------- |
| footer | content to append after the Input |

### Expuesto

| Nombre                                                              | Descripción            | Parámetros                                                                   |
| ------------------------------------------------------------------- | ---------------------- | ---------------------------------------------------------------------------- |
| color                                                               | objeto de color actual | ^[object]`Color`         |
| inputRef                                                            | custom input ref       | ^[object]`InputInstance` |
| update ^(2.11.4) | update sub components  | ^[Function]`() => void`  |
