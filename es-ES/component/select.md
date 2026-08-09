---
title: Select
lang: es-ES
---

# Select

Cuando haya muchas opciones, utilice un menú desplegable para mostrar y seleccionar las que desee.

:::tip

After version ^(2.5.0), the default width of `el-select` changed to `100%`. When used in a inline form, the width will collapse. In order to display the width properly, you need to give `el-select` a specific width (eg: [Example](https://github.com/element-plus/element-plus/issues/15834#issuecomment-1936919229)) .

:::

## Uso básico

:::demo `v-model` es el valor de `el-option` que actualmente está seleccionado.

select/basic-usage

:::

## Options attribute ^(2.10.5)

:::demo Shortcut from basic `el-option` usage. You can customize the alias of the `options` through the `props` attribute.

select/options

:::

## Opción deshabilitada

:::demo Establezca el valor de `disabled` en `el-option` a `true` para deshabilitar esa opción.

select/disabled-option

:::

## Deshabilitar el select

Desactivar todo el componente.

:::demo Ajuste `disabled` de `el-select` para desactivarlo.

select/disabled

:::

## Clearable

Puede limpiar el Select con un icono.

:::demo Set `clearable` attribute for `el-select` and a clear icon will appear.

select/clearable

:::

## Sizes

:::demo Add `size` attribute to change the size of Select. In addition to the default size, there are two other options: `large`, `small`.

select/size

:::

## Selección múltiple básica

Selección múltiple utiliza etiquetas para mostrar las opciones seleccionadas.

:::demo Asigne el atributo `multiple` a `el-select` para activar la selección múltiple. En este caso, el valor de `v-model` será un array de opciones seleccionadas. Por defecto, las opciones seleccionadas se mostrarán como etiquetas. Puede colapsar a un texto usando el atributo `collapse-tags`. Puede comprobarlos cuando el ratón pasa el cursor sobre el texto usando el atributo `collapse-tags-tooltip`.

select/multiple

:::

## Plantilla personalizada

Puede personalizar plantillas HTML para opciones.

:::demo Insertar plantillas HTML personalizadas en el slot de `el-option`.

select/custom-template

:::

## Header of the dropdown ^(2.4.3)

You can customize the header of the dropdown.

:::demo Use slot to customize the content.

select/custom-header

:::

## Footer of the dropdown ^(2.4.3)

You can customize the footer of the dropdown.

:::demo Use slot to customize the content.

select/custom-footer

:::

## Agrupando

Mostrar opciones en grupos.

:::demo Use `el-option-group` para agrupar las opciones, y su atributo `label` significa el nombre del grupo.

select/grouping

:::

## Filtrado de opciones

Puede filtrar las opciones que desee.

:::demo Añadiendo `filterable` a `el-select` se habilita el filtro. Por defecto, Select encontrará todas las opciones cuyo atributo `label` contiene el valor de entrada. Si prefiere otras estrategias de filtrado, puede pasar el `filter-method`. `filter-method` es una `funcion` que se llama cuando el valor de entrada cambia, y su parámetro es el valor de entrada actual.

select/filterable

:::

## Búsqueda remota

Introduzca palabras clave y busque los datos en el servidor.

:::demo Establezca el valor de `filterable` y `remote` con `true` para habilitar la búsqueda remota, y deberá pasar el `remote-method`. `remote-method` es una `función` que se llama cuando el valor de entrada cambia, y su parámetro es el valor de entrada actual. Tenga en cuenta que si `el-option` se presenta con la directiva `v-for`, debe agregar el atributo `key` para `el-option`. Su valor debe ser único, como `item.value` en el siguiente ejemplo.

select/remote-search

:::

## Crear nuevos items

Crear y seleccionar nuevos elementos que no están incluidos en las opciones de selección

:::demo usando el atributo `allow-create`, los usuarios pueden crear nuevos elementos escribiendo en un input. Tenga en cuenta que para que `allow-create` funcione, `filterable` debe ser `true`. Este ejemplo también demuestra `default-first-option`. Cuando este atributo se establece en `true`, puede seleccionar la primera opción en la lista de opciones actual pulsando enter sin tener que navegar con teclas de ratón o flecha.

select/allow-create

:::

## Usar el atributo value-key

Si el valor de vinculación de Select es un objeto, asegúrese de asignar `value-key` como su nombre único de clave de identidad.

:::demo Usando el atributo `value-key`, los datos con etiquetas duplicadas pueden ser manejados correctamente. El valor de la propiedad `label` está duplicado, pero la opción puede ser identificada a través del `id`.

select/value-key

:::

## Custom Tag ^(2.5.0)

You can customize tags.

:::demo Insert customized tags into the slot of `el-select`. `collapse-tags`, `collapse-tags-tooltip`, `max-collapse-tags` will not work.

select/custom-tag

:::

## Custom Loading ^(2.5.2)

Override loading content.

:::demo

select/custom-loading

:::

## Empty Values ^(2.7.0)

If you want to support empty string, please set `empty-values` to `[null, undefined]`.

If you want to change the clear value to `null`, please set `value-on-clear` to `null`.

:::demo

select/empty-values

:::

## Custom Label ^(2.7.4)

You can customize label.

:::demo

select/custom-label

:::

## Select API

### Select Attributes

| Nombre                                | Descripción                                                                                                                                                  | Tipo                                                                                                                                                                                   | Default                                        |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| model-value / v-model                 | valor vinculado                                                                                                                                              | ^[string] / ^[number] / ^[boolean] / ^[object] / ^[array]                                                                                                                              | —                                              |
| multiple                              | si multiple-select esta activo                                                                                                                               | ^[boolean]                                                                                                                                                                             | false                                          |
| options ^(2.10.5)                     | data of the options, the key of `value` and `label` and `disabled` can be customize by `props`                                                               | ^[array]`Array<{[key: string]: any}>`                                                                                                                                            | —                                              |
| [props](#props) ^(2.10.5)             | configuration options                                                                                                                                        | ^[object]                                                                                                                                                                              | —                                              |
| disabled                              | si Select esta deshabilitado                                                                                                                                 | ^[boolean]                                                                                                                                                                             | false                                          |
| value-key                             | si se colapsan los tags a un texto cuando `multiple` es `true`.                                                                                              | ^[string]                                                                                                                                                                              | value                                          |
| size                                  | tamaño del input                                                                                                                                             | ^[enum]`'' \| 'large' \| 'default' \| 'small'`                                                                                                                                      | —                                              |
| clearable                             | si el select puede ser limpiado                                                                                                                              | ^[boolean]                                                                                                                                                                             | false                                          |
| collapse-tags                         | si contraer etiquetas a un texto con la selección múltiple                                                                                                   | ^[boolean]                                                                                                                                                                             | false                                          |
| collapse-tags-tooltip ^(2.3.0)        | si se muestran todas las etiquetas seleccionadas al pasar el ratón sobre el texto de las etiquetas colapsadas. Para usar esto, `collapse-tags` debe ser true | ^[boolean]                                                                                                                                                                             | false                                          |
| [tag-tooltip](#tag-tooltip) ^(2.13.3) | configuration object for the collapse-tags tooltip. To use this, `collapse-tags` and `collapse-tags-tooltip` must be true                                    | ^[object]`TagTooltipProps`                                                                                                                                                             | {}                                             |
| multiple-limit                        | máximo número de opciones que el usuario puede seleccionar cuando `multiple` es `true`. Sin límite cuando se fija a 0                                        | ^[number]                                                                                                                                                                              | 0                                              |
| id                                    | native input id input                                                                                                                                        | ^[string]                                                                                                                                                                              | —                                              |
| name                                  | el atributo `name` del input seleccionado                                                                                                                    | ^[string]                                                                                                                                                                              | —                                              |
| effect                                | tooltip theme, built-in theme: `dark` / `light`                                                                                                              | ^[enum]`'dark' \| 'light'` / ^[string]                                                                                                                                                | light                                          |
| autocomplete                          | el atributo `autocomplete` del input seleccionado                                                                                                            | ^[string]                                                                                                                                                                              | off                                            |
| placeholder                           | placeholder, default is 'Select'                                                                                                                             | ^[string]                                                                                                                                                                              | —                                              |
| filterable                            | si Select es filtrable                                                                                                                                       | ^[boolean]                                                                                                                                                                             | false                                          |
| allow-create                          | si está permitido crear nuevos ítems. To use this, `filterable` must be true                                                                                 | ^[boolean]                                                                                                                                                                             | false                                          |
| filter-method                         | custom filter method, the first parameter is the current input value. Para usar esto, `filterable` debe ser `true`.                                          | ^[Function]`(query: string) => void`                                                                                                                                                | —                                              |
| remote                                | si las opciones se traerán desde el servidor                                                                                                                 | ^[boolean]                                                                                                                                                                             | false                                          |
| debounce ^(2.11.7)                    | debounce delay during remote search, in milliseconds                                                                                                         | ^[number]                                                                                                                                                                              | 300                                            |
| remote-method                         | function that gets called when the input value changes. Its parameter is the current input value. To use this, `filterable` must be true                     | ^[Function]`(query: string) => void`                                                                                                                                                | —                                              |
| remote-show-suffix                    | en el método de búsqueda remota mostrar icono del sufijo                                                                                                     | ^[boolean]                                                                                                                                                                             | false                                          |
| loading                               | si Select está cargando datos del servidor                                                                                                                   | ^[boolean]                                                                                                                                                                             | false                                          |
| loading-text                          | displayed text while loading data from server, default is 'Loading'                                                                                          | ^[string]                                                                                                                                                                              | —                                              |
| no-match-text                         | displayed text when no data matches the filtering query, you can also use slot `empty`, default is 'No matching data'                                        | ^[string]                                                                                                                                                                              | —                                              |
| no-data-text                          | displayed text when there is no options, you can also use slot `empty`, default is 'No data'                                                                 | ^[string]                                                                                                                                                                              | —                                              |
| popper-class                          | custom class name for Select's dropdown and tags' tooltip                                                                                                    | ^[string]                                                                                                                                                                              | ''                                             |
| popper-style ^(2.11.0)                | custom style for Select's dropdown and tags' tooltip                                                                                                         | ^[string] / ^[object]                                                                                                                                                                  | —                                              |
| reserve-keyword                       | when `multiple` and `filterable` is true, whether to reserve current keyword after selecting an option                                                       | ^[boolean]                                                                                                                                                                             | true                                           |
| default-first-option                  | seleccione la primera opción de coincidencia al introducir la clave. Usar con `filterable` o `remote`                                                        | ^[boolean]                                                                                                                                                                             | false                                          |
| teleported                            | whether select dropdown is teleported, if `true` it will be teleported to where `append-to` sets                                                             | ^[boolean]                                                                                                                                                                             | true                                           |
| append-to ^(2.8.4)                    | which element the select dropdown appends to                                                                                                                 | ^[CSSSelector] / ^[HTMLElement]                                                                                                                                                        | —                                              |
| persistent                            | when select dropdown is inactive and `persistent` is `false`, select dropdown will be destroyed                                                              | ^[boolean]                                                                                                                                                                             | true                                           |
| automatic-dropdown                    | for non-filterable Select, this prop decides if the option menu pops up when the input is focused                                                            | ^[boolean]                                                                                                                                                                             | false                                          |
| clear-icon                            | custom clear icon component                                                                                                                                  | ^[string] / ^[object]`Component`                                                                                                                                                       | CircleClose                                    |
| fit-input-width                       | whether the width of the dropdown is the same as the input                                                                                                   | ^[boolean]                                                                                                                                                                             | false                                          |
| suffix-icon                           | custom suffix icon component                                                                                                                                 | ^[string] / ^[object]`Component`                                                                                                                                                       | ArrowDown                                      |
| tag-type                              | tag type                                                                                                                                                     | ^[enum]`'' \| 'success' \| 'info' \| 'warning' \| 'danger'`                                                                                                                        | info                                           |
| tag-effect ^(2.7.7)                   | tag effect                                                                                                                                                   | ^[enum]`'' \| 'light' \| 'dark' \| 'plain'`                                                                                                                                         | light                                          |
| validate-event                        | whether to trigger form validation                                                                                                                           | ^[boolean]                                                                                                                                                                             | true                                           |
| offset ^(2.8.8)                       | offset of the dropdown                                                                                                                                       | ^[number]                                                                                                                                                                              | 12                                             |
| show-arrow ^(2.8.8)                   | whether the dropdown has an arrow                                                                                                                            | ^[boolean]                                                                                                                                                                             | true                                           |
| placement ^(2.2.17)                   | position of dropdown                                                                                                                                         | ^[enum]`'top' \| 'top-start' \| 'top-end' \| 'bottom' \| 'bottom-start' \| 'bottom-end' \| 'left' \| 'left-start' \| 'left-end' \| 'right' \| 'right-start' \| 'right-end'` | bottom-start                                   |
| fallback-placements ^(2.5.6)          | list of possible positions for dropdown [popper.js](https://popper.js.org/docs/v2/modifiers/flip/#fallbackplacements)                                        | ^[array]`Placement[]`                                                                                                                                                                  | ['bottom-start', 'top-start', 'right', 'left'] |
| max-collapse-tags ^(2.3.0)            | the max tags number to be shown. To use this, `collapse-tags` must be true                                                                                   | ^[number]                                                                                                                                                                              | 1                                              |
| popper-options                        | [popper.js](https://popper.js.org/docs/v2/) parameters                                                                                                       | ^[object]refer to [popper.js](https://popper.js.org/docs/v2/) doc                                                                                                                      | {}                                             |
| aria-label ^(a11y)                    | same as `aria-label` in native input                                                                                                                         | ^[string]                                                                                                                                                                              | —                                              |
| empty-values ^(2.7.0)                 | empty values of component, [see config-provider](./config-provider.md#empty-values-configurations)                                                           | ^[array]                                                                                                                                                                               | —                                              |
| value-on-clear ^(2.7.0)               | clear return value, [see config-provider](./config-provider.md#empty-values-configurations)                                                                  | ^[string] / ^[number] / ^[boolean] / ^[Function]                                                                                                                                       | —                                              |
| suffix-transition ^(deprecated)       | animation when dropdown appears/disappears icon                                                                                                              | ^[boolean]                                                                                                                                                                             | true                                           |
| tabindex ^(2.9.0)                     | tabindex for input                                                                                                                                           | ^[string] / ^[number]                                                                                                                                                                  | —                                              |

:::warning

`suffix-transition` has been **deprecated**, and **will be** removed in ^(2.4.0), please use override style scheme.

:::

### props

| name              | Descripción                                                                                | Type      | Default  |
| ----------------- | ------------------------------------------------------------------------------------------ | --------- | -------- |
| value             | especifica qué clave del objeto del nodo se utiliza como value                             | ^[string] | value    |
| label             | especifica qué clave del objeto del nodo se utiliza como label                             | ^[string] | label    |
| options ^(2.11.0) | especifica qué clave del nodo se utiliza como nodo hijo                                    | ^[string] | options  |
| disabled          | especifica qué clave del nodo se utiliza para verificar si el nodo está deshabilitado o no | ^[string] | disabled |

### tag-tooltip ^(2.13.3)

:::tip Fallback Mechanism

Properties in tag-tooltip follow this priority order:

1. Explicitly defined fields within the tag-tooltip object.
2. Shared props inherited from el-select (e.g. effect, popper-class, popper-style, teleported, append-to, popper-options).
3. Default values of the underlying el-tooltip component. This allows you to override specific tooltip behaviors for tags while maintaining consistency with the Select dropdown by default.

:::

:::tip Custom Container Positioning

When appending the Tooltip to a custom container (via the `append-to` attribute), the container should be configured with `position: relative` or `position: absolute` to ensure accurate positioning. Additionally, you can apply `overflow: hidden` to the container if you need to prevent the Tooltip from overflowing its boundaries.

:::

| Atributos           | Descripción                                                                                                          | Tipo                                                                                                                                                                                   | Por defecto                        |
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

### Select Events

| Nombre                | Descripción                                                  | Type                                                                           |
| --------------------- | ------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| change                | se dispara cuando el valor del select cambia                 | ^[Function]`(value: any) => void`                                           |
| visible-change        | se dispara cuando el menú desplegable aparece o desaparece   | ^[Function]`(visible: boolean) => void`                                     |
| remove-tag            | se dispara cuando un tag es removido en modo múltiple        | ^[Function]`(tagValue: any) => void`                                        |
| clear                 | se dispara cuando el icono se clickea en un Select limpiable | ^[Function]`() => void`                                                     |
| blur                  | se dispara cuando el input pierde el foco                    | ^[Function]`(event: FocusEvent) => void`                                    |
| focus                 | se dispara cuando el input obtiene el foco                   | ^[Function]`(event: FocusEvent) => void`                                    |
| popup-scroll ^(2.9.4) | triggers when dropdown scrolls                               | ^[Function]`(data:{scrollTop: number, scrollLeft: number}) => void`         |
| end-reached ^(2.14.0) | triggers when dropdown scroll reaches an end                 | ^[Function]`(direction: 'top' \| 'bottom' \| 'left' \| 'right') => void` |

### Select Slots

| Nombre del slot  | Descripción                                                                                     | Subtags                                                                                                                  |
| ---------------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| default          | option component list                                                                           | Option Group / Option                                                                                                    |
| header ^(2.4.3)  | content at the top of the dropdown                                                              | —                                                                                                                        |
| footer ^(2.4.3)  | content at the bottom of the dropdown                                                           | —                                                                                                                        |
| prefix           | contenido prefix de un  Select                                                                  | —                                                                                                                        |
| empty            | Lista sin opciones                                                                              | —                                                                                                                        |
| tag ^(2.5.0)     | content as Select tag, subTags `data`, `selectDisabled` and `deleteTag` introduced in ^(2.10.3) | ^[object]`{ data: OptionBasic[], selectDisabled: boolean, deleteTag: (event: MouseEvent, tag: OptionBasic) => void }` |
| loading ^(2.5.2) | content as Select loading                                                                       | —                                                                                                                        |
| label ^(2.7.4)   | content as Select label. `index` introduced in ^(2.11.2)                                        | ^[object]`{ index: number, label: string \| any, value: string \| any }`                                               |

### Select Exposes

| Nombre                 | Description                                     | Tipo                                              |
| ---------------------- | ----------------------------------------------- | ------------------------------------------------- |
| focus                  | focus the Input component                       | ^[Function]`() => void`                        |
| blur                   | blur the Input component, and hide the dropdown | ^[Function]`() => void`                        |
| selectedLabel ^(2.8.5) | get the currently selected label                | ^[object]`ComputedRef<string \| string[]>` |

## Option Group API

### Option Group Attributes

| Name     | Descripción                                  | Tipo       | Por defecto |
| -------- | -------------------------------------------- | ---------- | ----------- |
| label    | name of the group                            | ^[string]  | —           |
| disabled | whether to disable all options in this group | ^[boolean] | false       |

### Option Group Slots

| Nombre  | Descripción               | Subtags |
| ------- | ------------------------- | ------- |
| default | customize default content | Option  |

## Option API

### Option Attributes

| Nombre   | Descripción                                 | Tipo                                           | Por defecto |
| -------- | ------------------------------------------- | ---------------------------------------------- | ----------- |
| value    | value of option                             | ^[string] / ^[number] / ^[boolean] / ^[object] | —           |
| label    | label of option, same as `value` if omitted | ^[string] / ^[number]                          | —           |
| disabled | whether option is disabled                  | ^[boolean]                                     | false       |

### Option Slots

| Name    | Descripción               |
| ------- | ------------------------- |
| default | customize default content |
