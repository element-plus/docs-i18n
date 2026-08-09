---
title: DateTimePicker
lang: es-ES
---

# DateTimePicker

Seleccionar fecha y hora juntos en un picker.

:::tip

DateTimePicker es derivado de DatePicker y TimePicker. Para una explicación más detallada sobre los atributos, puede referirse a DatePicker y TimePicker.

:::

## Fecha y hora

:::demo Puede seleccionar fecha y hora en un selector al mismo tiempo estableciendo `type` a `datetime`. La forma de utilizar los atajos es la misma que con Date Picker.

datetime-picker/date-and-time

:::

## Formato de fecha y hora

Utilice `format` para controlar el formato del texto visualizado en el input. Utilice `value-format` para controlar el formato del valor enlazado.

Por defecto, el componente acepta y emite un objeto `Date`.

Revise la lista [aquí](https://day.js.org/docs/en/display/format#list-of-all-available-formats) de todos los formatos disponibles de Day.js.

:::warning

Preste atención a la capitalización

:::

:::demo

datetime-picker/date-and-time-formats

:::

## Date and time formats in dropdown panel

Use `date-format` and `time-format` to control displayed text's format in the dropdown panel's input box.

:::demo

datetime-picker/date-and-time-formats-panel

:::

## Date and time range

:::demo You can select date and time range by setting `type` to `datetimerange`.

datetime-picker/date-and-time-range

:::

## Single Panel ^(2.14.0)

:::demo By default date picker ranges have two panels. If you want one panel set the `single-panel` attribute.

datetime-picker/single-panel

:::

## Default time value for start date and end date

:::demo When picking date range on the date panel with type `datetimerange`, `00:00:00` will be used as the default time value for start and end date. We can control it with the `default-time` attribute. `default-time` accepts an array of up to two Date objects. The first item controls time value of the start date and the second item controls time value of the end date.

datetime-picker/default-time

:::

## Custom icon ^(2.8.0)

Custom icons available with slots.

:::demo

datetime-picker/custom-icon

:::

## API

### Attributes

| Nombre                       | Descripción                                                                                                          | Tipo                                                                                                 | Por defecto                        |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------- |
| model-value / v-model        | binding value, if it is an `range` picker, the length of the array should be 2                                       | ^[number] / ^[string] / ^[Date] / ^[array]`number[] \| string[] \| Date[]`                         | ''                                 |
| readonly                     | si DateTimePicker es solo de lectura                                                                                 | ^[boolean]                                                                                           | false                              |
| disabled                     | si DateTimePicker está deshabilitado                                                                                 | ^[boolean]                                                                                           | false                              |
| editable                     | si el input puede ser editado                                                                                        | ^[boolean]                                                                                           | true                               |
| clearable                    | si mostrar el botón de borrado                                                                                       | ^[boolean]                                                                                           | true                               |
| size                         | tamaño del input                                                                                                     | ^[enum]`'large' \| 'default' \| 'small'`                                                           | default                            |
| placeholder                  | placeholder en modo no rango                                                                                         | ^[string]                                                                                            | —                                  |
| start-placeholder            | placeholder para el inicio de fecha en el modo rango                                                                 | ^[string]                                                                                            | —                                  |
| end-placeholder              | placeholder para el fin de fecha en el modo rango                                                                    | ^[string]                                                                                            | —                                  |
| arrow-control                | si se puede modificar la hora utilizando botones con flechas                                                         | ^[boolean]                                                                                           | false                              |
| type                         | tipo del selector                                                                                                    | ^[enum]`'year' \| 'month' \| 'date' \| 'datetime' \| 'week' \| 'datetimerange' \| 'daterange'` | date                               |
| format                       | formato de valor mostrado en el input                                                                                | ^[string] see [date formats](./date-picker.md#date-formats)                                          | YYYY-MM-DD HH:mm:ss                |
| popper-class                 | nombre de clase personalizado para el Dropdown de DatePicker                                                         | ^[string]                                                                                            | —                                  |
| popper-style                 | custom style for DateTimePicker's dropdown                                                                           | ^[string] / ^[object]                                                                                | —                                  |
| popper-options               | Opción de popper personalizada ver más en [popper.js](https://popper.js.org/docs/v2/)                                | ^[object]`Partial<PopperOptions>`                                                              | {}                                 |
| fallback-placements ^(2.8.4) | list of possible positions for Tooltip [popper.js](https://popper.js.org/docs/v2/modifiers/flip/#fallbackplacements) | ^[array]`Placement[]`                                                                                | ['bottom', 'top', 'right', 'left'] |
| placement ^(2.8.4)           | posición del desplegable                                                                                             | `Posición`                                                                                           | bottom                             |
| range-separator              | separador de rango                                                                                                   | ^[string]                                                                                            | '-'                                |
| default-value                | opcional, fecha predeterminada del calendario                                                                        | ^[object]`Date \| [Date, Date]`                                                                     | —                                  |
| default-time                 | el valor por defecto de la hora después de elegir una fecha. La hora `00:00:00` se utilizará si no se especifica     | ^[object]`Date \| [Date, Date]`                                                                     | —                                  |
| value-format                 | opcional, formato del valor enlazado. Si no está especificado, el valor enlazado será un objeto Date                 | ^[string] see [date formats](https://day.js.org/docs/en/display/format)                              | —                                  |
| date-format ^(2.4.0)         | optional, format of the date displayed in input's inner panel                                                        | ^[string] see [date formats](https://day.js.org/docs/en/display/format)                              | YYYY-MM-DD                         |
| time-format ^(2.4.0)         | optional, format of the time displayed in input's inner panel                                                        | ^[string] see [date formats](https://day.js.org/docs/en/display/format)                              | HH:mm:ss                           |
| id                           | same as `id` in native input                                                                                         | ^[string] / ^[array]`[string, string]`                                                               | —                                  |
| name                         | same as `name` in native input                                                                                       | ^[string]                                                                                            | —                                  |
| unlink-panels                | unlink two date-panels in range-picker                                                                               | ^[boolean]                                                                                           | false                              |
| single-panel ^(2.14.0)       | show only one panel in range-picker                                                                                  | ^[boolean]                                                                                           | false                              |
| prefix-icon                  | Custom prefix icon component                                                                                         | ^[string] / `Component`                                                                              | Date                               |
| clear-icon                   | Custom clear icon component                                                                                          | ^[string] / `Component`                                                                              | CircleClose                        |
| shortcuts                    | an object array to set shortcut options                                                                              | ^[array]`Array<{ text: string, value: Date \| Function }>`                                    | —                                  |
| disabled-date                | a function determining if a date is disabled with that date as its parameter. Should return a Boolean                | ^[Function]`(data: Date) => boolean`                                                              | —                                  |
| disabled-hours               | To specify the array of hours that cannot be selected                                                                | ^[Function]`(role: string, comparingDate?: Dayjs) => number[]`                                    | —                                  |
| disabled-minutes             | To specify the array of minutes that cannot be selected                                                              | ^[Function]`(hour: number, role: string, comparingDate?: Dayjs) => number[]`                      | —                                  |
| disabled-seconds             | To specify the array of seconds that cannot be selected                                                              | ^[Function]`(hour: number, minute: number, role: string, comparingDate?: Dayjs) => number[]`      | —                                  |
| cell-class-name              | set custom className                                                                                                 | ^[Function]`(data: Date) => string`                                                               | —                                  |
| teleported                   | whether datetime-picker dropdown is teleported to the body                                                           | ^[boolean]                                                                                           | true                               |
| empty-values ^(2.7.0)        | empty values of component, [see config-provider](./config-provider.md#empty-values-configurations)                   | ^[array]                                                                                             | —                                  |
| value-on-clear ^(2.7.0)      | clear return value, [see config-provider](./config-provider.md#empty-values-configurations)                          | ^[string] / ^[number] / ^[boolean] / ^[Function]                                                     | —                                  |
| show-now ^(2.8.7)            | whether to show the now button                                                                                       | ^[boolean]                                                                                           | true                               |
| show-footer ^(2.10.5)        | whether to show footer where the date picker is one ^[enum]`'datetime' \| 'datetimerange'`                          | ^[boolean]                                                                                           | true                               |
| show-confirm ^(2.11.0)       | whether to show the confirm button                                                                                   | ^[boolean]                                                                                           | true                               |
| show-week-number ^(2.10.3)   | show the week number besides the week                                                                                | ^[boolean]                                                                                           | false                              |

### Events

| Nombre          | Descripción                                                         | Parámetros                                                                                     |
| --------------- | ------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| change          | triggers when user confirms the value or click outside              | ^[Function]`(val: typeof v-model) => void`                                                  |
| blur            | se dispara cuando el input pierde el foco                           | ^[Function]`(e: FocusEvent) => void`                                                        |
| focus           | se dispara cuando el input obtiene el foco                          | ^[Function]`(e: FocusEvent) => void`                                                        |
| clear ^(2.7.7)  | triggers when a clear button is clicked                             | ^[Function]`() => void`                                                                     |
| calendar-change | se dispara cuando se cambia la fecha seleccionada. Only for `range` | ^[Function]`(val: [Date, null \| Date]) => void`                                           |
| panel-change    | triggers when the navigation button click.                          | ^[Function]`(date: Date \| [Date, Date], mode: 'month' \| 'year', view?: string) => void` |
| visible-change  | se dispara cuando el desplegable aparece/desaparece                 | ^[Function]`(visibility: boolean) => void`                                                  |

### Slots

| Nombre              | Descripción                           |
| ------------------- | ------------------------------------- |
| default             | contenido personalizado de la celda   |
| range-separator     | separador de los rangos personalizado |
| prev-month ^(2.8.0) | prev month icon                       |
| next-month ^(2.8.0) | next month icon                       |
| prev-year ^(2.8.0)  | prev year icon                        |
| next-year ^(2.8.0)  | next year icon                        |

### Exposes

| Método        | Descripción                    | Type                       |
| ------------- | ------------------------------ | -------------------------- |
| focus         | focus the DatePicker component | ^[Function]`() => void` |
| blur ^(2.8.7) | blur the DatePicker component  | ^[Function]`() => void` |

## Declaraciones de tipo

<details>
  <summary>Mostrar declaraciones</summary>

```ts
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
