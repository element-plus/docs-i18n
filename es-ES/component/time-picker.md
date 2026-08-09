---
title: TimePicker
lang: es-ES
---

# TimePicker

Use el Time Picker para input de tipo time.

## Selector de tiempo arbitrario

Puede elegir un tiempo arbitrario.

:::demo por defecto, puede desplazar la rueda del ratón para elegir la hora, alternativamente puede usar las flechas de control cuando se establece el atributo `arrow-control`.

time-picker/basic

:::

## Limitar el rango de tiempo

También puede limitar el rango de tiempo.

:::demo Limite el intervalo de tiempo especificando `disabledHours` `disabledMinutes` y `disabledSeconds`.

time-picker/basic-range

:::

## Rango de tiempo arbitrario

Es posible escoger un rango de tiempo arbitrario.

:::demo Podemos dar la opción de elegir un rango de tiempo agregando el atributo `is-range`. También, `arrow-control` está soportado en modo de rango.

time-picker/range

:::

## API

### Atributos

| Nombre                       | Descripción                                                                                                          | Tipo                                                                                               | Por defecto                        |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | ---------------------------------- |
| model-value / v-model        | valor enlazado, si es un array, la longitud debe ser de 2                                                            | ^[number] / ^[string] / ^[object]`Date \| [Date, Date] \| [number, number] \| [string, string]` | ''                                 |
| readonly                     | si el Time Picker está en modo de sólo lectura                                                                       | ^[boolean]                                                                                         | false                              |
| disabled                     | si el Time Picker se encuentra deshabilitado                                                                         | ^[boolean]                                                                                         | false                              |
| editable                     | si el input puede ser editado                                                                                        | ^[boolean]                                                                                         | true                               |
| clearable                    | si mostrar el botón de borrado                                                                                       | ^[boolean]                                                                                         | true                               |
| size                         | tamaño del input                                                                                                     | ^[enum]`'large' \| 'default' \| 'small'`                                                         | —                                  |
| placeholder                  | placeholder en modo no rango                                                                                         | ^[string]                                                                                          | ''                                 |
| start-placeholder            | placeholder para el tiempo de inicio en modo de rango                                                                | ^[string]                                                                                          | —                                  |
| end-placeholder              | placeholder para el tiempo de finalización en modo de rango                                                          | ^[string]                                                                                          | —                                  |
| is-range                     | si es posible escoger un rango de tiempo, solo funciona con                                                          | ^[boolean]                                                                                         | false                              |
| arrow-control                | si es posible escoger el tiempo usando los botones de flecha                                                         | ^[boolean]                                                                                         | false                              |
| popper-class                 | nombre de clase personalizada para el dropdown del Time Picker                                                       | ^[string]                                                                                          | ''                                 |
| popper-style                 | custom style for TimePicker's dropdown                                                                               | ^[string] / ^[object]                                                                              | —                                  |
| popper-options               | Opción de popper personalizada ver más en [popper.js](https://popper.js.org/docs/v2/)                                | ^[object]`Partial<PopperOptions>`                                                            | {}                                 |
| fallback-placements ^(2.8.4) | list of possible positions for Tooltip [popper.js](https://popper.js.org/docs/v2/modifiers/flip/#fallbackplacements) | ^[array]`Placement[]`                                                                              | ['bottom', 'top', 'right', 'left'] |
| placement ^(2.8.4)           | posición del desplegable                                                                                             | `Posición`                                                                                         | bottom                             |
| range-separator              | separador de rango                                                                                                   | ^[string]                                                                                          | '-'                                |
| format                       | formato en que se muestra el valor en el input                                                                       | ^[string] see [date formats](./date-picker.md#date-formats)                                        | —                                  |
| default-value                | opcional, fecha predeterminada del calendario                                                                        | ^[Date] / ^[array]`[Date, Date]`                                                                   | —                                  |
| value-format                 | optional, format of binding value. If not specified, the binding value will be a Date object                         | ^[string] see [date formats](./date-picker.md#date-formats)                                        | —                                  |
| id                           | igual que `id` en el input nativo                                                                                    | ^[string] / ^[array]`[string, string]`                                                             | —                                  |
| name                         | como `name` en input nativo                                                                                          | ^[string]                                                                                          | ''                                 |
| aria-label ^(a11y) ^(2.7.2)  | igual que `aria-label` en el input nativo                                                                            | ^[string]                                                                                          | —                                  |
| prefix-icon                  | Personaliza el componente de icono de prefijo                                                                        | ^[string] / ^[Component]                                                                           | Clock                              |
| clear-icon                   | Personaliza el componente de icono de limpieza                                                                       | ^[string] / ^[Component]                                                                           | CircleClose                        |
| disabled-hours               | Especifica el array de horas que no se pueden seleccionar                                                            | ^[Function]`(role: string, comparingDate?: Dayjs) => number[]`                                  | —                                  |
| disabled-minutes             | Especifica el array de minutos que no se pueden seleccionar                                                          | ^[Function]`(hour: number, role: string, comparingDate?: Dayjs) => number[]`                    | —                                  |
| disabled-seconds             | Especifica el array de segundos que no se pueden seleccionar                                                         | ^[Function]`(hour: number, minute: number, role: string, comparingDate?: Dayjs) => number[]`    | —                                  |
| teleported                   | si el menú desplegable del time-picker se teletransporta al body                                                     | ^[boolean]                                                                                         | true                               |
| tabindex                     | orden de tabulación para el Input                                                                                    | ^[string] / ^[number]                                                                              | 0                                  |
| empty-values ^(2.7.0)        | empty values of component, [see config-provider](./config-provider.md#empty-values-configurations)                   | ^[array]                                                                                           | —                                  |
| value-on-clear ^(2.7.0)      | clear return value, [see config-provider](./config-provider.md#empty-values-configurations)                          | ^[string] / ^[number] / ^[boolean] / ^[Function]                                                   | —                                  |
| save-on-blur ^(2.13.4)       | Whether to auto-fill the input with the current time on focus when no value is selected                              | ^[boolean]                                                                                         | true                               |
| label ^(a11y) ^(deprecated)  | same as `aria-label` in native input                                                                                 | ^[string]                                                                                          | —                                  |

### Eventos

| Nombre         | Descripción                                                       | Tipo                                                                                                                 |
| -------------- | ----------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| change         | se lanza cuando el usuario confirma el valor                      | ^[Function]`(val: number \| string \| Date \| [number, number] \| [string, string] \| [Date, Date]) => void` |
| blur           | se dispara cuando se pierde el foco                               | ^[Function]`(e: FocusEvent) => void`                                                                              |
| focus          | se dispara cuando se obtiene el foco                              | ^[Function]`(e: FocusEvent) => void`                                                                              |
| clear ^(2.7.7) | triggers when the clear icon is clicked in a clearable TimePicker | ^[Function]`() => void`                                                                                           |
| visible-change | se dispara cuando aparece/desaparece el desplegable               | ^[Function]`(visibility: boolean) => void`                                                                        |

### Expuesto

| Nombre                | Descripción                    | Tipo                       |
| --------------------- | ------------------------------ | -------------------------- |
| focus                 | focus the TimePicker component | ^[Function]`() => void` |
| blur                  | blur the TimePicker component  | ^[Function]`() => void` |
| handleOpen ^(2.2.16)  | abre el popper de TimePicker   | ^[Function]`() => void` |
| handleClose ^(2.2.16) | cierra el popper de TimePicker | ^[Function]`() => void` |

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
