---
title: DatePicker
lang: es-ES
---

# DatePicker

Utilice Date Picker para introducir fechas.

## Introducir fecha

Selector de fecha básico medido por 'día'.

:::demo La medida está determinada por el atributo `type`. Puede habilitar opciones rápidas a través de la propiedad `shortcuts`. Las fechas desactivadas se ajustan mediante `disabledDate`, que es una función.

date-picker/enter-date

:::

## Otras mediciones

You can choose week, month, year, quarter or multiple dates by extending the standard date picker component.

:::demo

date-picker/other-measurements

:::

## Rango de fechas

Se admite la selección de un rango de fechas.

:::demo Cuando está en modo rango, los paneles izquierdo y derecho están enlazados por defecto. Si desea que los dos paneles cambien los meses actuales de forma independiente, puede utilizar el atributo `unlink-panels`.

date-picker/date-range

:::

## Rango de mes

Se admite la selección de un periodo de meses.

:::demo Cuando está en modo rango, los paneles izquierdo y derecho están enlazados por defecto. Si desea que los dos paneles cambien los años actuales de forma independiente, puede utilizar el atributo `unlink-panels`.

date-picker/month-range

:::

## Year Range ^(2.8.0)

Picking a year range is supported.

:::demo When in range mode, the left and right panels are linked by default. If you want the two panels to switch years independently, you can use the `unlink-panels` attribute.

date-picker/year-range

:::

## Quarter Range ^(2.14.5)

Picking a quarter range is supported.

:::demo Cuando está en modo rango, los paneles izquierdo y derecho están enlazados por defecto. If you want the two panels to switch years independently, you can use the `unlink-panels` attribute.

date-picker/quarter-range

:::

## Single Panel ^(2.14.0)

:::demo By default date picker ranges have two panels. If you want one panel set the `single-panel` attribute.

date-picker/single-panel

:::

## Valor por defecto

Si el usuario no ha elegido una fecha, muestra el calendario de hoy por defecto. Puede utilizar `default-value` para fijar otra fecha. Su valor debe ser analizable por `new Date()`.

Si el tipo es `daterange`, `default-value` establece el valor para el calendario del lado izquierdo.

:::demo

date-picker/default-value

:::

## Formatos de Fecha

Utilice `format` para controlar el formato del texto visualizado en el input. Utilice `value-format` para controlar el formato del valor vinculado.

Por defecto, el componente acepta y emite un objeto `Date`.

Revise la lista [aquí](https://day.js.org/docs/en/display/format#list-of-all-available-formats) de todos los formatos disponibles de Day.js.

:::warning

Preste atención a la capitalización

:::

:::demo

date-picker/date-formats

:::

## Hora por defecto para comienzo y fin de fecha

Al seleccionar un rango de fechas, puede asignar la parte de la hora para la fecha de inicio y la fecha de finalización.

:::demo Por defecto, la parte de la hora de la fecha de inicio y la fecha de fin son para ambos de `00:00:00`. Configurar `default-time` puede cambiar la hora respectivamente. Acepta un array de hasta dos objetos de fecha. La primera cadena establece la hora para la fecha de inicio y la segunda para la fecha de finalización.

date-picker/default-time

:::

## Establecer contenido personalizado del prefijo

El contenido del prefijo puede ser personalizado.

:::demo Configurando `prefix-icon` al componente que importas de otro .vue o generado por la función de renderizado.

date-picker/custom-prefix-icon

:::

## Contenido personalizado

The content of cell can be customized, in scoped-slot you can get the cell data. Note that the custom content structure should be consistent with the default structure, otherwise style misalignment may occur.

:::demo

date-picker/custom-content

:::

## Custom icon ^(2.8.0)

Custom icons available with slots.

:::demo

date-picker/custom-icon

:::

Para detalles de datos, por favor refiérase a:

```ts
interface DateCell {
  column: number
  customClass: string | undefined
  disabled: boolean
  end: boolean
  inRange: boolean
  row: number
  selected: Dayjs | undefined
  isCurrent: boolean | undefined
  isSelected: boolean
  renderText: string | undefined
  start: boolean
  text: number
  timestamp: number
  date: Date
  dayjs: Dayjs
  type: 'normal' | 'today' | 'week' | 'next-month' | 'prev-month'
}
```

## Localización

El idioma predeterminado es el inglés, si necesita utilizar otros idiomas, por favor revise [Internacionalización](/es-ES/guide/i18n)

Nota, el locale de la fecha y hora (nombre del mes, primer día de la semana ...) también están configurados en la localización.

## API

### Attributes

| Nombre                       | Descripción                                                                                                                           | Tipo                                                                                                                                                                                                                      | Default                            |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------- |
| model-value / v-model        | binding value, if it is an `range` picker, the length of the array should be 2                                                        | ^[number] / ^[string] / ^[Date] / ^[array]`number[] \| string[] \| Date[]`                                                                                                                                              | ''                                 |
| readonly                     | si DatePicker es solo de lectura                                                                                                      | ^[boolean]                                                                                                                                                                                                                | false                              |
| disabled                     | si DatePicker está deshabilitado                                                                                                      | ^[boolean]                                                                                                                                                                                                                | false                              |
| size                         | tamaño del input                                                                                                                      | ^[enum]`'' \| 'large' \| 'default' \| 'small'`                                                                                                                                                                         | —                                  |
| editable                     | si el input es editable                                                                                                               | ^[boolean]                                                                                                                                                                                                                | true                               |
| clearable                    | si se muestra el botón de borrado                                                                                                     | ^[boolean]                                                                                                                                                                                                                | true                               |
| placeholder                  | placeholder en modo no rango                                                                                                          | ^[string]                                                                                                                                                                                                                 | ''                                 |
| start-placeholder            | placeholder para el inicio de fecha en el modo rango                                                                                  | ^[string]                                                                                                                                                                                                                 | —                                  |
| end-placeholder              | placeholder para el fin de fecha en el modo rango                                                                                     | ^[string]                                                                                                                                                                                                                 | —                                  |
| type                         | type of the picker. `quarter`, `quarters`, and `quarterrange` are supported since ^(2.14.5)                                           | ^[enum]`'year' \| 'years' \|'month' \| 'months' \| 'date' \| 'dates' \| 'datetime' \| 'week' \| 'quarter' \| 'quarters' \| 'datetimerange' \| 'daterange' \| 'monthrange' \| 'yearrange' \| 'quarterrange'` | date                               |
| format                       | formato en que se muestra el valor en el input                                                                                        | ^[string] see [date formats](#date-formats)                                                                                                                                                                               | YYYY-MM-DD                         |
| popper-class                 | nombre de clase personalizada para el dropdown de DatePicker                                                                          | ^[string]                                                                                                                                                                                                                 | —                                  |
| popper-style                 | custom style for DatePicker's dropdown                                                                                                | ^[string] / ^[object]                                                                                                                                                                                                     | —                                  |
| popper-options               | Opción de popper personalizada ver más en [popper.js](https://popper.js.org/docs/v2/)                                                 | ^[object]`Partial<PopperOptions>`                                                                                                                                                                                   | {}                                 |
| range-separator              | separador de rango                                                                                                                    | ^[string]                                                                                                                                                                                                                 | '-'                                |
| default-value                | opcional, fecha por defecto del calendario                                                                                            | ^[object]`Date \| [Date, Date]`                                                                                                                                                                                          | —                                  |
| default-time                 | opcional, el valor de la hora a usar al seleccionar el rango de fechas                                                                | ^[object]`Date \| [Date, Date]`                                                                                                                                                                                          | —                                  |
| value-format                 | opcional, formato del valor enlazado. Si no está especificado, el valor enlazado será un objeto Date                                  | ^[string] see [date formats](#date-formats)                                                                                                                                                                               | —                                  |
| id                           | igual que `id` en entrada nativa                                                                                                      | ^[string] / ^[array]`[string, string]`                                                                                                                                                                                    | —                                  |
| name                         | igual que `name` en la entrada nativa                                                                                                 | ^[string] / ^[array]`[string, string]`                                                                                                                                                                                    | ''                                 |
| unlink-panels                | desvincula los dos paneles de fecha en el selector de rango                                                                           | ^[boolean]                                                                                                                                                                                                                | false                              |
| single-panel ^(2.14.0)       | show only one panel in range-picker                                                                                                   | ^[boolean]                                                                                                                                                                                                                | false                              |
| prefix-icon                  | custom prefix icon component. By default, if the value of `type` is `TimeLikeType`, the value is `Clock`, else is `Calendar`          | ^[string] / ^[object]`Component`                                                                                                                                                                                          | ''                                 |
| clear-icon                   | personaliza el componente de icono de limpieza                                                                                        | ^[string] / ^[object]`Component`                                                                                                                                                                                          | `CircleClose`                      |
| validate-event               | si se activa la validación del formulario                                                                                             | ^[boolean]                                                                                                                                                                                                                | true                               |
| disabled-date                | una función que determina si una fecha está desactivada con esa fecha como parámetro. Debe devolver un booleano                       | ^[Function]`(data: Date) => boolean`                                                                                                                                                                                   | —                                  |
| shortcuts                    | un array de objetos para establecer opciones de acceso directo                                                                        | ^[array]`Array<{ text: string, value: Date \| Function }>`                                                                                                                                                         | []                                 |
| cell-class-name              | establece nombre de clase personalizado                                                                                               | ^[Function]`(data: Date) => string`                                                                                                                                                                                    | —                                  |
| teleported                   | si el menú desplegable del selector de fecha se teletransporta al body                                                                | ^[boolean]                                                                                                                                                                                                                | true                               |
| empty-values ^(2.7.0)        | empty values of component, [see config-provider](./config-provider.md#empty-values-configurations)                                    | ^[array]                                                                                                                                                                                                                  | —                                  |
| value-on-clear ^(2.7.0)      | clear return value, [see config-provider](./config-provider.md#empty-values-configurations)                                           | ^[string] / ^[number] / ^[boolean] / ^[Function]                                                                                                                                                                          | —                                  |
| fallback-placements ^(2.8.4) | list of possible positions for Tooltip [popper.js](https://popper.js.org/docs/v2/modifiers/flip/#fallbackplacements)                  | ^[array]`Placement[]`                                                                                                                                                                                                     | ['bottom', 'top', 'right', 'left'] |
| placement ^(2.8.4)           | position of dropdown                                                                                                                  | `Placement`                                                                                                                                                                                                               | bottom                             |
| show-footer ^(2.10.5)        | whether to show footer                                                                                                                | ^[boolean]                                                                                                                                                                                                                | true                               |
| show-confirm ^(2.11.0)       | whether to show the confirm button                                                                                                    | ^[boolean]                                                                                                                                                                                                                | true                               |
| show-week-number ^(2.10.3)   | show the week number besides the week                                                                                                 | ^[boolean]                                                                                                                                                                                                                | false                              |
| automatic-dropdown ^(2.11.4) | this prop decides if the date picker panel pops up when the input is focused. (The default value will be set to false in version 3.0) | ^[boolean]                                                                                                                                                                                                                | true                               |

### Events

| Nombre          | Descripción                                                           | Type                                                                                           |
| --------------- | --------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| change          | triggers when user confirms the value or click outside                | ^[Function]`(val: typeof v-model) => void`                                                  |
| blur            | se dispara cuando el input pierde el foco                             | ^[Function]`(e: FocusEvent) => void`                                                        |
| focus           | se dispara cuando el input obtiene el foco                            | ^[Function]`(e: FocusEvent) => void`                                                        |
| clear ^(2.7.7)  | triggers when a clear button is clicked                               | ^[Function]`() => void`                                                                     |
| calendar-change | triggers when the calendar selected date is changed. Only for `range` | ^[Function]`(val: [Date, null \| Date]) => void`                                           |
| panel-change    | se dispara cuando se hace clic en el botón de navegación.             | ^[Function]`(date: Date \| [Date, Date], mode: 'month' \| 'year', view?: string) => void` |
| visible-change  | se dispara cuando el desplegable aparece/desaparece                   | ^[Function]`(visibility: boolean) => void`                                                  |

### Slots

| Name                | Descripción                    |
| ------------------- | ------------------------------ |
| default             | custom cell content            |
| range-separator     | custom range separator content |
| prev-month ^(2.8.0) | prev month icon                |
| next-month ^(2.8.0) | next month icon                |
| prev-year ^(2.8.0)  | prev year icon                 |
| next-year ^(2.8.0)  | next year icon                 |

### Exposes

| Nombre                | Descripción                    | Type                       |
| --------------------- | ------------------------------ | -------------------------- |
| focus                 | focus the DatePicker component | ^[Function]`() => void` |
| blur ^(2.8.7)         | blur the DatePicker component  | ^[Function]`() => void` |
| handleOpen ^(2.2.16)  | open the DatePicker popper     | ^[Function]`() => void` |
| handleClose ^(2.2.16) | close the DatePicker popper    | ^[Function]`() => void` |

## Type Declarations

<details>
  <summary>Show declarations</summary>

```ts
import type { Options as PopperOptions } from '@popperjs/core'

type TimeLikeType = 'datetime' | 'datetimerange'

type Placement =
  | 'top'
  | 'top-start'
  | 'top-end'
  | 'bottom'
  | 'bottom-start'
  | 'bottom-end'
  | 'left'
  | 'left-start'
  | 'left-end'
  | 'right'
  | 'right-start'
  | 'right-end'
```

</details>
