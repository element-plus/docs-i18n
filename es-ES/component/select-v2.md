---
title: Virtualized Select
lang: es-ES
---

# Virtualized Select

:::tip

Este componente todavía está en pruebas, si encuentra algún error o problema, por favor infórmenos en [GitHub](https://github.com/element-plus/element-plus/issues) para que lo arreglemos.

:::

## Fondo

En algunos casos de uso, un selector puede terminar cargando decenas de miles de filas de datos. Renderizar esa cantidad de datos en el DOM podría ser una carga para el navegador, lo que puede resultar en problemas de rendimiento. Para una mejor experiencia de usuario y desarrollador, decidimos añadir este componente.

## Uso Básico

El selector más simple

:::demo

select-v2/basic-usage

:::

## Selección múltiple

El selector básico de selección múltiple con etiquetas

:::demo

select-v2/multiple

:::

## Sizes

:::demo Add `size` attribute to change the size of Select-V2. In addition to the default size, there are two other options: `large`, `small`.

select-v2/size

:::

## Hide extra tags when the selected items are too many

Puede colapsar las etiquetas a un texto usando el atributo `collapse-tags`. Puede comprobarlos cuando el ratón pasa el cursor sobre el texto usando el atributo `collapse-tags-tooltip`.

:::demo

select-v2/hide-extra-tags

:::

## Selección múltiple filtrable

Cuando las opciones son demasiado grandes, puedes usar la opción `filterable` para habilitar la función de filtro para encontrar la opción deseada

:::demo

select-v2/filterable

:::

## Deshabilitar el selector y las opciones de selección

Puede elegir desactivar el selector en sí mismo o la opción.

:::demo

select-v2/disabled

:::

## Grupo de opciones

Podemos agrupar la opción como quiera, siempre y cuando los datos satisfagan el patrón.

:::demo

select-v2/grouping

:::

## Limpiando el selector

Podemos borrar todas las opciones seleccionadas a la vez, también aplicables para una única selección.

:::demo

select-v2/clearable

:::

## Personalizar las opciones de renderizado

Podemos definir nuestra propia plantilla para renderizar la opción en la ventana emergente.

:::demo

select-v2/customized-option

:::

## Header of the dropdown ^(2.5.2)

You can customize the header of the dropdown.

:::demo Use slot to customize the content.

select-v2/custom-header

:::

## Footer of the dropdown ^(2.5.2)

You can customize the footer of the dropdown.

:::demo Use slot to customize the content.

select-v2/custom-footer

:::

## Crear nuevos ítems

Crear y seleccionar nuevos elementos que no están incluidos en las opciones de selección

Al usar el atributo `allow-create`, los usuarios pueden crear nuevos elementos escribiendo en el cuadro de entrada. Tenga en cuenta que para que `allow-create` funcione, `filterable` debe ser `true`. This example also demonstrates `default-first-option`. When this attribute is set to `true`, you can select the first option in the current option list by hitting enter without having to navigate with mouse or arrow keys.

:::tip

Es mejor establecer `:reserve-keyword="false"` cuando se use `allow-create`

:::

:::demo

select-v2/allow-create

:::

## Búsqueda remota

Introduzca palabras clave y datos de búsqueda desde el servidor.

:::demo Establezca el valor de `filterable` y `remote` con `true` para habilitar la búsqueda remota, y deberá pasar el `remote-method`. `remote-method` es una `función` que se llama cuando el valor de entrada cambia, y su parámetro es el valor de entrada actual.

select-v2/remote-search

:::

## Use value-key attribute

when `options.value` is an object, you should set a unique identity key name for value

::: tip

Before ^(2.4.0), `value-key` was used both as the unique value of the selected object and as an alias for the value in `options`. Now `value-key` is only used as the unique value of the selected object, and the alias for the value in options is `props.value`.

:::

:::demo

select-v2/use-valueKey

:::

## Aliases for custom options ^(2.4.2)

When your `options` format is different from the default format, you can customize the alias of the `options` through the `props` attribute

:::demo

select-v2/props

:::

## Custom Tag ^(2.5.0)

You can customize tags.

:::demo Insert customized tags into the slot of `el-select`. `collapse-tags`, `collapse-tags-tooltip`, `max-collapse-tags` will not work.

select-v2/custom-tag

:::

## Custom Loading ^(2.5.2)

Override loading content.

:::demo

select-v2/custom-loading

:::

## Empty Values ^(2.7.0)

If you want to support empty string, please set `empty-values` to `[null, undefined]`.

If you want to change the clear value to `null`, please set `value-on-clear` to `null`.

:::demo

select-v2/empty-values

:::

## Custom Label ^(2.7.4)

You can customize label.

:::demo

select-v2/custom-label

:::

## Custom Width ^(2.9.2)

The width of dropdown box is calculated by default based on the value of `label`. If you customize the dropdown box options through the `default slot`, it is likely that the text displayed in the options is not equal to the value of `label`, resulting in calculation errors. In this case, you can set the `fit-input-width` attribute to a number to fix its width.

:::demo

select-v2/custom-width

:::

## API

### Attributes

| Nombre                                | Descripción                                                                                                                                                                                      | Tipo                                                                                                                                                                                   | Por defecto                                    |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| model-value / v-model                 | binding value                                                                                                                                                                                    | ^[string] / ^[number] / ^[boolean] / ^[object] / ^[array]                                                                                                                              | —                                              |
| options                               | data of the options, the key of `value` and `label` can be customize by `props`                                                                                                                  | ^[array]                                                                                                                                                                               | —                                              |
| [props](#props) ^(2.4.2)              | configuration options, see the following table                                                                                                                                                   | ^[object]                                                                                                                                                                              | —                                              |
| multiple                              | is multiple                                                                                                                                                                                      | ^[boolean]                                                                                                                                                                             | false                                          |
| disabled                              | is disabled                                                                                                                                                                                      | ^[boolean]                                                                                                                                                                             | false                                          |
| value-key                             | unique identity key name for value, required when value is an object                                                                                                                             | ^[string]                                                                                                                                                                              | value                                          |
| size                                  | size of component                                                                                                                                                                                | ^[enum]`'' \| 'large' \| 'default' \| 'small'`                                                                                                                                      | ''                                             |
| clearable                             | whether select can be cleared                                                                                                                                                                    | ^[boolean]                                                                                                                                                                             | false                                          |
| clear-icon                            | custom clear icon                                                                                                                                                                                | ^[string] / ^[object]`Component`                                                                                                                                                       | CircleClose                                    |
| collapse-tags                         | whether to collapse tags to a text when multiple selecting                                                                                                                                       | ^[boolean]                                                                                                                                                                             | false                                          |
| multiple-limit                        | maximum number of options user can select when multiple is true. No limit when set to 0                                                                                                          | ^[number]                                                                                                                                                                              | 0                                              |
| id                                    | native input id input                                                                                                                                                                            | ^[string]                                                                                                                                                                              | —                                              |
| name                                  | the name attribute of select input                                                                                                                                                               | ^[string]                                                                                                                                                                              | —                                              |
| effect                                | tooltip theme, built-in theme: `dark` / `light`                                                                                                                                                  | ^[enum]`'dark' \| 'light'` / ^[string]                                                                                                                                                | light                                          |
| autocomplete                          | autocomplete of select input                                                                                                                                                                     | ^[string]                                                                                                                                                                              | off                                            |
| placeholder                           | placeholder                                                                                                                                                                                      | ^[string]                                                                                                                                                                              | Please select                                  |
| filterable                            | whether Select is filterable                                                                                                                                                                     | ^[boolean]                                                                                                                                                                             | false                                          |
| allow-create                          | whether creating new items is allowed. To use this, `filterable` must be true                                                                                                                    | ^[boolean]                                                                                                                                                                             | false                                          |
| filter-method                         | custom filter method, the first parameter is the current input value. To use this, `filterable` must be true method                                                                              | ^[Function]`(query: string) => void`                                                                                                                                                | —                                              |
| loading                               | whether Select is loading data from server                                                                                                                                                       | ^[boolean]                                                                                                                                                                             | false                                          |
| loading-text                          | displayed text while loading data from server, default is 'Loading'                                                                                                                              | ^[string]                                                                                                                                                                              | —                                              |
| reserve-keyword                       | whether reserve the keyword after select filtered option.                                                                                                                                        | ^[boolean]                                                                                                                                                                             | true                                           |
| default-first-option                  | select first matching option on enter key. Use with `filterable` or `remote`                                                                                                                     | ^[boolean]                                                                                                                                                                             | false                                          |
| no-match-text                         | displayed text when no data matches the filtering query, you can also use slot `empty`, default is 'No matching data'                                                                            | ^[string]                                                                                                                                                                              | —                                              |
| no-data-text                          | displayed text when there is no options, you can also use slot empty                                                                                                                             | ^[string]                                                                                                                                                                              | No Data                                        |
| popper-class                          | custom class name for Select's dropdown and tags' tooltip                                                                                                                                        | ^[string] / ^[object]                                                                                                                                                                  | ''                                             |
| popper-style ^(2.11.0)                | custom style for Select's dropdown and tags' tooltip                                                                                                                                             | ^[string] / ^[object]                                                                                                                                                                  | —                                              |
| teleported                            | whether select dropdown is teleported, if `true` it will be teleported to where `append-to` sets                                                                                                 | ^[boolean]                                                                                                                                                                             | true                                           |
| append-to ^(2.8.8)                    | which element the select dropdown appends to                                                                                                                                                     | ^[CSSSelector] / ^[HTMLElement]                                                                                                                                                        | —                                              |
| persistent                            | when select dropdown is inactive and `persistent` is `false`, select dropdown will be destroyed                                                                                                  | ^[boolean]                                                                                                                                                                             | true                                           |
| popper-options                        | [popper.js](https://popper.js.org/docs/v2/) parameters                                                                                                                                           | ^[object]refer to [popper.js](https://popper.js.org/docs/v2/) doc                                                                                                                      | {}                                             |
| automatic-dropdown                    | for non-filterable Select, this prop decides if the option menu pops up when the input is focused                                                                                                | ^[boolean]                                                                                                                                                                             | false                                          |
| fit-input-width ^(2.9.2)              | whether the width of the dropdown is the same as the input, if the value is `number`, then the width is fixed                                                                                    | ^[boolean] / ^[number]                                                                                                                                                                 | true                                           |
| suffix-icon ^(2.9.8)                  | custom suffix icon component                                                                                                                                                                     | ^[string] / ^[object]`Component`                                                                                                                                                       | ArrowDown                                      |
| height                                | The height of the dropdown panel, 34px for each item                                                                                                                                             | ^[number]                                                                                                                                                                              | 274                                            |
| item-height                           | The height of the dropdown item                                                                                                                                                                  | ^[number]                                                                                                                                                                              | 34                                             |
| estimated-option-height               | Controls virtual-list sizing mode: if undefined, the list uses fixed item height from `item-height`; if provided, the list uses dynamic item sizing and this value as the estimated item height. | ^[number]                                                                                                                                                                              | —                                              |
| scrollbar-always-on                   | Controls whether the scrollbar is always displayed                                                                                                                                               | ^[boolean]                                                                                                                                                                             | false                                          |
| remote                                | whether search data from server                                                                                                                                                                  | ^[boolean]                                                                                                                                                                             | false                                          |
| debounce ^(2.11.7)                    | debounce delay during remote search, in milliseconds                                                                                                                                             | ^[number]                                                                                                                                                                              | 300                                            |
| remote-method                         | function that gets called when the input value changes. Its parameter is the current input value. To use this, `filterable` must be true                                                         | ^[Function]`(query: string) => void`                                                                                                                                                | —                                              |
| remote-show-suffix ^(2.11.9)          | en el método de búsqueda remota mostrar icono del sufijo                                                                                                                                         | ^[boolean]                                                                                                                                                                             | false                                          |
| validate-event                        | whether to trigger form validation                                                                                                                                                               | ^[boolean]                                                                                                                                                                             | true                                           |
| offset ^(2.8.8)                       | offset of the dropdown                                                                                                                                                                           | ^[number]                                                                                                                                                                              | 12                                             |
| show-arrow ^(2.8.8)                   | whether the dropdown has an arrow                                                                                                                                                                | ^[boolean]                                                                                                                                                                             | true                                           |
| placement                             | position of dropdown                                                                                                                                                                             | ^[enum]`'top' \| 'top-start' \| 'top-end' \| 'bottom' \| 'bottom-start' \| 'bottom-end' \| 'left' \| 'left-start' \| 'left-end' \| 'right' \| 'right-start' \| 'right-end'` | bottom-start                                   |
| fallback-placements ^(2.5.6)          | list of possible positions for dropdown [popper.js](https://popper.js.org/docs/v2/modifiers/flip/#fallbackplacements)                                                                            | ^[array]`Placement[]`                                                                                                                                                                  | ['bottom-start', 'top-start', 'right', 'left'] |
| collapse-tags-tooltip ^(2.3.0)        | whether show all selected tags when mouse hover text of collapse-tags. To use this, `collapse-tags` must be true                                                                                 | ^[boolean]                                                                                                                                                                             | false                                          |
| [tag-tooltip](#tag-tooltip) ^(2.13.3) | configuration object for the collapse-tags tooltip. To use this, `collapse-tags` and `collapse-tags-tooltip` must be true                                                                        | ^[object]`TagTooltipProps`                                                                                                                                                             | {}                                             |
| max-collapse-tags ^(2.3.0)            | The max tags number to be shown. To use this, `collapse-tags` must be true                                                                                                                       | ^[number]                                                                                                                                                                              | 1                                              |
| tag-type ^(2.5.0)                     | tag type                                                                                                                                                                                         | ^[enum]`'' \| 'success' \| 'info' \| 'warning' \| 'danger'`                                                                                                                        | info                                           |
| tag-effect ^(2.7.7)                   | tag effect                                                                                                                                                                                       | ^[enum]`'' \| 'light' \| 'dark' \| 'plain'`                                                                                                                                         | light                                          |
| aria-label ^(a11y) ^(2.5.0)           | same as `aria-label` in native input                                                                                                                                                             | ^[string]                                                                                                                                                                              | —                                              |
| empty-values ^(2.7.0)                 | empty values of component, [see config-provider](./config-provider.md#empty-values-configurations)                                                                                               | ^[array]                                                                                                                                                                               | —                                              |
| value-on-clear ^(2.7.0)               | clear return value, [see config-provider](./config-provider.md#empty-values-configurations)                                                                                                      | ^[string] / ^[number] / ^[boolean] / ^[Function]                                                                                                                                       | —                                              |
| popper-append-to-body ^(deprecated)   | whether to append the popper menu to body. If the positioning of the popper is wrong, you can try to set this prop to false                                                                      | ^[boolean]                                                                                                                                                                             | false                                          |
| tabindex ^(2.9.0)                     | tabindex for input                                                                                                                                                                               | ^[string] / ^[number]                                                                                                                                                                  | —                                              |

### props

| Attribute | Descripción                                                     | Type      | Default  |
| --------- | --------------------------------------------------------------- | --------- | -------- |
| value     | specify which key of node object is used as the node's value    | ^[string] | value    |
| label     | specify which key of node object is used as the node's label    | ^[string] | label    |
| options   | specify which key of node object is used as the node's children | ^[string] | options  |
| disabled  | specify which key of node object is used as the node's disabled | ^[string] | disabled |

### tag-tooltip ^(2.13.3)

:::tip Fallback Mechanism

Properties in tag-tooltip follow this priority order:

1. Explicitly defined fields within the tag-tooltip object.
2. Shared props inherited from el-select-v2 (e.g. effect, popper-class, popper-style, teleported, append-to, popper-options).
3. Default values of the underlying el-tooltip component. This allows you to override specific tooltip behaviors for tags while maintaining consistency with the Select dropdown by default.

:::

:::tip Custom Container Positioning

When appending the Tooltip to a custom container (via the `append-to` attribute), the container should be configured with `position: relative` or `position: absolute` to ensure accurate positioning. Additionally, you can apply `overflow: hidden` to the container if you need to prevent the Tooltip from overflowing its boundaries.

:::

| Atributos           | Descripción                                                                                                          | Type                                                                                                                                                                                   | Por defecto                        |
| ------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------- |
| append-to           | a qué elemento se agrega el CONTENT del tooltip                                                                      | ^[CSSSelector] / ^[HTMLElement]                                                                                                                                                        | —                                  |
| placement           | posición del Tooltip                                                                                                 | ^[enum]`'top' \| 'top-start' \| 'top-end' \| 'bottom' \| 'bottom-start' \| 'bottom-end' \| 'left' \| 'left-start' \| 'left-end' \| 'right' \| 'right-start' \| 'right-end'` | bottom                             |
| fallback-placements | list of possible positions for Tooltip [popper.js](https://popper.js.org/docs/v2/modifiers/flip/#fallbackplacements) | ^[array]`Placement[]`                                                                                                                                                                  | ['bottom', 'top', 'right', 'left'] |
| effect              | Tema del tooltip, temas integrados: `dark` / `light`                                                                 | ^[enum]`'dark' \| 'light'` / ^[string]                                                                                                                                                | —                                  |
| popper-class        | nombre de clase personalizada para el popper del Tooltip                                                             | ^[string]                                                                                                                                                                              | —                                  |
| popper-style        | custom style for Tooltip's popper                                                                                    | ^[string] / ^[object]                                                                                                                                                                  | —                                  |
| transition          | nombre de animación                                                                                                  | ^[string]                                                                                                                                                                              | —                                  |
| teleported          | si el contenido del tooltip es teletransportado, si es `true` será teletransportado a donde establezca `append-to`   | ^[boolean]                                                                                                                                                                             | —                                  |
| popper-options      | [parámetros popper.js](https://popper.js.org/docs/v2/)                                                               | ^[object]refer to [popper.js](https://popper.js.org/docs/v2/) doc                                                                                                                      | —                                  |
| show-after          | retraso de la aparición, en milisegundos                                                                             | ^[number]                                                                                                                                                                              | —                                  |
| hide-after          | retraso de la desaparición, en milisegundos                                                                          | ^[number]                                                                                                                                                                              | —                                  |
| auto-close          | tiempo de espera en milisegundos para ocultar el tooltip de forma automática                                         | ^[number]                                                                                                                                                                              | —                                  |
| offset              | offset del Tooltip                                                                                                   | ^[number]                                                                                                                                                                              | —                                  |

### Events

| Nombre                | Description                                                                                                | Tipo                                                                           |
| --------------------- | ---------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| change                | triggers when the selected value changes, the param is current selected value                              | ^[Function]`(val: any) => void`                                             |
| visible-change        | triggers when the dropdown appears/disappears, the param will be true when it appears, and false otherwise | ^[Function]`(visible: boolean) => void`                                     |
| remove-tag            | triggers when a tag is removed in multiple mode, the param is removed tag value                            | ^[Function]`(tagValue: any) => void`                                        |
| clear                 | triggers when the clear icon is clicked in a clearable Select                                              | ^[Function]`() => void`                                                     |
| blur                  | triggers when Input blurs                                                                                  | ^[Function]`(event: FocusEvent) => void`                                    |
| focus                 | triggers when Input focuses                                                                                | ^[Function]`(event: FocusEvent) => void`                                    |
| end-reached ^(2.14.0) | triggers when dropdown scroll reaches an end                                                               | ^[Function]`(direction: 'top' \| 'bottom' \| 'left' \| 'right') => void` |

### Slots

| Name             | Description                                                                                     | Type                                                                                                              |
| ---------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| default          | Option renderer                                                                                 | —                                                                                                                 |
| header ^(2.5.2)  | content at the top of the dropdown                                                              | —                                                                                                                 |
| footer ^(2.5.2)  | content at the bottom of the dropdown                                                           | —                                                                                                                 |
| empty            | content when options is empty                                                                   | —                                                                                                                 |
| prefix           | prefix content of input                                                                         | —                                                                                                                 |
| tag ^(2.5.0)     | content as Select tag, subTags `data`, `selectDisabled` and `deleteTag` introduced in ^(2.10.3) | ^[object]`{ data: Option[], selectDisabled: boolean, deleteTag: (event: MouseEvent, option: Option) => void }` |
| loading ^(2.5.2) | content as Select loading                                                                       | —                                                                                                                 |
| label ^(2.7.4)   | content as Select label. `index` introduced in ^(2.11.2)                                        | ^[object]`{ index: number, label: string \| any, value: string \| any }`                                        |

### Exposes

| Name                   | Descripción                                     | Tipo                                              |
| ---------------------- | ----------------------------------------------- | ------------------------------------------------- |
| focus                  | focus the Input component                       | ^[Function]`() => void`                        |
| blur                   | blur the Input component, and hide the dropdown | ^[Function]`() => void`                        |
| selectedLabel ^(2.8.5) | get the currently selected label                | ^[object]`ComputedRef<string \| string[]>` |
