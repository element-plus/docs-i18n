---
title: Calendar
lang: es-ES
---

# Calendar

Muestra fechas.

## Básico

:::demo Configure `value` para especificar el mes que se muestra actualmente. Si no se especifica `value`, se muestra el mes actual. `value` soporta enlace bidireccional.

calendar/basic

:::

## Controller Type ^(2.13.1)

:::demo You can set the type of the controller for Calendar header. When setting `select`, you can use `formatter` to customize `label`.

calendar/controller-type

:::

## Contenido personalizado

:::demo Personalice lo que se muestra en la celda del calendario configurando el `scoped-slot` que se llama `dateCell`. En el `scoped-slot` puede obtener la fecha (la fecha de la celda actual), datos (incluyendo el tipo, Si está seleccionado (isSelected), atributo de día). Para obtener más información, consulte la documentación de la API a continuación.

calendar/customize

:::

## Rango

:::demo Defina el atributo `range` para especificar un rango de fechas a visualizar en el calendario. El tiempo de inicio debe ser el lunes, el tiempo de finalización debe ser el domingo y el período no puede exceder los dos meses.

calendar/range

:::

## Cabecera personalizada

:::demo

calendar/header

:::

## Idiomas

El idioma predeterminado es el inglés, si necesita utilizar otros idiomas, por favor revise [Internacionalización](/es-ES/guide/i18n)

Nota, el locale de la fecha y hora (nombre del mes, primer día de la semana ...) también están configurados en la localización.

## API

### Atributos

| Nombre                    | Descripción                                                                                                                                                                                                                                        | Tipo                                                                           | Por defecto |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | ----------- |
| model-value / v-model     | valor enlazado                                                                                                                                                                                                                                     | ^[Date]                                                                        | —           |
| range                     | rango de tiempo, incluyendo el tiempo de inicio y el tiempo final. El tiempo de inicio debe ser el día de inicio de la semana, el tiempo de finalización debe ser el día de finalización de la semana y el período no puede exceder los dos meses. | ^[array]`[Date, Date]`                                                         | —           |
| controller-type ^(2.13.1) | type of the controller for Calendar header                                                                                                                                                                                                         | ^[enum]`'button' \| 'select'`                                                 | button      |
| formatter ^(2.13.1)       | format label when `controller-type` is 'select'                                                                                                                                                                                                    | ^[Function]`(value: number, type: 'year' \| 'month') => string \| number` | —           |

### Slots

| Nombre    | Descripción                                                                                                                                                                                                                                                                    | Tipo                                                                                                                           |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ |
| date-cell | `type` indica el mes al que pertenece la fecha, los valores opcionales son prev-month, current-month, next-month; `isSelected` indica si la fecha está seleccionada; `day` es la fecha formateada en el formato `YYYY-MM-DD`; `date` es el objeto Date que la celda representa | ^[object]`{ data: { type: 'prev-month' \| 'current-month' \| 'next-month', isSelected: boolean, day: string, date: Date } }` |
| header    | contenido de la cabecera del calendario                                                                                                                                                                                                                                        | ^[object]`{ date: string }`                                                                                                    |

### Exposes

| Name                        | Description                                                            | Type                                                                                             |
| --------------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| selectedDay                 | currently selected date                                                | ^[object]`ComputedRef<Dayjs \| undefined>`                                                |
| pickDay                     | select a specific date                                                 | ^[Function]`(day: dayjs.Dayjs) => void`                                                       |
| selectDate                  | select date                                                            | ^[Function]`(type: CalendarDateType) => void`                                                 |
| calculateValidatedDateRange | Calculate the validate date range according to the start and end dates | ^[Function]`(startDayjs: dayjs.Dayjs, endDayjs: dayjs.Dayjs) => [dayjs.Dayjs, dayjs.Dayjs][]` |

## Type Declarations

<details>
  <summary>Show declarations</summary>

```ts
type CalendarDateType =
  'prev-month' | 'next-month' | 'prev-year' | 'next-year' | 'today'
```

</details>
