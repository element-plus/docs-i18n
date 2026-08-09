---
title: Cascader
lang: es-ES
---

# Cascader

Si las opciones tienen una estructura jerárquica clara, Cascader puede ser utilizado para visualizarlas y seleccionarlas.

## Uso básico

Hay dos maneras de expandir elementos de opciones hijas.

:::demo Asignando el atributo `options` a un array de opciones, renderiza un Cascader. El atributo `props.expandedTrigger` define cómo se expanden las opciones hijas.

cascader/basic

:::

## Opción deshabilitada

Deshabilite una opción estableciendo el campo `disabled` en el objeto de la opción.

:::demo En este ejemplo, el primer elemento en el array `options` tiene un campo `disabled: true`, así que está desactivado. Por defecto, Cascader comprueba el campo `disabled` en cada objeto de las opciones; si se está usando otro nombre de campo para indicar si una opción está deshabilitada, puede asignarla en el atributo `props.disabled` (ver la tabla API de abajo para más detalles). Y por supuesto, los nombres de los campos `value`, `label` y `children` también pueden ser personalizados de la misma manera.

cascader/option-disabling

:::

## Limpiable

Asigne al atributo `clearable` a `el-cascader` y un icono de limpieza aparecerá cuando sea seleccionado y actualizado

:::demo

cascader/clearable

:::

## Custom Clear Icon ^(2.11.0)

You can customize the clear icon by setting the `clear-icon` attribute

:::demo

cascader/clear-icon

:::

## Mostrar solo el último nivel

La entrada sólo puede mostrar el último nivel en lugar de todos los niveles.

:::demo El atributo `show-all-levels` define si todos los niveles son mostrados. Si es `false`, solo se muestra el último nivel.

cascader/last-level

:::

## Selección múltiple

Añada `:props="props"` en la etiqueta y establezca el dato `props = { multiple: true }` para usar la selección múltiple.

Hacer:

```vue
<template>
  <el-cascader :props="props" />
</template>

<script lang="ts" setup>
const props = { multiple: true }
</script>
```

No haga:

```vue
<template>
  <!--  Object literal binding here is invalid syntax for cascader  -->
  <el-cascader :props="{ multiple: true }" />
</template>
```

:::demo Cuando se utiliza selección múltiple, todas las etiquetas seleccionadas se mostrarán por defecto. Puede establecer `collapse-tags = true` para plegar las etiquetas seleccionadas. You can set `max-collapse-tags` to show max tags number, default 1. You can check them when mouse hover collapse text by using `collapse-tags-tooltip` attribute.

cascader/multiple-selection

:::

## Seleccione cualquier nivel de opciones

En una selección simple, solo los nodos de hoja pueden ser marcados, y en una selección múltiple, marcar los nodos padre conducirá a que los nodos de hoja sean marcados eventualmente. Cuando se habilita esta función, puede hacer que los nodos padre e hijo se desvinculen y puede seleccionar cualquier nivel de opciones.

:::demo Asigne `props.checkStrictly = true` para que el estado de marcado de un nodo no afecte a sus nodos padres y nodos hijos, entonces puede seleccionar cualquier nivel de opciones.

cascader/any-level

:::

## Carga dinámica

Carga dinámica de los nodos hijos cuando se marca un nodo.

:::demo Asigne `lazy = true` para usar carga dinámica, y tiene que especificar cómo cargar la fuente de datos por `lazyload`. Hay dos parámetros de `lazyload`, el primer parámetro `node` es el nodo en el que se ha hecho clic actualmente, y `resolve` es un callback que indica que la carga ha terminado, el cual debe ser invocado. Para mostrar el estado del nodo de forma más precisa, se puede agregar el campo `leaf` (puede ser modificado por `props.leaf`) para indicar si es un nodo de hoja. En caso contrario, se deducirá si tiene algún nodo hijo.

cascader/dynamic-loading

:::

## Filtrable

Buscar y seleccionar opciones con una palabra clave.

:::demo Añadiendo `filterable` al `el-cascader` habilita el filtro. Cascader mostrará coincidencia con los nodos cuya etiqueta o etiqueta del padre (según `show-all-levels`) incluye la palabra clave. Por supuesto, puede personalizar la lógica de búsqueda mediante `filter-method` que acepta una función, el primer parámetro es `node`, el segundo es `keyword`, y necesita devolver un valor booleano indicando si es válido.

cascader/filterable

:::

## Contenido de opción personalizada

Puede personalizar el contenido del nodo.

:::demo Puede personalizar el contenido del nodo mediante `scoped slot`. Tendrá acceso a `nodo` y `data` en el ámbito, representando el objeto Nodo y los datos del nodo actual, respectivamente.

cascader/custom-content

:::

## Custom suggestion item ^(2.9.5)

You can customize the filter suggestion item by `suggestion-item` slot. You'll have access to `item` in the scope, standing for the suggestion item.

:::demo

cascader/custom-suggestion-item

:::

## Panel de Cascader

`CascaderPanel` es el componente central de `Cascader` que tiene varias características como una sola selección, selección múltiple, carga dinámica, etc.

:::demo Al igual que `el-cascader`, puede establecer opciones alternativas `options`, y habilitar otras características por `props`, vea el formulario de la API de abajo para más detalles.

cascader/panel

:::

## Custom Tag ^(2.10.3)

You can customize tags.

:::demo Insert customized tags into the slot of `el-cascader`. `collapse-tags`, `collapse-tags-tooltip`, `max-collapse-tags` will not work.

cascader/custom-tag

:::

## Show Checked Strategy ^(2.10.5)

Control how selected values are displayed in multiple selection mode.

:::demo In multiple selection mode, you can use `show-checked-strategy` to control how selected values are displayed. The default strategy is `child`, which shows all selected child nodes. The `parent` strategy only shows parent nodes when all their children are selected.

cascader/show-checked-strategy

:::

## Click to Check Node ^(2.10.5)

Only using `multiple` or `checkStrictly` attributes.

You can add `checkOnClickNode` to be able to click on the node in addition with the prefix icon.\
Toggle the visibility of the prefix with `showPrefix`. :::tip Add `checkOnClickLeaf` to check only the leaf node (last children), enabled by default. :::

:::demo

cascader/check-on-click-node

:::

## Custom Header & Footer ^(2.10.5)

You can customize both the header and footer of the dropdown using slots.

:::demo Use slot to customize the content.

cascader/custom-header-footer

:::

## Virtual Scroll ^(2.14.0)

When dealing with large amounts of data, you can enable virtual scrolling to improve performance.

:::demo Set `virtual-scroll` to `true` to enable virtual scrolling. You can also customize the menu height with `height` and node height with `item-size`. Default height is 204px and default item size is 34px.

cascader/virtual-scroll

:::

## Custom Suggestion Width ^(2.14.0)

The width of the suggestion panel (when filtering) is calculated by default based on the maximum width of the matched options. If you customize the suggestion options through the `suggestion-item` slot, it is likely that the text displayed in the options is not equal to the value of `label`, resulting in calculation errors. In this case, you can use the `fit-input-width` attribute to fix its width. When the value is `number`, the width is a specific fixed pixel value.

:::tip

The `fit-input-width` attribute only controls the width of the suggestion panel during searching, it does not affect the default cascader panel.

:::

:::demo

cascader/fit-input-width

:::

## Cascader API

### Cascader Attributes

| Nombre                                     | Descripción                                                                                                                                                                   | Tipo                                                                                                                                                                                   | Por defecto  |
| ------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ |
| model-value / v-model                      | valor vinculado                                                                                                                                                               | ^[string] / ^[number] /^[array]`string[] \| number[] \| any`                                                                                                                         | —            |
| options                                    | los datos de las opciones, la clave de `value` y `label` pueden ser personalizados con `CascaderProps`.                                                                       | ^[array]`CascaderOption[]`                                                                                                                                                             | —            |
| [props](#cascaderprops)                    | opciones de configuración, vea la tabla `CascaderProps`.                                                                                                                      | ^[object]`CascaderProps`                                                                                                                                                               | —            |
| size                                       | tamaño del input                                                                                                                                                              | ^[enum]`'large' \| 'default' \| 'small'`                                                                                                                                             | —            |
| placeholder                                | placeholder del input                                                                                                                                                         | ^[string]                                                                                                                                                                              | —            |
| disabled                                   | si Cascader está desactivado                                                                                                                                                  | ^[boolean]                                                                                                                                                                             | —            |
| clearable                                  | si el valor seleccionado puede ser borrado                                                                                                                                    | ^[boolean]                                                                                                                                                                             | —            |
| clear-icon ^(2.11.0)                       | personaliza el componente de icono de limpieza                                                                                                                                | ^[string] / ^[object]`Component`                                                                                                                                                       | CircleClose  |
| show-all-levels                            | si se muestran todos los niveles del valor seleccionado en el input                                                                                                           | ^[boolean]                                                                                                                                                                             | true         |
| collapse-tags                              | si se contraen las etiquetas en modo de selección múltiple                                                                                                                    | ^[boolean]                                                                                                                                                                             | —            |
| collapse-tags-tooltip                      | si se muestran todas las etiquetas seleccionadas al pasar el ratón sobre el texto de las etiquetas colapsadas. Para usar esto, `collapse-tags` debe ser true                  | ^[boolean]                                                                                                                                                                             | false        |
| max-collapse-tags-tooltip-height ^(2.10.2) | max height of collapse-tags tooltip.                                                                                                                                          | ^[string] / ^[number]                                                                                                                                                                  | —            |
| separator                                  | separador de las etiquetas de las opciones                                                                                                                                    | ^[string]                                                                                                                                                                              | ' / '        |
| filterable                                 | si se pueden buscar las opciones                                                                                                                                              | ^[boolean]                                                                                                                                                                             | —            |
| filter-method                              | personaliza la lógica de búsqueda, el primer parámetro es `node`, el segundo es `keyword`, y necesita devolver un valor booleano indicando si es válido.                      | ^[Function]`(node: CascaderNode, keyword: string) => boolean`                                                                                                                       | —            |
| debounce                                   | retardo al escribir la palabra clave del filtro, en milisegundos                                                                                                              | ^[number]                                                                                                                                                                              | 300          |
| before-filter                              | función hook anterior al filtro con el valor a ser filtrado como su parámetro. Si se devuelve `false` o se devuelve una `Promise` y luego se rechaza, el filtrado se abortará | ^[Function]`(value: string) => boolean`                                                                                                                                             | —            |
| popper-class                               | custom class name for Cascader's dropdown and tags' tooltip                                                                                                                   | ^[string]                                                                                                                                                                              | ''           |
| popper-style                               | custom style for Cascader's dropdown and tags' tooltip                                                                                                                        | ^[string] / ^[object]                                                                                                                                                                  | —            |
| teleported                                 | si el popup de la cascada es teletransportada                                                                                                                                 | ^[boolean]                                                                                                                                                                             | true         |
| effect ^(2.10.5)                           | tooltip theme, built-in theme: `dark` / `light`                                                                                                                               | ^[enum]`'dark' \| 'light'` / ^[string]                                                                                                                                                | light        |
| tag-type                                   | tipo de etiqueta                                                                                                                                                              | ^[enum]`'success' \| 'info' \| 'warning' \| 'danger'`                                                                                                                               | info         |
| tag-effect ^(2.7.8)                        | tag effect                                                                                                                                                                    | ^[enum]`'light' \| 'dark' \| 'plain'`                                                                                                                                                | light        |
| validate-event                             | si se debe activar la validación del formulario                                                                                                                               | ^[boolean]                                                                                                                                                                             | true         |
| max-collapse-tags ^(2.3.10)                | The max tags number to be shown. To use this, `collapse-tags` must be true                                                                                                    | ^[number]                                                                                                                                                                              | 1            |
| empty-values ^(2.7.0)                      | empty values of component, [see config-provider](./config-provider.md#empty-values-configurations)                                                                            | ^[array]                                                                                                                                                                               | —            |
| value-on-clear ^(2.7.0)                    | clear return value, [see config-provider](./config-provider.md#empty-values-configurations)                                                                                   | ^[string] / ^[number] / ^[boolean] / ^[Function]                                                                                                                                       | —            |
| persistent ^(2.7.8)                        | when dropdown is inactive and `persistent` is `false`, dropdown will be destroyed                                                                                             | ^[boolean]                                                                                                                                                                             | true         |
| fallback-placements ^(2.8.1)               | list of possible positions for Tooltip [popper.js](https://popper.js.org/docs/v2/modifiers/flip/#fallbackplacements)                                                          | ^[array]`Placement[]`                                                                                                                                                                  | —            |
| placement ^(2.8.1)                         | position of dropdown                                                                                                                                                          | ^[enum]`'top' \| 'top-start' \| 'top-end' \| 'bottom' \| 'bottom-start' \| 'bottom-end' \| 'left' \| 'left-start' \| 'left-end' \| 'right' \| 'right-start' \| 'right-end'` | bottom-start |
| popper-append-to-body ^(deprecated)        | si añadir o no el menú popup al body. Si la posición del popper es incorrecta, puedes intentar establecer esta prop a false                                                   | ^[boolean]                                                                                                                                                                             | true         |
| show-checked-strategy ^(2.10.5)            | strategy for displaying checked nodes in multiple selection mode. Use `parent` when you want things tidy. Use `child` when every single item matters                          | ^[enum]`'parent' \| 'child'`                                                                                                                                                          | child        |
| virtual-scroll ^(2.14.0)                   | whether to enable virtual scrolling for large data                                                                                                                            | ^[boolean]                                                                                                                                                                             | false        |
| fit-input-width ^(2.14.0)                  | whether the width of the suggestion panel is the same as the input, if the value is `number`, then the width is fixed                                                         | ^[boolean] / ^[number]                                                                                                                                                                 | false        |
| item-size ^(2.14.0)                        | node height for virtual scrolling (px)                                                                                                                                        | ^[number]                                                                                                                                                                              | 34           |
| height ^(2.14.0)                           | menu height for virtual scrolling (px)                                                                                                                                        | ^[number]                                                                                                                                                                              | 204          |

### Cascader Events

| Nombre         | Descripción                                                            | Tipo                                                           |
| -------------- | ---------------------------------------------------------------------- | -------------------------------------------------------------- |
| change         | se dispara cuando el valor cambia                                      | ^[Function]`(value: CascaderValue) => void`                 |
| expand-change  | se dispara cuando cambia la expansión                                  | ^[Function]`(value: CascaderValue) => void`                 |
| blur           | se dispara cuando se pierde el foco                                    | ^[Function]`(event: FocusEvent) => void`                    |
| focus          | se dispara cuando se obtiene el foco                                   | ^[Function]`(event: FocusEvent) => void`                    |
| clear ^(2.7.7) | triggers when the clear icon is clicked in a clearable Select          | ^[Function]`() => void`                                     |
| visible-change | se dispara cuando el desplegable aparece/desaparece                    | ^[Function]`(value: boolean) => void`                       |
| remove-tag     | se dispara cuando se elimina la etiqueta en modo de selección múltiple | ^[Function]`(value: CascaderNode['valueByOption']) => void` |

### Cascader Slots

| Nombre                   | Descripción                                                                                                        | Tipo                                                         |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------ |
| default                  | el contenido personalizado del nodo en cascada, que son datos de nodo y el objeto del nodo actual respectivamente. | ^[object]`{ node: any, data: any }`                          |
| empty                    | contenido cuando no hay opciones coincidentes.                                                                     | —                                                            |
| prefix ^(2.9.4)          | content as Input prefix                                                                                            | —                                                            |
| suggestion-item ^(2.9.5) | custom content for suggestion item when searching                                                                  | ^[object]`{ item: CascaderNode }`                            |
| tag ^(2.10.3)            | custom tags style                                                                                                  | ^[object]`{ data: Tag[], deleteTag: (tag: Tag) => void }` |
| header ^(2.10.5)         | content at the top of the dropdown                                                                                 | —                                                            |
| footer ^(2.10.5)         | content at the bottom of the dropdown                                                                              | —                                                            |

### Cascader Exposes

| Nombre                        | Descripción                                                                                                                                         | Tipo                                                                |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| getCheckedNodes               | obtener un array del nodo seleccionado actualmente,(leafOnly) si solo devuelve los nodos verificados de la hoja, el valor predeterminado es `false` | ^[Function]`(leafOnly: boolean) => CascaderNode[] \| undefined` |
| cascaderPanelRef              | referencia del panel de cascada                                                                                                                     | ^[object]`ComputedRef<any>`                                   |
| togglePopperVisible ^(2.2.31) | cambiar el tipo visible de popper                                                                                                                   | ^[Function]`(visible?: boolean) => void`                         |
| contentRef                    | referencia al contenido del Cascader                                                                                                                | ^[object]`ComputedRef<any>`                                   |
| presentText ^(2.8.4)          | selected content text                                                                                                                               | ^[object]`ComputedRef<string>`                                |
| focus ^(2.11.8)               | coloca el foco en el input                                                                                                                          | ^[Function]`() => void`                                          |
| blur ^(2.11.8)                | quita el foco en el input                                                                                                                           | ^[Function]`() => void`                                          |

## CascaderPanel API

### CascaderPanel Attributes

| Nombre                   | Descripción                                                                                             | Tipo                                                        | Por defecto |
| ------------------------ | ------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- | ----------- |
| model-value / v-model    | valor vinculado                                                                                         | ^[string]/^[number]/^[array]`string[] \| number[] \| any` | —           |
| options                  | los datos de las opciones, la clave de `value` y `label` pueden ser personalizados con `CascaderProps`. | ^[array]`CascaderOption[]`                                  | —           |
| [props](#cascaderprops)  | opciones de configuración, vea la siguiente tabla `CascaderProps`.                                      | ^[object]`CascaderProps`                                    | —           |
| virtual-scroll ^(2.14.0) | whether to enable virtual scrolling for large data                                                      | ^[boolean]                                                  | false       |
| item-size ^(2.14.0)      | node height for virtual scrolling (px)                                                                  | ^[number]                                                   | 34          |
| height ^(2.14.0)         | menu height for virtual scrolling (px)                                                                  | ^[number]                                                   | 204         |

### CascaderPanel Events

| Nombre            | Descripción                                                                          | Tipo                                                         |
| ----------------- | ------------------------------------------------------------------------------------ | ------------------------------------------------------------ |
| change            | se dispara cuando el valor cambia                                                    | ^[Function]`(value: CascaderValue \| undefined) => void` |
| update:modelValue | triggers when the binding value changes                                              | ^[Function]`(value: CascaderValue \| undefined) => void` |
| expand-change     | se dispara cuando cambia la expansión                                                | ^[Function]`(value: CascaderNodePathValue) => void`       |
| close             | evento de panel de cierre, entregado a Cascader para aplazar la sentencia del panel. | ^[Function]`() => void`                                   |

### CascaderPanel Slots

| Nombre         | Descripción                                                                                                        | Tipo                                |
| -------------- | ------------------------------------------------------------------------------------------------------------------ | ----------------------------------- |
| default        | el contenido personalizado del nodo en cascada, que son datos de nodo y el objeto del nodo actual respectivamente. | ^[object]`{ node: any, data: any }` |
| empty ^(2.8.3) | the content of the panel when there is no data.                                                                    | —                                   |

### CascaderPanel Exposes

| Nombre            | Descripción                                                                                                                                         | Tipo                                                                |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| getCheckedNodes   | obtener un array del nodo seleccionado actualmente,(leafOnly) si solo devuelve los nodos verificados de la hoja, el valor predeterminado es `false` | ^[Function]`(leafOnly: boolean) => CascaderNode[] \| undefined` |
| clearCheckedNodes | borrar los nodos marcados                                                                                                                           | ^[Function]`() => void`                                          |

## CascaderProps

| Atributo                   | Descripción                                                                                                                     | Tipo                                                                          | Por defecto |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------- |
| expandTrigger              | modo de activación de la expansión                                                                                              | ^[enum]`'click' \| 'hover'`                                                  | click       |
| multiple                   | si la selección múltiple está habilitada                                                                                        | ^[boolean]                                                                    | false       |
| checkStrictly              | si el marcado de un nodo no afecta a sus nodos padre e hijo                                                                     | ^[boolean]                                                                    | false       |
| emitPath                   | si emitir un array de la ruta del nodo cuando los nodos marcados cambian, si es false solo emite el valor del nodo.             | ^[boolean]                                                                    | true        |
| lazy                       | si la carga de nodos hijos es dinámica, use son el atributo `lazyload`                                                          | ^[boolean]                                                                    | false       |
| lazyLoad                   | method for loading child nodes data, only works when `lazy` is true. The reject parameter is supported after version ^(2.11.5). | ^[Function]`(node: Node, resolve: Resolve, reject: () => void) => void` | —           |
| value                      | especifica qué clave del objeto del nodo se utiliza como value                                                                  | ^[string]                                                                     | value       |
| label                      | especifica qué clave del objeto del nodo se utiliza como label                                                                  | ^[string]                                                                     | label       |
| children                   | especifica qué clave del nodo se utiliza como nodo hijo                                                                         | ^[string]                                                                     | children    |
| disabled                   | especifica qué clave del nodo se utiliza para verificar si el nodo está deshabilitado o no                                      | ^[string]                                                                     | disabled    |
| leaf                       | especifica qué clave del nodo se utiliza como campo leaf                                                                        | ^[string]                                                                     | leaf        |
| hoverThreshold             | umbral de expansión de las opciones                                                                                             | ^[number]                                                                     | 500         |
| checkOnClickNode ^(2.10.5) | whether to check or uncheck node when clicking on the node                                                                      | ^[boolean]                                                                    | false       |
| checkOnClickLeaf ^(2.10.5) | whether to check or uncheck node when clicking on leaf node (last children).                                                    | ^[boolean]                                                                    | true        |
| showPrefix ^(2.10.5)       | whether to show the radio or checkbox prefix                                                                                    | ^[boolean]                                                                    | true        |

## Declaraciones de tipo

<details>
  <summary>Mostrar declaraciones</summary>

```ts
type CascaderNodeValue = string | number
type CascaderNodePathValue = CascaderNodeValue[]
type CascaderValue =
  | CascaderNodeValue
  | CascaderNodePathValue
  | (CascaderNodeValue | CascaderNodePathValue)[]

type Resolve = (data: any) => void

type ExpandTrigger = 'click' | 'hover'

type LazyLoad = (node: Node, resolve: Resolve, reject: () => void) => void

type isDisabled = (data: CascaderOption, node: Node) => boolean

type isLeaf = (data: CascaderOption, node: Node) => boolean

interface CascaderOption extends Record<string, unknown> {
  label?: string
  value?: CascaderNodeValue
  children?: CascaderOption[]
  disabled?: boolean
  leaf?: boolean
}

interface CascaderProps {
  expandTrigger?: ExpandTrigger
  multiple?: boolean
  checkStrictly?: boolean
  emitPath?: boolean
  lazy?: boolean
  lazyLoad?: LazyLoad
  value?: string
  label?: string
  children?: string
  disabled?: string | isDisabled
  leaf?: string | isLeaf
  hoverThreshold?: number
}

class Node {
  readonly uid: number
  readonly level: number
  readonly value: CascaderNodeValue
  readonly label: string
  readonly pathNodes: Node[]
  readonly pathValues: CascaderNodePathValue
  readonly pathLabels: string[]

  childrenData: ChildrenData
  children: Node[]
  text: string
  loaded: boolean
  /**
   * Is it checked
   *
   * @default false
   */
  checked: boolean
  /**
   * Used to indicate the intermediate state of unchecked and fully checked child nodes
   *
   * @default false
   */
  indeterminate: boolean
  /**
   * Loading Status
   *
   * @default false
   */
  loading: boolean

  // getter
  isDisabled: boolean
  isLeaf: boolean
  valueByOption: CascaderNodeValue | CascaderNodePathValue

  // method
  appendChild(childData: CascaderOption): Node
  calcText(allLevels: boolean, separator: string): string
  broadcast(): void
  emit(): void
  onParentCheck(checked: boolean): void
  onChildCheck(): void
  setCheckState(checked: boolean): void
  doCheck(checked: boolean): void
}

Node as CascaderNode
```

</details>
