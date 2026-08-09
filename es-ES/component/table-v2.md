---
title: Virtualized Table
lang: es-ES
---

# Tabla virtualizada ^(beta)

Along with evolutionary web development, table component has always been the most popular component in our web apps especially for dashboards, data analysis. For [Table V1](./table.md), with even just 1000 records of data, it can be very annoying when using it, because of the poor performance.

Con la Tabla Virtualizada, puede renderizar masivos trozos de datos en un parpadeo de ojos.

:::tip

Este componente todavía está **bajo prueba**, úselo bajo su propio riesgo. If you find any bugs or issues, please report them at [GitHub](https://github.com/element-plus/element-plus/issues) for us to fix. Also there were some APIs which are not mentioned in this documentation, some of them were not fully developed yet, which is why they are not mentioned here.

**Even though** Virtualized Table is efficient, when the data load is too large, your **network** and **memory size** can become the bottleneck of your app. So keep in mind that Virtualized Table is never the ultimate solution for everything, consider paginating your data, adding filters etc.

:::

## Uso básico

Let's demonstrate the performance of the Virtualized Table by rendering a basic example with 10 columns and 1000 rows.

:::demo

table-v2/basic

:::

## Auto redimensionar

When you do not want to manually pass the `width` and `height` properties to the table, you can wrap the table component with the AutoResizer. This will automatically update the width and height for you.

Redimensione su navegador para ver cómo funciona.

:::tip

Make sure the parent node of the `AutoResizer` **HAS A FIXED HEIGHT**, since its default height value is set to 100%. Alternatively, you can define it by passing the `style` attribute to `AutoResizer`.

:::

:::demo

table-v2/auto-resizer

:::

## Personalizar el procesador de celdas{#customize-cell-renderer}

Of course, you can render the table cell according to your needs. Here's a simple example of how to customize your cell.

:::demo

table-v2/cell-templating

:::

## Tabla con selecciones

Utilizando el renderizador de celdas personalizado para permitir la selección para la tabla.

:::demo

table-v2/selection

:::

## Edición en línea

Just as we demonstrated with selections above, you can use the same method to enable inline editing.

:::demo

table-v2/inline-editing

:::

## Tabla con estado

Puede destacar su contenido de tabla para distinguir entre "success, information, warning, danger" y otros estados.

To customize the appearance of rows, use the `row-class-name` attribute. For example, every 10th row is highlighted using the `bg-blue-200` class, and every 5th row with the `bg-red-100` class.

:::demo

table-v2/row-class

:::

## Tabla con filas pegajosas

You can make some rows stick to the top of the table, and that can be very easily achieved by using the `fixed-data` attribute.

You can dynamically set the sticky row based on scroll events, as shown in this example.

:::demo

table-v2/sticky-rows

:::

## Tabla con columnas fijas

If you want to have columns stick to the left or right for some reason, you can achieve this by adding special attributes to the table.

Puede establecer el atributo de la columna `fixed` a `true` (representando con `FixedDir.LEFT`) o `FixedDir.LEFT` o `FixedDir.RIGHT`

:::demo

table-v2/fixed-columns

:::

## Encabezado de grupo

By customizing your header renderer, you can group your header as shown in this example.

:::tip

In this case we used `JSX` feature which is not supported in the playground. You may try them out in your local environment or on online IDEs such as `codesandbox`.

Se recomienda que escriba el componente de tabla en JSX, ya que contiene manipulaciones de VNode.

:::

:::demo

table-v2/grouping-header

:::

## Filtros

Virtualized Table provides custom header renderers for creating customized headers. We can then utilize these to render filters.

:::demo

table-v2/filter

:::

## Ordenable

Puede ordenar la tabla con el estado de ordenación.

:::demo

table-v2/sort

:::

## Orden controlado

You can define multiple sortable columns as needed. Keep in mind that if you define multiple sortable columns, the UI may appear confusing to your users, as it becomes unclear which column is currently being sorted.

:::demo

table-v2/controlled-sort

:::

## Intervalo cruzado

When dealing with a large list, it's easy to lose track of the current row and column you are visiting. In such cases, using this feature can be very helpful.

:::demo

table-v2/cross-hovering

:::

## Colspan

The virtualized table doesn't use the built-in `table` element, so `colspan` and `rowspan` behave a bit differently compared to [TableV1](./table.md). However, with a customized row renderer, these features can still be implemented. In this section, we'll demonstrate how to achieve this.

:::demo

table-v2/colspan

:::

## Rowspan

Since we have covered [Colspan](#colspan), it's worth noting that we also have row span. It's a little bit different from colspan but the idea is basically the same.

:::demo

table-v2/rowspan

:::

## Rowspan y Colspan juntos

¡Podemos combinar rowspan y colspan para alcanzar el objetivo de negocio!

:::demo

table-v2/spans

:::

## Datos con formato de árbol

Virtual Table can also render data in a tree-like structure. By clicking the arrow icon, you can expand or collapse the tree nodes.

:::demo

table-v2/tree-data

:::

## Filas de altura dinámica

Virtual Table is capable of rendering rows with dynamic heights. If you're working with data and are uncertain about the content size, this feature is ideal for rendering rows that adjust to the content's height. To enable this, pass down the `estimated-row-height` attribute. The closer the estimated height matches the actual content, the smoother the rendering experience.

:::tip

Each row's height is dynamically measured during rendering the rows. As a result, if you're trying to display a large amount of data, the UI **might be** bouncing.

:::

:::demo

table-v2/dynamic-height

:::

## Vista de detalle

Using dynamic height rendering, you can also display a detailed view within the table.

:::demo

table-v2/detailed-view

:::

## Pie personalizado

Render a customized footer when you want to show a concluding message or information.

:::demo

table-v2/footer

:::

## Renderizado personalizado de vacío

Render a customized empty element.

:::demo

table-v2/empty

:::

## Overlay

Render an overlay on top of the table when you want to show a loading indicator or something else.

:::demo

table-v2/overlay

:::

## Desplazamiento manual

Use the methods provided by Table V2 to scroll manually/programmatically with desired offset/rows.

:::tip

El segundo parámetro para `scrollToRow` es la estrategia de desplazamiento que por defecto es `auto`, calcula la posición para desplazarse por sí misma. If you wish to scroll to a specific position, you can define the strategy yourself. Las opciones disponibles son `"auto" | "center" | "end" | "start" | "smart"`

La diferencia entre `smart` y `auto` es que `auto` es un subconjunto de la estrategia de desplazamiento `smart`.

:::

:::demo

table-v2/manual-scroll

:::

## TableV2 API

### TableV2 Attributes

| Nombre                    | Descripción                                                                                                                                                     | Tipo                                                   | Por defecto |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ | ----------- |
| cache                     | Number of rows rendered in advance to boost the performance                                                                                                     | `number`                                               | 2           |
| estimated-row-height      | La altura estimada de fila para renderizar filas de altura dinámica                                                                                             | `number`                                               | —           |
| header-class              | Nombre de clase personalizado pasado al envoltorio de cabecera                                                                                                  | `string` / Function<[HeaderClassGetter](#typings)>     | —           |
| header-props              | Nombre de las propiedades personalizadas pasadas al componente de cabecera                                                                                      | `object` / Function<[HeaderPropsGetter](#typings)>     | —           |
| header-cell-props         | Nombre de las propiedades personalizadas pasadas al componente de celdas de la cabecera                                                                         | `object` / Function<[HeaderCellPropsGetter](#typings)> | —           |
| header-height             | The height of the header is set by `height`. If given an array, it renders header rows equal to its length                                                      | `number`/ `number[]`                                   | 50          |
| footer-height             | The height of the footer element, when provided, will be part to the calculation of the table's height.                                                         | `number`                                               | 0           |
| row-class                 | Nombre de clase personalizado pasado al envoltorio de fila                                                                                                      | `string` / Function<[RowClassGetter](#typings)>        | —           |
| row-key                   | The key of each row, if not provided, will be the index of the row                                                                                              | `string` / `Symbol` / `number`                         | id          |
| row-props                 | Nombre de las propiedades personalizadas pasadas al componente de fila                                                                                          | `object` / Function<[RowPropsGetter](#typings)>        | —           |
| row-height                | La altura de cada fila, utilizada para calcular la altura total de la tabla                                                                                     | `number`                                               | 50          |
| row-event-handlers        | Una colección de manejadores conectados a cada fila                                                                                                             | `object`\<[RowEventHandlers](#typings)\>             | —           |
| cell-props                | propiedades adicionales pasados a cada célula (excepto las células de la cabecera)                                                                              | `object` / Function<[CellPropsGetter](#typings)>       | —           |
| columns                   | Un array de definiciones de columnas.                                                                                                                           | [Column[]](#column-attribute)                          | —           |
| data                      | Una matriz de datos a procesar en la tabla.                                                                                                                     | [Data[]](#typings)                                     | []          |
| data-getter               | A method to customize data fetch from the data source.                                                                                                          | Function<[DataGetter\<T\>](#typings)>                | —           |
| fixed-data                | Datos para procesar filas sobre el contenido principal y debajo del encabezado                                                                                  | `object`\<[Data](#typings)\>                         | —           |
| expand-column-key         | La clave de columna que indica qué fila se puede expandir                                                                                                       | `string`                                               | —           |
| expanded-row-keys         | Un array de claves para filas expandidas, puede utilizarse con `v-model`                                                                                        | [KeyType[]](#typings)                                  | —           |
| default-expanded-row-keys | Un array de claves para filas expandidas por defecto, **NO REACTIVE**                                                                                           | [KeyType[]](#typings)                                  | —           |
| class                     | Class name for the virtual table, will be applied to all three tables (left, right, main)                                                                       | `string` / `array` / `object`                          | —           |
| fixed                     | Flag indicates the table column's width to be fixed or flexible.                                                                                                | `boolean`                                              | false       |
| width ^(required)         | Width of the table                                                                                                                                              | `number`                                               | —           |
| height ^(required)        | Height of the table                                                                                                                                             | `number`                                               | —           |
| max-height                | Maximum height of the table                                                                                                                                     | `number`                                               | —           |
| indent-size               | horizontal indentation of tree table                                                                                                                            | `number`                                               | 12          |
| h-scrollbar-size          | Indica el tamaño de la barra de desplazamiento horizontal para la tabla, utilizada para prevenir el colapso de la barra de desplazamiento horizontal y vertical | `number`                                               | 6           |
| v-scrollbar-size          | Indica el tamaño de la barra de desplazamiento vertical para la tabla, utilizada para prevenir el colapso de la barra de desplazamiento horizontal y vertical   | `number`                                               | 6           |
| scrollbar-always-on       | Si se activa, la barra de desplazamiento siempre se mostrará en lugar de cuando el ratón se coloca encima de la tabla                                           | `boolean`                                              | false       |
| sort-by                   | Indicador de orden                                                                                                                                              | `object`\<[SortBy](#typings)\>                       | {}          |
| sort-state                | Múltiples indicadores de ordenación                                                                                                                             | `object`\<[SortState](#typings)\>                    | undefined   |

### TableV2 Slots

| Nombre      | Parámetros                                    |
| ----------- | --------------------------------------------- |
| cell        | `object`\<[CellSlotProps](#typings)\>       |
| header      | `object`\<[HeaderSlotProps](#typings)\>     |
| header-cell | `object`\<[HeaderCellSlotProps](#typings)\> |
| row         | `object`\<[RowSlotProps](#typings)\>        |
| footer      | —                                             |
| empty       | —                                             |
| overlay     | —                                             |

### TableV2 Events

| Nombre               | Descripción                                                                                                                     | Parámetros                                       |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| column-sort          | Se invoca cuando la columna está ordenada                                                                                       | `object`\<[ColumnSortParam](#typings)\>        |
| expanded-rows-change | Invocado cuando las filas expandidas cambian                                                                                    | [KeyType[]](#typings)                            |
| end-reached          | Invoked when the end of the table is reached. The callback contain the remain distance, it is the usually the scrollbar height. | ^[Function]`(remainDistance: number) => void` |
| scroll               | Invoked after scrolling                                                                                                         | `object`\<[ScrollParams](#typings)\>           |
| rows-rendered        | Invocado cuando las filas son procesadas                                                                                        | `object`\<[RowsRenderedParams](#typings)\>     |
| row-expand           | Se invoca cuando se expande/contrae el nodo del árbol haciendo clic en el icono de la flecha                                    | `object`\<[RowExpandParams](#typings)\>        |

### TableV2 Exposes

| Método       | Descripción                                                                       | Parámetros                                                                                   |
| ------------ | --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| scrollTo     | Desplazar a una posición determinada                                              | ^[Function]`(param: {scrollLeft?: number, scrollTop?: number}) => void`                   |
| scrollToLeft | Desplazar a una posición horizontal determinada                                   | ^[Function]`(scrollLeft: number) => void`                                                 |
| scrollToTop  | Desplazar a una posición vertical dada                                            | ^[Function]`(scrollTop: number) => void`                                                  |
| scrollToRow  | desplazar a una fila determinada con la estrategia de desplazamiento especificada | ^[Function]`(row: number, strategy?: 'center' \| 'end' \| 'start' \| 'smart') => void` |

:::tip

Note that these are `JavaScript` Objects, so you **CANNOT USE** kebab-case for these attributes

:::

### Column Attribute

| Nombre             | Descripción                                                                         | Tipo                                                                                                                                                                 | Por defecto |
| ------------------ | ----------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| align              | Alineación del contenido de la celda                                                | [Alignment](https://github.com/element-plus/element-plus/blob/b92b22932758f0ddea98810ae248f6ca62f77e25/packages/components/table-v2/src/constants.ts#L6)             | left        |
| class              | Nombre de la clase para la columna                                                  | `string`                                                                                                                                                             | —           |
| key                | Unique identification                                                               | [KeyType](#typings)                                                                                                                                                  | —           |
| dataKey            | Unique identification of data                                                       | [KeyType](#typings)                                                                                                                                                  | —           |
| fixed              | Dirección fija de la columna                                                        | `boolean` / [FixedDir](https://github.com/element-plus/element-plus/blob/b92b22932758f0ddea98810ae248f6ca62f77e25/packages/components/table-v2/src/constants.ts#L11) | false       |
| flexGrow           | CSSProperties flex grow, Only useful when this is not a fixed table                 | `number`                                                                                                                                                             | 0           |
| flexShrink         | CSSProperties flex shrink, Only useful when this is not a fixed table               | `number`                                                                                                                                                             | 1           |
| headerClass        | Utilizado para personalizar la clase de columna de cabecera                         | `string`                                                                                                                                                             | —           |
| hidden             | Si la columna es invisible                                                          | `boolean`                                                                                                                                                            | —           |
| style              | Estilo personalizado para la celda de columna, se fusionará con celda de cuadrícula | ^[object]`CSSProperties`                                                                                                                                             | —           |
| sortable           | Indica si la columna es ordenable                                                   | `boolean`                                                                                                                                                            | —           |
| title              | El texto por defecto renderizado en la celda de cabecera                            | `string`                                                                                                                                                             | —           |
| maxWidth           | Ancho máximo para la columna                                                        | `number`                                                                                                                                                             | —           |
| minWidth           | Ancho mínimo para la columna                                                        | `number`                                                                                                                                                             | —           |
| width ^(required)  | Width for the column                                                                | `number`                                                                                                                                                             | —           |
| cellRenderer       | Renderizado personalizado de celdas                                                 | `VueComponent` / (props: [CellRenderProps](#typings)) => VNode                                                                                                       | —           |
| headerCellRenderer | Renderizado personalizado de cabecera                                               | `VueComponent` / (props: [HeaderRenderProps](#typings)) => VNode                                                                                                     | —           |

## Typings{#typings}

<details>
<summary>Mostrar Declaraciones de Tipo</summary>

```ts
type HeaderClassGetter = (param: {
  columns: Column<any>[]
  headerIndex: number
}) => string

type HeaderPropsGetter = (param: {
  columns: Column<any>[]
  headerIndex: number
}) => Record<string, any>

type HeaderCellPropsGetter = (param: {
  columns: Column<any>[]
  column: Column<any>
  columnIndex: number
  headerIndex: number
  style: CSSProperties
}) => Record<string, any>

type RowClassGetter = (param: {
  columns: Column<any>[]
  rowData: any
  rowIndex: number
}) => string

type RowPropsGetter = (param: {
  columns: Column<any>[]
  rowData: any
  rowIndex: number
}) => Record<string, any>

type CellPropsGetter = (param: {
  column: Column<any>
  columns: Column<any>[]
  columnIndex: number
  cellData: any
  rowData: any
  rowIndex: number
}) => void

type DataGetterParams<T> = {
  columns: Column<T>[]
  column: Column<T>
  columnIndex: number
} & RowCommonParams

type DataGetter<T> = (params: DataGetterParams<T>) => T

type CellRenderProps<T> = {
  cellData: T
  column: Column<T>
  columns: Column<T>[]
  columnIndex: number
  rowData: any
  rowIndex: number
}

type HeaderRenderProps<T> = {
  column: Column<T>
  columns: Column<T>[]
  columnIndex: number
  headerIndex: number
}

type ScrollParams = {
  xAxisScrollDir: 'forward' | 'backward'
  scrollLeft: number
  yAxisScrollDir: 'forward' | 'backward'
  scrollTop: number
}

type CellSlotProps<T> = {
  column: Column<T>
  columns: Column<T>[]
  columnIndex: number
  depth: number
  style: CSSProperties
  rowData: any
  rowIndex: number
  isScrolling: boolean
  expandIconProps?:
    | {
        rowData: any
        rowIndex: number
        onExpand: (expand: boolean) => void
      }
    | undefined
}

type HeaderSlotProps = {
  cells: VNode[]
  columns: Column<any>[]
  headerIndex: number
}

type HeaderCellSlotProps = {
  class: string
  columns: Column<any>[]
  column: Column<any>
  columnIndex: number
  headerIndex: number
  style: CSSProperties
  headerCellProps?: any
  sortBy: SortBy
  sortState?: SortState | undefined
  onColumnSorted: (e: MouseEvent) => void
}

type RowCommonParams = {
  rowData: any
  rowIndex: number
}

type RowEventHandlerParams = {
  rowKey: KeyType
  event: Event
} & RowCommonParams

type RowEventHandler = (params: RowEventHandlerParams) => void
type RowEventHandlers = {
  onClick?: RowEventHandler
  onContextmenu?: RowEventHandler
  onDblclick?: RowEventHandler
  onMouseenter?: RowEventHandler
  onMouseleave?: RowEventHandler
}

type RowsRenderedParams = {
  rowCacheStart: number
  rowCacheEnd: number
  rowVisibleStart: number
  rowVisibleEnd: number
}

type RowSlotProps = {
  columns: Column<any>[]
  rowData: any
  columnIndex: number
  rowIndex: number
  data: any
  key: number | string
  isScrolling?: boolean
  style: CSSProperties
}

type RowExpandParams = {
  expanded: boolean
  rowKey: KeyType
} & RowCommonParams

type Data = {
  [key: KeyType]: any
  children?: Array<any>
}

type FixedData = Data

type KeyType = string | number | symbol

type ColumnSortParam<T> = { column: Column<T>; key: KeyType; order: SortOrder }

enum SortOrder {
  ASC = 'asc',
  DESC = 'desc',
}

enum Alignment {
  LEFT = 'left',
  CENTER = 'center',
  RIGHT = 'right',
}

type SortBy = { key: KeyType; Order: SortOrder }
type SortState = Record<KeyType, SortOrder>
```

</details>

## FAQs

#### How do I render a list with a checkbox in the first column?

Since you are allowed to define your own cell renderer, you can do what the example [Customize Cell Renderer](#customize-cell-renderer) did to render `checkbox` yourself, and maintain the state by yourself.

#### Why does virtualized table provide less features than [TableV1](./table.md)

For virtualized table, we intend to provide less feature and let our users implement their own features as needed. Integrar demasiadas características hace que el código sea difícil de mantener y para la mayoría de los usuarios las características básicas son suficientes. Algunas características clave aún no han sido desarrolladas. ¡Queremos saber tu opinión! Únete a [Discord](https://discord.com/invite/gXK9XNzW3X) para estar atento.
