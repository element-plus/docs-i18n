---
title: Table
lang: es-ES
---

# Table

Visualiza múltiples datos con un formato similar. Puede ordenar, filtrar y comparar sus datos en la tabla.

## Tabla básica

La tabla básica es solo para mostrar datos.

:::demo Después de haber establecido el atributo `data` de `el-table` con un arreglo de objetos, puede usar la propiedad `prop` (el correspondiente a la clave de un objeto dentro del array `data`) en `el-table-column` para insertar datos a las columnas de la tabla, y establecer el atributo `label` para definir el nombre de la columna que se va a mostrar. También puede usar el atributo `width` para establecer el ancho de las columnas.

table/basic

:::

## Tabla con franjas

La tabla con franjas hace más fácil distinguir filas diferentes.

:::demo El atributo `stripe` acepta un `Boolean`. Si es `true`, la tabla será con franjas.

table/striped

:::

## Tabla con bordes

:::demo Por defecto, la tabla no tiene bordes verticales. Si lo necesita, puede establecer el atributo `border` a `true`.

table/with-border

:::

## Tabla con estados

Puede destacar el contenido de la tabla para distinguir entre "success, information, warning, danger" y otros estados.

:::demo Utilice `row-class-name` en `el-table` para agregar clases personalizadas a una fila específica. De esa manera podrá darle diseño con esas clases.

table/with-status

:::

## Table with show overflow tooltip

When the content is too long, it will break into multiple lines, you can use `show-overflow-tooltip` to keep it in one line.

:::demo Attribute `show-overflow-tooltip`, which accepts a `Boolean` value. Cuando se establece a `true`, el contenido extra se mostrará en un tooltip cuando se pase el cursor sobre la celda.

table/show-overflow-tooltip

:::

## Tabla con cabecera fija

Cuando hay demasiadas filas, puede usar una cabecera fija.

:::demo Al configurar el atributo `height` de `el-table`, puede dejar fija la cabecera de la tabla sin necesidad de agregar otro código.

table/fixed-header

:::

## Tabla con columnas fijas

Cuando se tienen demasiadas columnas, puede fijar algunas de ellas.

:::demo El atributo `fixed` es utilizado en `el-table-column`, este acepta un `Boolean`. Si es `true`, la columna será fijada a la izquierda. También acepta dos tipos: 'left' y 'right', ambos indican donde debe ser fijada la columna.

table/fixed-column

:::

## Tabla con columnas y cabecera fija

Cuando tiene grandes cantidades de datos para colocar en una tabla, puede fijar la cabecera y columnas al mismo tiempo.

:::demo Fije las columnas y cabecera al mismo tiempo combinando los dos ejemplos anteriores.

table/fixed-column-and-header

:::

## Tabla de altura fluida con cabecera fija (y columnas)

Cuando los datos se cambian dinámicamente, tal vez desee que la tabla tenga una altura máxima en lugar de una altura fija y que muestre la barra de desplazamiento si es necesario.

:::demo Al configurar el atributo `max-height` de `el-table`, puede fijar la cabecera de la tabla. La barra de desplazamiento únicamente se mostrará si la altura sobrepasa el valor de la altura máxima.

table/fixed-header-with-fluid-header

:::

## Agrupando cabeceras de la tabla

Cuando la estructura de datos es compleja, puede usar la cabecera de grupo para mostrar la jerarquía de datos.

:::demo Solo necesita colocar el-table-column dentro de otro el-table-column, de esta forma logrará agruparles.

table/grouping-header

:::

## Tabla con cabecera de grupo fija

se puede usar la cabecera de grupo fija

:::demo El atributo `fixed` de la cabecera del grupo es determinado por `el-table-column`

table/fixed-column-and-group-header

:::

## Selección simple

La selección de una sola fila es posible.

:::demo La tabla permite la selección de una sola fila. Puede activarlo añadiendo el atributo `highlight-current-row`. Un evento llamado `current-change` será disparado cuando la selección de la fila cambie, sus parámetros son la fila antes y después del cambio: `currentRow` y `oldCurrentRow`. Si necesita mostrar el índice de la fila, puede agregar un nuevo `el-table-column` con el atributo `type` asignado al `index` y podrá ver el índice iniciando desde 1.

table/single-select

:::

## Selección multiple

También puede seleccionar múltiples filas.

After ^(2.8.3), `toggleRowSelection` supports the third parameter `ignoreSelectable` to determine whether to ignore the selectable attribute.

:::demo Activar la selección múltiple es sencillo: Solo debe agregar un `el-table-column` con su `type` establecido en `selection`.

table/multi-select

:::

## Ordenar

Ordenar los datos para encontrar o comparar información rápidamente.

:::demo Establezca el atributo `sortable` para ordenar los datos de una columna. Este acepta un `Boolean` con un valor por defecto `false`. Establezca el atributo `default-sort` para determinar la columna y orden por defecto. Para aplicar sus propias reglas de ordenamiento, utilice `sort-method` o `sort-by`. Si lo que necesita es ordenar de forma remota desde backend, establezca `sortable` a `custom`, y escuche el evento `sort-change` de la tabla. Al dispararse el evento, tendrá acceso a la columna ordenada y el tipo de orden para que pueda obtener los datos de la tabla ordenada desde su API. En este ejemplo utilizamos otro atributo llamado `formatter` para darle un formato al valor de ciertas columnas. Este acepta una función que tiene dos parámetros: `row` y `column`. Puede manejarlo de acuerdo a sus propias necesidades.

table/sort

:::

## Filtros

Filtra la tabla para encontrar la información que necesita.

:::demo Establezca el atributo `filters` y `filter-method` en `el-table-column` haciendo esta columna filtrable. `filters` es un arreglo, y `filter-method` es una función que decide que filas se muestra. Tiene tres parámetros: `value`, `row` y `column`.

table/filter

:::

## Plantilla de columna personalizada

Personalice la columna de la tabla para que pueda integrarse con otros componentes.

:::demo Tiene acceso a la siguiente información: row, column, $index y store (gestor de estados de la tabla) por [slots](https://v3.vuejs.org/guide/component-slots.html).

table/custom-column

:::

## Tabla con cabecera personalizada

Se puede personalizar el encabezado de la tabla para que se pueda adaptar aún más.

:::demo Puede personalizar el aspecto del encabezado con los [slots](https://v3.vuejs.org/guide/component-slots.html).de header.

table/custom-header

:::

## Filas expandibles

Cuando el contenido de la fila es demasiado largo y no quiere mostrar la barra de desplazamiento horizontal, puede usar la función de fila expandible.

After ^(2.9.7), `preserve-expanded-content` is added to control whether to preserve expanded row content in DOM when collapsed.

:::demo Puede activar la fila expandible estableciendo la propiedad type="expand" o con slots. La plantilla para el-table-column se mostrará como el contenido de la fila expandible, y puede acceder a los mismos atributos que cuando está usando `slots` en plantillas de columnas personalizadas.

table/expandable-row

:::

## Datos con estructura de árbol y modo perezoso

:::demo Puede visualizar datos con una estructura de árbol. Cuando la fila contiene el campo `children`, se trata como datos anidados. Para renderizar datos anidados, la propiedad `row-key` es necesaria. Además, los datos de registros secundarios se pueden cargar de forma asíncrona. Establezca la propiedad `lazy` de la tabla a true y la función que usara a `load`. Especifique el atributo `hasChildren` en la fila para determinar qué fila contiene descendencia. Tanto `children` como `hasChildren` pueden configurarse a través de `tree-props`.

table/tree-and-lazy

:::

## Selectable tree ^(2.8.0)

:::demo When `treeProps.checkStrictly` is true, the selection state of parent and child nodes is no longer associated, that is, when the parent node is selected, its child nodes will not be selected; when `treeProps.checkStrictly` is false, the selection state of parent and child nodes will be associated with the selection state of child nodes, that is, when the parent node is selected, all its child nodes will be selected.

table/check-strictly

:::

## Fila resumen

Para una tabla de números, puede agregar una fila extra en el pie de página de la tabla que muestra la suma de cada columna.

:::demo Puede agregar la fila de resumen configurando `show-summary` a `true`. Por defecto, para la fila de resumen, la primera columna no resume nada, pero siempre muestra 'Sum' (puede configurar el texto mostrado usando `sum-text`), las otras columnas suman cada número en esa columna y los muestran. Por supuesto, puede definir un comportamiento propio para suma. To do so, pass a method to `summary-method`, which returns an array, and each element of the returned array will be displayed in the columns of the summary row, It can be a VNode or string. La segunda tabla de este ejemplo es una demostración detallada.

table/summary

:::

## Rowspan and colspan

Configure rowspan y colspan para combinar las celdas

:::demo Utilice el atributo `span-method` para configurar rowspan y colspan. Este acepta un método, y pasa un objeto a ese método incluyendo la fila actual `row`, columna actual `column`, índice de fila actual `rowIndex` y índice de columna actual `columnIndex`. El método debe devolver un arreglo de dos números, el primer número siendo `rowspan` y el segundo `colspan`. También puede devolver un objeto con las propiedades `rowspan` y `colspan`.

table/rowspan-and-colspan

:::

## Índice personalizado

Puede personalizar el índice de la fila con la propiedad `type=index` de las columnas.

:::demo Para personalizar el índice de la fila, utilice el atributo `index` en `el-table-column` con `type=index`. Si este es asignado a un número, todos los índices tendrán un desplazamiento desde ese número. También acepta un método con cada índice (iniciando desde `0`) como un parámetro, y devuelve un valor que puede ser mostrado como índice.

table/custom-index

:::

## Disposición de la tabla

La propiedad [table-layout](https://developer.mozilla.org/en-US/docs/Web/CSS/table-layout) establece el algoritmo usado para exponer celdas de tablas, filas y columnas.

:::demo

table/table-layout

:::

## Tooltip formatter ^(2.9.4)

You can use `tooltip-formatter` to customize the tooltip content.

:::demo

table/tooltip-formatter

:::

## Table API

### Atributos de la tabla

| Nombre                             | Descripción                                                                                                                                                                                                                                                                                                                     | Tipo                                                                                                                                                                               | Default                                                                                                                 |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| data                               | table data                                                                                                                                                                                                                                                                                                                      | ^[array]`any[]`                                                                                                                                                                    | []                                                                                                                      |
| height                             | table's height. Por defecto tiene una altura `auto`. Si este valor es un número, la altura es medido en pixeles; si este valor es una cadena, se asigna ese valor al style.height de la tabla, la altura es afectada por estilos externos                                                                                       | ^[string] / ^[number]                                                                                                                                                              | —                                                                                                                       |
| max-height                         | table's max-height. The legal value is a number or the height in px                                                                                                                                                                                                                                                             | ^[string] / ^[number]                                                                                                                                                              | —                                                                                                                       |
| stripe                             | especifica si la tabla se mostrara con franjas                                                                                                                                                                                                                                                                                  | ^[boolean]                                                                                                                                                                         | false                                                                                                                   |
| border                             | especifica si la tabla tiene bordes verticales                                                                                                                                                                                                                                                                                  | ^[boolean]                                                                                                                                                                         | false                                                                                                                   |
| size                               | tamaño de la tabla                                                                                                                                                                                                                                                                                                              | ^[enum]`'' \| 'large' \| 'default' \| 'small'`                                                                                                                                  | —                                                                                                                       |
| fit                                | especifica si el ancho de la columna se adapta automáticamente a su contenedor                                                                                                                                                                                                                                                  | ^[boolean]                                                                                                                                                                         | true                                                                                                                    |
| show-header                        | especifica si la cabecera de la tabla es visible                                                                                                                                                                                                                                                                                | ^[boolean]                                                                                                                                                                         | true                                                                                                                    |
| highlight-current-row              | especifica si la fila actual estara resaltada                                                                                                                                                                                                                                                                                   | ^[boolean]                                                                                                                                                                         | false                                                                                                                   |
| current-row-key                    | clave de la fila actual, un ajuste unicamente de prop                                                                                                                                                                                                                                                                           | ^[string] / ^[number]                                                                                                                                                              | —                                                                                                                       |
| row-class-name                     | función que devuelve nombres de clases personalizadas para las filas, o una cadena asignando el nombre de clase para cada fila                                                                                                                                                                                                  | ^[Function]`(data: { row: any, rowIndex: number }) => string` / ^[string]                                                                                                       | —                                                                                                                       |
| row-style                          | función que devuelve el estilo personalizado para cada fila, o un objeto asignando el estilo personalizado para todas las filas                                                                                                                                                                                                 | ^[Function]`(data: { row: any, rowIndex: number }) => CSSProperties` / ^[object]`CSSProperties`                                                                                 | —                                                                                                                       |
| cell-class-name                    | función que devuelve nombres de clases personalizadas para las celdas, o una cadena asignando el nombre de clase para cada celda                                                                                                                                                                                                | ^[Function]`(data: { row: any, column: TableColumnCtx<T>, rowIndex: number, columnIndex: number }) => string` / ^[string]                                                 | —                                                                                                                       |
| cell-style                         | función que devuelve estilos personalizados para cada celda, o un objeto asignado el estilo personalizado para todas las celdas                                                                                                                                                                                                 | ^[Function]`(data: { row: any, column: TableColumnCtx<T>, rowIndex: number, columnIndex: number }) => CSSProperties` / ^[object]`CSSProperties`                           | —                                                                                                                       |
| header-row-class-name              | función que devuelve nombre de clases personalizadas para cada fila en la cabecera de la tabla, o una cadena asignando nombre de clase para todas las filas en la cabecera de la tabla                                                                                                                                          | ^[Function]`(data: { row: any, rowIndex: number }) => string` / ^[string]                                                                                                       | —                                                                                                                       |
| header-row-style                   | función que devuelve estilos personalizados para cada una de las filas en la cabecera de la tabla, o un objeto asignando el estilo personalizado para todas las filas en la cabecera de la tabla                                                                                                                                | ^[Function]`(data: { row: any, rowIndex: number }) => CSSProperties` / ^[object]`CSSProperties`                                                                                 | —                                                                                                                       |
| header-cell-class-name             | función que devuelve nombres de clases personalizada para cada celda en la cabecera de la tabla, o una cadena asignando el nombre de clase para todas las celda en la cabecera de la tabla                                                                                                                                      | ^[Function]`(data: { row: any, column: TableColumnCtx<T>, rowIndex: number, columnIndex: number }) => string` / ^[string]                                                 | —                                                                                                                       |
| header-cell-style                  | función que devuelve estilos personalizados para cada celda en la cabecera de la tabla, o un objeto asignando el estilo personalizado para todas las celdas en la cabecera de la tabla                                                                                                                                          | ^[Function]`(data: { row: any, column: TableColumnCtx<T>, rowIndex: number, columnIndex: number }) => CSSProperties` / ^[object]`CSSProperties`                           | —                                                                                                                       |
| row-key                            | key de los datos de las filas, utilizada para optimizar el renderizado. Requerido si `reserve-selection` está activada o muestra los datos con formato de árbol. When its type is String, multi-level access is supported, e.g. `user.info.id`, but `user.info[0].id` is not supported, in which case `Function` should be used | ^[Function]`(row: any) => string` / ^[string]                                                                                                                                   | —                                                                                                                       |
| empty-text                         | displayed text when data is empty. Puede personalizar esta área con `#empty`                                                                                                                                                                                                                                                    | ^[string]                                                                                                                                                                          | Sin Datos                                                                                                               |
| default-expand-all                 | especifica si todas las filas se expanden por defecto, solo funciona cuando la tabla tiene una columna type="expand" o contiene datos de estructura de árbol                                                                                                                                                                    | ^[boolean]                                                                                                                                                                         | false                                                                                                                   |
| expand-row-keys                    | set expanded rows by this prop, prop's value is the keys of expand rows, you should set row-key before using this prop.                                                                                                                                                                                                         | ^[array]`Array<string>`                                                                                                                                                      | —                                                                                                                       |
| default-sort                       | establece la columna y orden por defecto. la propiedad `prop` es utilizada para establecer la columna de ordenamiento por defecto, la propiedad `order` es utilizada para definir el tipo de orden por defecto                                                                                                                  | ^[object]`Sort`                                                                                                                                                                    | if `prop` is set, and `order` is not set, then `order` is default to ascending                                          |
| tooltip-effect                     | el `effect` del tooltip por desbordamiento                                                                                                                                                                                                                                                                                      | ^[enum]`'dark' \| 'light'`                                                                                                                                                        | dark                                                                                                                    |
| tooltip-options ^(2.2.28)          | las opciones para el tooltip de desbordamiento, [vea el componente de tooltip](tooltip.html#attributes)                                                                                                                                                                                                                         | ^[object]`Pick<ElTooltipProps, 'effect' \| 'enterable' \| 'hideAfter' \| 'offset' \| 'placement' \| 'popperClass' \| 'popperOptions' \| 'showAfter' \| 'showArrow'>` | ^[object]`{ enterable: true, placement: 'top', showArrow: true, hideAfter: 200, popperOptions: { strategy: 'fixed' } }` |
| append-filter-panel-to ^(2.8.4)    | which element the filter panels appends to                                                                                                                                                                                                                                                                                      | ^[string]                                                                                                                                                                          | —                                                                                                                       |
| show-summary                       | específica si debe mostrar la fila de resumen                                                                                                                                                                                                                                                                                   | ^[boolean]                                                                                                                                                                         | false                                                                                                                   |
| sum-text                           | texto a mostrar para la primer columna de la fila de resumen                                                                                                                                                                                                                                                                    | ^[string]                                                                                                                                                                          | Sum                                                                                                                     |
| summary-method                     | método personalizado para resumen                                                                                                                                                                                                                                                                                               | ^[Function]`(data: { columns: any[], data: any[] }) => (VNode \| string)[]`                                                                                                    | —                                                                                                                       |
| span-method                        | método que devuelve rowspan y colspan                                                                                                                                                                                                                                                                                           | ^[Function]`(data: { row: any, column: TableColumnCtx<T>, rowIndex: number, columnIndex: number }) => number[] \| { rowspan: number, colspan: number } \| void`         | —                                                                                                                       |
| select-on-indeterminate            | controla el comportamiento del checkbox maestro en tablas de selección múltiple cuando solo se seleccionan algunas filas (pero no todas). If true, all rows will be selected, else deselected                                                                                                                                   | ^[boolean]                                                                                                                                                                         | true                                                                                                                    |
| indent                             | indentación horizontal de los datos en el formato de estructura de árbol                                                                                                                                                                                                                                                        | ^[number]                                                                                                                                                                          | 16                                                                                                                      |
| lazy                               | si se realiza una carga perezosa de los datos                                                                                                                                                                                                                                                                                   | ^[boolean]                                                                                                                                                                         | false                                                                                                                   |
| load                               | método para cargar datos de filas hijas, solo funciona cuando `lazy` es true                                                                                                                                                                                                                                                    | ^[Function]`(row: any, treeNode: TreeNode, resolve: (data: any[]) => void) => void`                                                                                          | —                                                                                                                       |
| tree-props                         | configuración para renderizar datos anidados                                                                                                                                                                                                                                                                                    | ^[object]`{ hasChildren?: string, children?: string, checkStrictly?: boolean }`                                                                                                    | ^[object]`{ hasChildren: 'hasChildren', children: 'children', checkStrictly: false }`                                   |
| table-layout                       | sets the algorithm used to lay out table cells, rows, and columns                                                                                                                                                                                                                                                               | ^[enum]`'fixed' \| 'auto'`                                                                                                                                                        | fixed                                                                                                                   |
| scrollbar-always-on                | si mostrar siempre la barra de desplazamiento                                                                                                                                                                                                                                                                                   | ^[boolean]                                                                                                                                                                         | false                                                                                                                   |
| show-overflow-tooltip              | whether to hide extra content and show them in a tooltip when hovering on the cell.It will affect all the table columns, refer to table [tooltip-options](#table-attributes)                                                                                                                                                    | ^[boolean] / [`object`](#table-attributes) ^(2.3.7)                                                                                                                                | —                                                                                                                       |
| flexible ^(2.2.1)                  | ensure main axis minimum-size doesn't follow the content                                                                                                                                                                                                                                                                        | ^[boolean]                                                                                                                                                                         | false                                                                                                                   |
| scrollbar-tabindex ^(2.8.3)        | body scrollbar's wrap container tabindex                                                                                                                                                                                                                                                                                        | ^[string] / ^[number]                                                                                                                                                              | —                                                                                                                       |
| allow-drag-last-column ^(2.9.2)    | whether to allow drag the last column                                                                                                                                                                                                                                                                                           | ^[boolean]                                                                                                                                                                         | true                                                                                                                    |
| tooltip-formatter ^(2.9.4)         | customize tooltip content when using `show-overflow-tooltip`                                                                                                                                                                                                                                                                    | ^[Function]`(data: { row: any, column: TableColumnCtx<T>, cellValue: any }) => VNode \| string`                                                                          | —                                                                                                                       |
| preserve-expanded-content ^(2.9.7) | whether to preserve expanded row content in DOM when collapsed                                                                                                                                                                                                                                                                  | ^[boolean]                                                                                                                                                                         | false                                                                                                                   |
| native-scrollbar ^(2.10.5)         | whether to use native scrollbars                                                                                                                                                                                                                                                                                                | ^[boolean]                                                                                                                                                                         | false                                                                                                                   |
| row-expandable ^(2.13.2)           | enable expandable rows, works when the table has a column type="expand"                                                                                                                                                                                                                                                         | ^[Function]`(row: any, index: number) => boolean`                                                                                                                               | —                                                                                                                       |

### Eventos de la tabla

| Nombre             | Descripción                                                                                                                                                                       | Tipo                                                                                                                                            |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| select             | se dispara cuando el usuario hace clic al _checkbox_ (caja de selección) en una fila                                                                                              | ^[Function]`<T = DefaultRow>(selection: T[], row: T) => void`                                                                          |
| select-all         | se dispara cando el usuario hace clic al _checkbox_ (caja de selección) en la cabecera de la tabla                                                                                | ^[Function]`<T = DefaultRow>(selection: T[]) => void`                                                                                  |
| selection-change   | se dispara cuando la selección cambia                                                                                                                                             | ^[Function]`<T = DefaultRow>(newSelection: T[]) => void`                                                                               |
| cell-mouse-enter   | se dispara cuando el ratón se desplaza dentro de una celda                                                                                                                        | ^[Function]`<T = DefaultRow>(row: T, column: TableColumnCtx<T>, cell: HTMLTableCellElement, event: MouseEvent) => void`          |
| cell-mouse-leave   | se dispara cuando el ratón se desplaza fuera de una celda                                                                                                                         | ^[Function]`<T = DefaultRow>(row: T, column: TableColumnCtx<T>, cell: HTMLTableCellElement, event: MouseEvent) => void`          |
| cell-click         | se dispara cuando se hace clic en una celda                                                                                                                                       | ^[Function]`<T = DefaultRow>(row: T, column: TableColumnCtx<T>, cell: HTMLTableCellElement, event: PointerEvent) => void`        |
| cell-dblclick      | se dispara cuando se hace doble clic en una celda                                                                                                                                 | ^[Function]`<T = DefaultRow>(row: T, column: TableColumnCtx<T>, cell: HTMLTableCellElement, event: MouseEvent) => void`          |
| cell-contextmenu   | se dispara cuando el usuario hace clic derecho en una celda                                                                                                                       | ^[Function]`<T = DefaultRow>(row: T, column: TableColumnCtx<T>, cell: HTMLTableCellElement, event: PointerEvent) => void`        |
| row-click          | se dispara cuando se hace clic en una fila                                                                                                                                        | ^[Function]`<T = DefaultRow>(row: T, column: TableColumnCtx<T> \| null, event: PointerEvent) => void`                           |
| row-contextmenu    | se dispara cuando el usuario hace clic derecho en una fila                                                                                                                        | ^[Function]`<T = DefaultRow>(row: T, column: TableColumnCtx<T> \| null, event: PointerEvent) => void`                           |
| row-dblclick       | se dispara cuando se hace doble clic en una fila                                                                                                                                  | ^[Function]`<T = DefaultRow>(row: T, column: TableColumnCtx<T> \| null, event: MouseEvent) => void`                             |
| header-click       | se dispara cuando se hace clic en una cabecera de columna                                                                                                                         | ^[Function]`<T = DefaultRow>(column: TableColumnCtx<T>, event: PointerEvent) => void`                                            |
| header-contextmenu | se dispara cuando el usuario hace clic derecho en una cabecera de columna                                                                                                         | ^[Function]`<T = DefaultRow>(column: TableColumnCtx<T>, event: PointerEvent) => void`                                            |
| sort-change        | se dispara cuando el orden de la tabla cambia                                                                                                                                     | ^[Function]`<T = DefaultRow>(data: {column: TableColumnCtx<T>, prop: string \| null, order: TableSortOrder \| null }) => void` |
| filter-change      | triggers when the table's filter changes                                                                                                                                          | ^[Function]`(newFilters: Record<string, string[]>) => void`                                                                            |
| current-change     | se dispara cuando la fila actual cambia                                                                                                                                           | ^[Function]`<T = DefaultRow>(currentRow: T \| null, oldCurrentRow: T \| null) => void`                                               |
| header-dragend     | se dispara después de modificar el ancho de una columna arrastrando el borde de la cabecera                                                                                       | ^[Function]`<T = DefaultRow>(newWidth: number, oldWidth: number, column: TableColumnCtx<T>, event: MouseEvent) => void`          |
| expand-change      | se activa cuando el usuario expande o colapsa una fila (para la tabla expansible, el segundo parámetro es expandedRows; para la tabla de árbol, el segundo parámetro es expanded) | ^[Function]`<T = DefaultRow>(row: T, expandedRows: T[]) => void & <T = DefaultRow>(row: T, expanded: boolean) => void`    |
| scroll ^(2.9.0)    | Invoked after scrolled                                                                                                                                                            | ^[Function]`({ scrollLeft: number, scrollTop: number }) => void`                                                                             |

### Slots de la tabla

| Nombre  | Descripción                                                                                                                                                                                                     | Subetiquetas |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ |
| default | personalizar contenido por defecto                                                                                                                                                                              | Table-column |
| append  | Contenidos a insertarse después de la última fila. Es posible que necesite este espacio si desea implementar _scroll_ infinito para la tabla. Este slot se mostrará por encima de la fila de resumen si la hay. | —            |
| empty   | puedes personalizar el contenido cuando los datos están vacíos.                                                                                                                                                 | —            |

### Table Exposes

| Método                         | Descripción                                                                                                                                                                                        | Type                                                                            |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| clearSelection                 | utilizado en selección múltiple de la tabla, limpia lo seleccionado                                                                                                                                | ^[Function]`() => void`                                                      |
| getSelectionRows               | devuelve las filas seleccionadas                                                                                                                                                                   | ^[Function]`() => any[]`                                                     |
| getHalfSelectionRows ^(2.14.2) | returns the currently half-selected rows                                                                                                                                                           | ^[Function]`() => any[]`                                                     |
| toggleRowSelection             | usado en la tabla de selección múltiple, conmuta si se selecciona una fila determinada. Con el segundo parámetro, puede establecer directamente si esta fila está seleccionada                     | ^[Function]`(row: any, selected?: boolean, ignoreSelectable = true) => void` |
| toggleAllSelection             | usado en la tabla de selección múltiple, alterna seleccionar todas o anular todas                                                                                                                  | ^[Function]`() => void`                                                      |
| toggleRowExpansion             | utilizado en la tabla expandible o en la tabla de árbol, conmuta si se expande una determinada fila. Con el segundo parámetro, puede establecer directamente si este registro se expande o colapsa | ^[Function]`(row: any, expanded?: boolean) => void`                          |
| setCurrentRow                  | utilizado en tabla con selección sencilla, establece una cierta fila como seleccionada. If called without any parameter, it will clear selection                                                   | ^[Function]`(row: any) => void`                                              |
| clearSort                      | borra el orden, restaurando los datos al orden original                                                                                                                                            | ^[Function]`() => void`                                                      |
| clearFilter                    | limpia los filtros de las columnas cuyas `columnKey` han sido pasadas. Si no hay parámetros, borrar todos los filtros                                                                              | ^[Function]`(columnKeys?: string[]) => void`                                 |
| doLayout                       | actualizar el diseño de la tabla. Cuando la visibilidad de la tabla cambia, puede necesitar llamar a este método para obtener un diseño correcto                                                   | ^[Function]`() => void`                                                      |
| sort                           | ordena la tabla manualmente. La propiedad `prop` se utiliza para establecer la columna de ordenación, la propiedad `order` se utiliza para establecer el orden                                     | ^[Function]`(prop: string, order: string) => void`                           |
| scrollTo                       | desplaza a un conjunto particular de coordenadas                                                                                                                                                   | ^[Function]`(options: number \| ScrollToOptions, yCoord?: number) => void`  |
| setScrollTop                   | fija posición de desplazamiento vertical                                                                                                                                                           | ^[Function]`(top?: number) => void`                                          |
| setScrollLeft                  | fija posición de desplazamiento horizontal                                                                                                                                                         | ^[Function]`(left?: number) => void`                                         |
| columns ^(2.7.6)               | Get table columns context.                                                                                                                                                                         | ^[array]`TableColumnCtx<T>[]`                                             |
| updateKeyChildren ^(2.8.4)     | used in lazy Table, must set `rowKey`, update key children                                                                                                                                         | ^[Function]`(key: string, data: T[]) => void`                                |

## Table-column API

### Atributos del Table-column

| Nombre                     | Descripción                                                                                                                                                                                                                                            | Type                                                                                                                                                                                   | Por defecto                       |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------- |
| type                       | tipo de columna. Si se establece a `selection`, la columna puede mostrar un _checkbox_. Si se establece a `index`, la columna puede mostrar el índice de la fila (iniciando desde 1). If set to `expand`, the column will display expand icon          | ^[enum]`'default' \| 'selection' \| 'index' \| 'expand'`                                                                                                                            | default                           |
| index                      | personaliza los índices para cada fila, funciona en columnas con `type=index`                                                                                                                                                                          | ^[number] / ^[Function]`(index: number) => number`                                                                                                                                  | —                                 |
| label                      | etiqueta de la columna                                                                                                                                                                                                                                 | ^[string]                                                                                                                                                                              | —                                 |
| column-key                 | column's key. Si necesita utilizar el evento `filter-change`, se usara este atributo para identificar que columna está siendo filtrada                                                                                                                 | ^[string]                                                                                                                                                                              | —                                 |
| prop                       | nombre del campo. También puede usar su alias: `property`                                                                                                                                                                                              | ^[string]                                                                                                                                                                              | —                                 |
| width                      | ancho de la columna                                                                                                                                                                                                                                    | ^[string] / ^[number]                                                                                                                                                                  | ''                                |
| min-width                  | ancho mínimo de la columna. Columnas con `width` tienen un ancho fijo, mientras que las columnas con `min-width` tienen un ancho que se distribuye en proporción                                                                                       | ^[string] / ^[number]                                                                                                                                                                  | ''                                |
| fixed                      | específica si la columna se fija a la izquierda o a la derecha. Se fijará a la izquierda si es `true`                                                                                                                                                  | ^[enum]`'left' \| 'right'` / ^[boolean]                                                                                                                                               | false                             |
| render-header              | función de renderizado para la cabecera de la tabla de esta columna                                                                                                                                                                                    | ^[Function]`(data: { column: TableColumnCtx<T>, $index: number }) => void`                                                                                                    | —                                 |
| sortable                   | si la columna puede ser ordenada. La ordenación remota se puede hacer estableciendo este atributo a 'custom' y escuchando el evento `sort-change` de la tabla                                                                                          | ^[boolean] / ^[string]                                                                                                                                                                 | false                             |
| sort-method                | método para ordenar, funciona cuando `sortable` está en `true`. Debería devolver un número, al igual que Array.sort                                                                                                                                    | ^[Function]`<T = any>(a: T, b: T) => number`                                                                                                                                  | —                                 |
| sort-by                    | especifica cuál es la propiedad por la cual se va a ordenar, funciona cuando `sortable` es `true` y `sort-method` es `undefined`. Si se establece a un arreglo, la columna ordenara secuencialmente por la siguiente propiedad si la anterior es igual | ^[Function]`(row: any, index: number) => string` / ^[string] / ^[array]`string[]`                                                                                                   | —                                 |
| sort-orders                | la estrategia para ordenar los datos, funciona cuando `sortable` es `true`. Acepta un arreglo, a medida que el usuario hace clic en el encabezado, la columna se ordena siguiendo la secuencia de los elementos del arreglo                            | ^[object]`('ascending' \| 'descending' \| null)[]`                                                                                                                                   | ['ascending', 'descending', null] |
| resizable                  | si el ancho de la columna puede ser redimensionado, funciona cuando `border` de `el-table` está en `true`                                                                                                                                              | ^[boolean]                                                                                                                                                                             | true                              |
| formatter                  | función que da formato al contenido de la celda                                                                                                                                                                                                        | ^[Function]`(row: any, column: TableColumnCtx<T>, cellValue: any, index: number) => VNode \| string`                                                                         | —                                 |
| show-overflow-tooltip      | si oculta contenido extra y lo muestra en un _tooltip_ al pasar el cursor sobre la celda                                                                                                                                                               | ^[boolean] / [`object`](#table-attributes) ^(2.2.28)                                                                                                                                   | undefined                         |
| align                      | alineación                                                                                                                                                                                                                                             | ^[enum]`'left' \| 'center' \| 'right'`                                                                                                                                               | left                              |
| header-align               | alineación de la cabecera de la tabla. Si se omite, se aplicará el valor del atributo anterior: `align`                                                                                                                                                | ^[enum]`'left' \| 'center' \| 'right'`                                                                                                                                               | left                              |
| class-name                 | nombre de la clase Css de la celda en la columna                                                                                                                                                                                                       | ^[string]                                                                                                                                                                              | —                                 |
| label-class-name           | nombre de la clase Css de la etiqueta de esta columna                                                                                                                                                                                                  | ^[string]                                                                                                                                                                              | —                                 |
| selectable                 | función que determina si una cierta fila puede ser seleccionada, funciona cuando `type` está en `selection`                                                                                                                                            | ^[Function]`(row: any, index: number) => boolean`                                                                                                                                   | —                                 |
| reserve-selection          | específica si se reserva la selección después de actualizar los datos, funciona cuando `type` está en `selection`. Note que `row-key` es requerido para que esto funcione                                                                              | ^[boolean]                                                                                                                                                                             | false                             |
| filters                    | un arreglo de opciones para filtrado de datos. Para cada elemento en este arreglo, `text` y `value` son obligatorios                                                                                                                                   | ^[array]`Array<{text: string, value: string}>`                                                                                                                                   | —                                 |
| filter-placement           | ubicación del menú desplegable de filtros                                                                                                                                                                                                              | ^[enum]`'top' \| 'top-start' \| 'top-end' \| 'bottom' \| 'bottom-start' \| 'bottom-end' \| 'left' \| 'left-start' \| 'left-end' \| 'right' \| 'right-start' \| 'right-end'` | —                                 |
| filter-class-name ^(2.5.0) | className for the filter dropdown                                                                                                                                                                                                                      | ^[string]                                                                                                                                                                              | —                                 |
| filter-multiple            | si el filtrado de datos soporta múltiples opciones                                                                                                                                                                                                     | ^[boolean]                                                                                                                                                                             | true                              |
| filter-method              | método para filtrado de datos. Si `filter-multiple` está activado, este método será llamado varias veces por cada fila, y se mostrará la fila si la llamada devuelve `true`                                                                            | ^[Function]`(value: any, row: any, column: TableColumnCtx<T>) => void`                                                                                                        | —                                 |
| filtered-value             | el valor del filtro para los datos seleccionados, puede ser útil cuando el encabezado de la tabla es renderizado con `render-header`                                                                                                                   | ^[array]`string[]`                                                                                                                                                                     | —                                 |
| tooltip-formatter ^(2.9.4) | customize tooltip content when using `show-overflow-tooltip`                                                                                                                                                                                           | ^[Function]`(data: { row: any, column: TableColumnCtx<T>, cellValue: any }) => VNode \| string`                                                                              | —                                 |

### Slots de Table-column

| Nombre               | Descripción                                                                                      | Type                                                                     |
| -------------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| default              | Custom content for table columns                                                                 | ^[object]`{ row: any, column: TableColumnCtx<T>, $index: number }` |
| header               | Custom content for table header                                                                  | ^[object]`{ column: TableColumnCtx<T>, $index: number }`           |
| filter-icon ^(2.7.8) | Custom content for filter icon                                                                   | ^[object]`{ filterOpened: boolean }`                                     |
| expand ^(2.10.0)     | Custom content for expand columns. The `expandable` property is supported starting from v2.13.2. | ^[object]`{ expanded: boolean, expandable: boolean }`                    |

## Type Declarations

<details>
  <summary>Show declarations</summary>

```ts
interface Sort {
  prop: string
  order: 'ascending' | 'descending'
  init?: any
  silent?: any
}

interface TreeNode {
  expanded?: boolean
  loading?: boolean
  noLazyChildren?: boolean
  indent?: number
  level?: number
  display?: boolean
}

type DefaultRow = Record<PropertyKey, any>

type TableColumnCtx<T extends DefaultRow = DefaultRow> = {
  id: string
  realWidth: number | null
  type: string
  label: string
  className: string
  labelClassName: string
  property: string
  prop: string
  width?: string | number
  minWidth: string | number
  renderHeader: (data: CI<T>) => VNode
  sortable: boolean | string
  sortMethod: (a: T, b: T) => number
  sortBy: string | ((row: T, index: number, array?: T[]) => string) | string[]
  resizable: boolean
  columnKey: string
  rawColumnKey: string
  align: string
  headerAlign: string
  showOverflowTooltip?: boolean | TableOverflowTooltipOptions
  tooltipFormatter?: TableOverflowTooltipFormatter<T>
  fixed: boolean | string
  formatter: (
    row: T,
    column: TableColumnCtx<T>,
    cellValue: any,
    index: number
  ) => VNode | string
  selectable: (row: T, index: number) => boolean
  reserveSelection: boolean
  filterMethod: FilterMethods<T>
  filteredValue: string[]
  filters: Filters
  filterPlacement: string
  filterMultiple: boolean
  filterClassName: string
  index: number | ((index: number) => number)
  sortOrders: (TableSortOrder | null)[]
  renderCell: (data: any) => VNode | VNode[]
  colSpan: number
  rowSpan: number
  children?: TableColumnCtx<T>[]
  level: number
  filterable: boolean | FilterMethods<T> | Filters
  order: TableSortOrder | null
  isColumnGroup: boolean
  isSubColumn: boolean
  columns: TableColumnCtx<T>[]
  getColumnIndex: () => number
  no: number
  filterOpened?: boolean
  renderFilterIcon?: (scope: any) => VNode
  renderExpand?: (scope: any) => VNode
}
```

</details>

## FAQ

#### How to infer the correct slot types for `el-table-column`?

`el-table-column` is a generic component. If TypeScript cannot infer the row type for its slots from the surrounding context, place Vue's `@vue-generic` directive comment immediately before `el-table-column` and pass the row type explicitly. For more details, see the Vue documentation on [Generics](https://vuejs.org/api/sfc-script-setup.html#generics).

```vue{3}
<template>
  <el-table :data="tableData">
    <!-- @vue-generic {User} -->
    <el-table-column label="Name">
      <template #default="{ row }">
        {{ row.name }}
      </template>
    </el-table-column>
  </el-table>
</template>

<script lang="ts" setup>
interface User {
  name: string
  address: string
}

const tableData: User[] = [
  {
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles',
  },
]
</script>
```

#### ¿Cómo usar la vista previa de la imagen en la tabla?

```vue{4}
<template>
  <el-table-column width="180">
    <template #default="scope">
      <el-image preview-teleported :preview-src-list="srcList" />
    </template>
  </el-table-column>
</template>
```

#### ¿Por qué la columna no se procesa cuando se usan plantillas DOM?

Typical issue: [#5046](https://github.com/element-plus/element-plus/issues/5046) [#5862](https://github.com/element-plus/element-plus/issues/5862) [#6919](https://github.com/element-plus/element-plus/issues/6919)

Esto se debe a que la especificación HTML solo permite que algunos elementos específicos omitan las etiquetas de cierre, los más comunes son `<input>` y `<img>`. Para todos los demás elementos, si omite la etiqueta de cierre, el analizador nativo HTML pensará que nunca terminó la etiqueta de apertura

For more details please refer to [vue docs](https://vuejs.org/guide/essentials/component-basics.html#self-closing-tags)
