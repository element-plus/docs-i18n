---
title: Autocomplete
lang: es-ES
---

# Autocompletado

Puede obtener algunas sugerencias basadas en la entrada actual.

## Uso básico

El componente Autocompletar proporciona sugerencias de entrada.

:::demo El atributo `fetch-suggestions` es un método que devuelve sugerencias de entrada. En este ejemplo, `querySearch(queryString, cb)` devuelve sugerencias a Autocompletar vía `cb(data)` cuando las sugerencias están listas.

autocomplete/autocomplete

:::

## Template personalizado

Personalice cómo se muestran las sugerencias.

:::demo Utilice `scoped slot` para personalizar los elementos de sugerencias. En el scope, puede acceder al objeto de sugerencia mediante la clave `item`.

autocomplete/autocomplete-template

:::

## Búsqueda remota

Búsqueda de datos desde el servidor.

:::demo

autocomplete/remote-search

:::

## Custom Loading ^(2.5.0)

Override loading content.

:::demo

autocomplete/custom-loading

:::

## Custom Header & Footer ^(2.10.6)

You can customize both the header and footer of the dropdown using slots

:::demo Use slot to customize the content.

autocomplete/custom-header-footer

:::

## API

### Atributos

| Nombre                               | Descripción                                                                                                                                    | Tipo                                                                                          | Por defecto  |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | ------------ |
| model-value / v-model                | valor enlazado                                                                                                                                 | ^[string]                                                                                     | —            |
| placeholder                          | el placeholder del autocompletado                                                                                                              | ^[string]                                                                                     | —            |
| clearable                            | si desea mostrar el botón de borrar                                                                                                            | ^[boolean]                                                                                    | false        |
| disabled                             | si el autocompletado está deshabilitado                                                                                                        | ^[boolean]                                                                                    | false        |
| value-key                            | nombre clave del objeto de sugerencia para mostrar en el input                                                                                 | ^[string]                                                                                     | value        |
| debounce                             | retraso de desconexión al teclear, en milisegundos                                                                                             | ^[number]                                                                                     | 300          |
| placement                            | posición del menú emergente                                                                                                                    | ^[enum]`'top' \| 'top-start' \| 'top-end' \| 'bottom' \| 'bottom-start' \| 'bottom-end'` | bottom-start |
| fetch-suggestions                    | un método para obtener sugerencias del input. Cuando las sugerencias están listas, invoca `callback(data:[])` para devolverlas a Autocompletar | ^[array] / ^[Function]`(queryString: string, callback: callbackfn) => void`                | —            |
| trigger-on-focus                     | si mostrar sugerencias cuando el input tenga el foco                                                                                           | ^[boolean]                                                                                    | true         |
| select-when-unmatched                | si se quiere emitir un evento `select` cuando no hay coincidencia de autocompletado                                                            | ^[boolean]                                                                                    | false        |
| name                                 | como `name` en el input nativo                                                                                                                 | ^[string]                                                                                     | —            |
| aria-label ^(a11y) ^(2.7.2)          | native `aria-label` attribute                                                                                                                  | ^[string]                                                                                     | —            |
| hide-loading                         | si se oculta el icono de load en la búsqueda remota                                                                                            | ^[boolean]                                                                                    | false        |
| popper-class                         | nombre de clase personalizado para el menú desplegable de autocompletado                                                                       | ^[string] / ^[object]                                                                         | ''           |
| popper-style ^(2.11.4)               | custom style for autocomplete's dropdown                                                                                                       | ^[string] / ^[object]                                                                         | —            |
| popper-options ^(2.14.0)             | [parámetros popper.js](https://popper.js.org/docs/v2/)                                                                                         | ^[object]refer to [popper.js](https://popper.js.org/docs/v2/) doc                             | {}           |
| show-arrow ^(2.14.0)                 | whether the dropdown has an arrow                                                                                                              | ^[boolean]                                                                                    | true         |
| teleported                           | si el desplegable de selección se teletransporta al body                                                                                       | ^[boolean]                                                                                    | true         |
| append-to ^(2.9.9)                   | which select dropdown appends to                                                                                                               | ^[CSSSelector] / ^[HTMLElement]                                                               | —            |
| highlight-first-item                 | si por defecto se destacara el primer elemento en las sugerencias de búsqueda remota                                                           | ^[boolean]                                                                                    | false        |
| fit-input-width                      | si el ancho del desplegable es el mismo que el del input                                                                                       | ^[boolean]                                                                                    | false        |
| popper-append-to-body ^(deprecated)  | si añadir el menú desplegable al body. Si la posición del desplegable es incorrecta, puede intentar establecer esta propiedad a false          | ^[boolean]                                                                                    | false        |
| loop-navigation ^(2.11.4)            | whether keyboard navigation loops from end to start                                                                                            | ^[boolean]                                                                                    | true         |
| [input props](./input.md#attributes) | —                                                                                                                                              | —                                                                                             | —            |

### Eventos

| Nombre | Descripción                                                     | Tipo                                                      |
| ------ | --------------------------------------------------------------- | --------------------------------------------------------- |
| blur   | triggers when Input blurs                                       | ^[Function]`(event: FocusEvent) => void`               |
| focus  | triggers when Input focuses                                     | ^[Function]`(event: FocusEvent) => void`               |
| input  | triggers when the Input value change                            | ^[Function]`(value: string \| number) => void`        |
| clear  | triggers when the Input is cleared by clicking the clear button | ^[Function]`() => void`                                |
| select | se dispara cuando se hace clic en una sugerencia                | ^[Function]`(item: Record<string, any>) => void` |
| change | se dispara cuando el icono dentro del valor de entrada cambia   | ^[Function]`(value: string \| number) => void`        |

### Slots

| Nombre           | Descripción                             | Tipo                                           |
| ---------------- | --------------------------------------- | ---------------------------------------------- |
| default          | custom content for input suggestions    | ^[object]`{ item: Record<string, any> }` |
| header ^(2.10.6) | content at the top of the dropdown      | -                                              |
| footer ^(2.10.6) | content at the bottom of the dropdown   | -                                              |
| prefix           | contenido como prefijo del input        | -                                              |
| suffix           | contenido como sufijo del input         | -                                              |
| prepend          | contenido a anteponer al input          | -                                              |
| append           | contenido para añadir después del input | -                                              |
| loading ^(2.5.0) | override loading content                | -                                              |

### Expuesto

| Nombre           | Descripción                                      | Type                                                         |
| ---------------- | ------------------------------------------------ | ------------------------------------------------------------ |
| activated        | si se activa el autocompletado                   | ^[object]`Ref<boolean>`                                |
| blur             | quita el foco en el input                        | ^[Function]`() => void`                                   |
| close            | contraer lista de sugerencias                    | ^[Function]`() => void`                                   |
| focus            | coloca el foco en el elemento                    | ^[Function]`() => void`                                   |
| handleSelect     | se dispara cuando se hace clic en una sugerencia | ^[Function]`(item: any) => Promise<void>`           |
| handleKeyEnter   | manejar evento de entrada de teclado             | ^[Function]`() => Promise<void>`                    |
| highlightedIndex | el índice del elemento actualmente destacado     | ^[object]`Ref<number>`                                 |
| highlight        | destacar un elemento en una sugerencia           | ^[Function]`(itemIndex: number) => void`                  |
| inputRef         | instancia del componente el-input                | ^[object]`Ref<ElInputInstance>`                        |
| loading          | indicador de carga de búsqueda remota            | ^[object]`Ref<boolean>`                                |
| popperRef        | instancia del componente el-tooltip              | ^[object]`Ref<ElTooltipInstance>`                      |
| suggestions      | obtener resultados de sugerencias                | ^[object]`Ref<record<string, any>[]>`            |
| getData ^(2.8.4) | loading suggestion list                          | ^[Function]`(queryString: string) => Promise<void>` |
