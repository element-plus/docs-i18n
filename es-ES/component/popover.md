---
title: Popover
lang: es-ES
---

# Popover

## Placement

Popover has 9 placements.

:::demo Use attribute `content` to set the display content when hover. The attribute `placement` determines the position of the Popover. Its value is `[orientation]-[alignment]` with four orientations `top`, `left`, `right`, `bottom` and three alignments `start`, `end`, `null`, and the default alignment is null. Take `placement="left-end"` for example, Popover will display on the left of the element which you are hovering and the bottom of the Popover aligns with the bottom of the element.

popover/placement

:::

## Uso básico

Popover is built with `ElTooltip`. Así que para algunos atributos duplicados, por favor consulte la documentación del Tooltip.

:::demo El atributo `trigger` es usado para definir como el popover se dispara: `hover`, `click`, `focus` o `contextmenu`. Si quieres controlarlo manualmente, puedes establecer `:visible`.

popover/basic-usage

:::

## Activación virtual

Like Tooltip, Popover can be triggered by virtual elements, if your use case includes separate the triggering element and the content element, you should definitely use the mechanism, normally we use `#reference` to place our triggering element, with `virtual-ref` API you can set your triggering element anywhere you like, but notice that the triggering element should be an element that accepts `mouse` and `keyboard` event.

:::warning

`v-popover` está a punto de ser obsoleta, por favor use `virtual-ref` como alternativa.

:::

:::demo

popover/virtual-triggering

:::

## Contenido rico

Otros componentes/elementos pueden ser anidados en el popover. A continuación se muestra un ejemplo de tabla anidada.

:::demo Reemplaza el atributo `content` con un default `slot`.

popover/nested-information

:::

## Operación anidada

Por supuesto, puede anidar otras operaciones. Es más ligero que usar un dialog.

:::demo

popover/nested-operation

:::

## Directivas

Aún puede usar popover en la forma de directiva, pero esto **no es recomendable**, ya que esto hace que su aplicación sea complicada, puede referirse la Activación virtual para más información.

:::demo

popover/directive-usage

:::

## API

### Atributos

| Nombre                             | Descripción                                                                                                                                                                           | Tipo                                                                                                                                                                                   | Default                                                                    |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| trigger                            | how the popover is triggered, not valid in controlled mode                                                                                                                            | ^[enum]`'click' \| 'focus' \| 'hover' \| 'contextmenu'` / ^[array]`Array<'click' \| 'focus' \| 'hover' \| 'contextmenu'>`                                                  | hover                                                                      |
| trigger-keys ^(2.9.8)              | When you click the mouse to focus on the trigger element, you can define a set of keyboard codes to control the display of popover through the keyboard, not valid in controlled mode | ^[Array]                                                                                                                                                                               | ['Enter','Space']                                                          |
| title                              | título del popover                                                                                                                                                                    | ^[string]                                                                                                                                                                              | —                                                                          |
| effect                             | Popover tiene dos temas: `dark` y `light`                                                                                                                                             | ^[enum]`'dark' \| 'light'` / ^[string]                                                                                                                                                | light                                                                      |
| content                            | contenido del popover, puede ser sustituido por un default `slot`                                                                                                                     | ^[string]                                                                                                                                                                              | ''                                                                         |
| width                              | ancho del popover                                                                                                                                                                     | ^[string] / ^[number]                                                                                                                                                                  | 150                                                                        |
| placement                          | posición del popover                                                                                                                                                                  | ^[enum]`'top' \| 'top-start' \| 'top-end' \| 'bottom' \| 'bottom-start' \| 'bottom-end' \| 'left' \| 'left-start' \| 'left-end' \| 'right' \| 'right-start' \| 'right-end'` | bottom                                                                     |
| disabled                           | si el popover está deshabilitado                                                                                                                                                      | ^[boolean]                                                                                                                                                                             | false                                                                      |
| visible / v-model:visible          | si el popover está visible                                                                                                                                                            | ^[boolean] / ^[null]                                                                                                                                                                   | null                                                                       |
| offset                             | popover offset, `Popover` is built with `Tooltip`, offset of `Popover` is `undefined`, but offset of `Tooltip` is 12                                                                  | ^[number]                                                                                                                                                                              | undefined                                                                  |
| transition                         | popover transition animation, the default is el-fade-in-linear                                                                                                                        | ^[string]                                                                                                                                                                              | —                                                                          |
| show-arrow                         | si una flecha del tooltip es mostrada o no. Para obtener más información, consulte [ElPopper](https://github.com/element-plus/element-plus/tree/dev/packages/components/popper)       | ^[boolean]                                                                                                                                                                             | true                                                                       |
| popper-options                     | parámetros para [popper.js](https://popper.js.org/docs/v2/)                                                                                                                           | ^[object]                                                                                                                                                                              | `{modifiers: [{name: 'computeStyles',options: {gpuAcceleration: false}}]}` |
| popper-class                       | nombre de clase personalizada para el componente                                                                                                                                      | ^[string]                                                                                                                                                                              | —                                                                          |
| popper-style                       | estilo personalizado para el popover                                                                                                                                                  | ^[string] / ^[object]                                                                                                                                                                  | —                                                                          |
| show-after                         | delay of appearance, in millisecond, not valid in controlled mode                                                                                                                     | ^[number]                                                                                                                                                                              | 0                                                                          |
| hide-after                         | delay of disappear, in millisecond, not valid in controlled mode                                                                                                                      | ^[number]                                                                                                                                                                              | 200                                                                        |
| auto-close                         | timeout in milliseconds to hide tooltip, not valid in controlled mode                                                                                                                 | ^[number]                                                                                                                                                                              | 0                                                                          |
| tabindex                           | [tabindex](https://developer.mozilla.org/es/docs/Web/HTML/Global_attributes/tabindex) del Popover                                                                                     | ^[number] / ^[string]                                                                                                                                                                  | 0                                                                          |
| teleported                         | si el desplegable del popover se teletransporta al body                                                                                                                               | ^[boolean]                                                                                                                                                                             | true                                                                       |
| append-to ^(2.9.10)                | which element the popover CONTENT appends to                                                                                                                                          | ^[CSSSelector] / ^[HTMLElement]                                                                                                                                                        | body                                                                       |
| persistent                         | cuando el popover esté inactivo y `persistent` sea `false`, el popover será destruido                                                                                                 | ^[boolean]                                                                                                                                                                             | true                                                                       |
| virtual-triggering                 | Indicates whether virtual triggering is enabled                                                                                                                                       | ^[boolean]                                                                                                                                                                             | —                                                                          |
| virtual-ref                        | Indicates the reference element to which the popover is attached                                                                                                                      | ^[HTMLElement]                                                                                                                                                                         | —                                                                          |
| [tooltip](./tooltip.md#attributes) | Inherits all attributes from Tooltip                                                                                                                                                  | —                                                                                                                                                                                      | —                                                                          |

### Slots

| Nombre    | Descripción                                                                     | Type                             |
| --------- | ------------------------------------------------------------------------------- | -------------------------------- |
| default   | content of popover, version ^(2.13.4) and later can receive the hide parameter. | ^[object]`{hide: () => void}` |
| reference | HTML element that triggers popover, only a single root element is accepted      | -                                |

### Eventos

| Name         | Descripción                                         | Type                       |
| ------------ | --------------------------------------------------- | -------------------------- |
| show         | se dispara cuando se muestra el popover             | ^[Function]`() => void` |
| before-enter | se dispara cuando la transición de entrada comienza | ^[Function]`() => void` |
| after-enter  | se dispara cuando la transición de entrada termina  | ^[Function]`() => void` |
| hide         | se dispara cuando se oculta el popover              | ^[Function]`() => void` |
| before-leave | se dispara cuando la transición de salida comienza  | ^[Function]`() => void` |
| after-leave  | se dispara cuando la transición de salida termina   | ^[Function]`() => void` |

### Exposes

| Name | Description  | Tipo                       |
| ---- | ------------ | -------------------------- |
| hide | hide popover | ^[Function]`() => void` |
