---
title: DatePickerPanel
lang: es-ES
---

# DatePickerPanel ^(beta)

`DatePickerPanel` is the core component of `DatePicker`.

## Introducir fecha

Selector de fecha básico medido por 'día'.

:::demo

date-picker-panel/basic

:::

## Border

By default the date-picker-panel is bordered but in some case you don't want it.
For example `DatePicker` don't inherit `border`.

:::demo

date-picker-panel/border

:::

## Deshabilitar

The `disabled` attribute determines if the date picker is fully disabled.

:::demo

date-picker-panel/disabled

:::

## Tipos

The measurement is determined by the `type` attribute.

:::demo

date-picker-panel/all-types

:::

## Localización

The default locale of is English, if you need to use other languages, please check [Internationalization](/en-US/guide/i18n)

Note, date time locale (month name, first day of the week ...) are also configured in localization.

## API

### Personalizable

| Nombre                                                                    | Descripción                                                                                                                                                                      | Parámetros                                                                                                                                                                                                                                                                                 | Valore por defecto                                     |
| ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------ |
| model-value / v-model                                                     | binding value, if it is an `range` picker, the length of the array should be 2                                                                                                   | ^[number] / ^[string] / ^[Date] / ^[array]`number[] \| string[] \| Date[]` | ''                                                     |
| border                                                                    | whether the date picker is bordered                                                                                                                                              | ^[boolean]                                                                                                                                                                                                                             | true                                                   |
| disabled                                                                  | si DateTimePicker está deshabilitado                                                                                                                                             | ^[boolean]                                                                                                                                                                                                                             | false                                                  |
| clearable                                                                 | si desea mostrar el botón de borrar                                                                                                                                              | ^[boolean]                                                                                                                                                                                                                             | true                                                   |
| editable ^(2.13.0)     | si el input puede ser editado                                                                                                                                                    | ^[boolean]                                                                                                                                                                                                                             | true                                                   |
| tipo                                                                      | tipo del selector                                                                                                                                                                | ^[enum]`'year' \| 'years' \|'month' \| 'months' \| 'date' \| 'dates' \| 'datetime' \| 'week' \| 'datetimerange' \| 'daterange' \| 'monthrange' \| 'yearrange'`                                                                         | date                                                   |
| default-value                                                             | opcional, fecha por defecto del calendario                                                                                                                                       | ^[object]`Date \| [Date, Date]`                                                                                                                                                                                                        | —                                                      |
| default-time                                                              | opcional, el valor de la hora a usar al seleccionar el rango de fechas                                                                                                           | ^[object]`Date \| [Date, Date]`                                                                                                                                                                                                        | —                                                      |
| value-format                                                              | opcional, formato del valor enlazado. Si no está especificado, el valor enlazado será un objeto Date                                                             | ^[string]                                                                                                                                                                                                                              | —                                                      |
| date-format                                                               | optional, format of the date displayed in input's inner panel                                                                                                                    | ^[string] see [date formats](https://day.js.org/docs/en/display/format)                                                                                                                                                                | YYYY-MM-DD                                             |
| time-format                                                               | optional, format of the time displayed in input's inner panel                                                                                                                    | ^[string] see [date formats](https://day.js.org/docs/en/display/format)                                                                                                                                                                | HH:mm:ss               |
| unlink-panels                                                             | desvincula los dos paneles de fecha en el selector de rango                                                                                                                      | ^[boolean]                                                                                                                                                                                                                             | false                                                  |
| single-panel ^(2.14.0) | show only one panel in range-picker                                                                                                                                              | ^[boolean]                                                                                                                                                                                                                             | false                                                  |
| disabled-date                                                             | una función que determina si una fecha está desactivada con esa fecha como parámetro. Debe devolver un booleano                                                  | ^[Function]`(data: Date) => boolean`                                                                                                                                                                                                   | —                                                      |
| shortcuts                                                                 | si se debe disparar la validacion                                                                                                                                                | ^[array]`Array<{ text: string, value: Date \| Function }>`                                                                                                                                                                             | [] |
| cell-class-name                                                           | establece nombre de clase personalizado                                                                                                                                          | ^[Function]`(data: Date) => string`                                                                                                                                                                                                    | —                                                      |
| show-footer                                                               | whether to show footer where the date picker is one ^[enum]`'dates' \| 'months' \| 'years' \| 'datetime' \| 'datetimerange'` | ^[boolean]                                                                                                                                                                                                                             | false                                                  |
| show-confirm                                                              | whether to show the confirm button                                                                                                                                               | ^[boolean]                                                                                                                                                                                                                             | false                                                  |
| show-week-number                                                          | show the week number besides the week                                                                                                                                            | ^[boolean]                                                                                                                                                                                                                             | false                                                  |

### Slot

| Nombre                                                             | Descripción                                                                           | Parámetros                                                                                                                                    |
| ------------------------------------------------------------------ | ------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| calendar-change                                                    | se dispara cuando se cambia la fecha del calendario. Only for `range` | ^[Function]`(val: [Date, null \| Date]) => void`                                          |
| panel-change                                                       | se dispara cuando se hace clic en el botón de navegación.             | ^[Function]`(date: Date \| [Date, Date], mode: 'month' \| 'year', view?: string) => void` |
| clear ^(2.13.1) | triggers when a clear button is clicked                                               | ^[Function]`() => void`                                                                   |

### Slots

| Nombre      | Descripción                         |
| ----------- | ----------------------------------- |
| por defecto | contenido personalizado de la celda |
| prev-month  | prev month icon                     |
| next-month  | next month icon                     |
| prev-year   | prev year icon                      |
| next-year   | next year icon                      |
