---
title: TimeSelect
lang: es-ES
---

# TimeSelect

Use el Time Select para input de tipo time.

El intervalo de tiempo disponible es de 00:00 a 23:59

## Selector de tiempo fijo

Provee una lista de tiempo fijo para que los usuarios escojan.

:::demo Use el tag `el-time-select`, se pueden asignar tiempo de inicio, tiempo de finalización y salto de tiempo con `start`, `end` y `step`.

time-select/basic

:::

## Formato de hora

Use `format` para controlar el formato de hora (horas y minutos).

Revise la lista [aquí](https://day.js.org/docs/en/display/format#list-of-all-available-formats) de todos los formatos disponibles de Day.js.

:::warning

Preste atención a la capitalización

:::

:::demo

time-select/time-formats

:::

## Rango de tiempo fijo

Si al principio se escoge la hora de inicio ( end ) el estado de la hora de final ( start ) cambiará en consecuencia.

:::demo

time-select/time-range

:::

## API

### Atributos

| Nombre                    | Descripción                                                                                        | Tipo                                                                                             | Por defecto |
| ------------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ | ----------- |
| model-value / v-model     | valor vinculado                                                                                    | ^[string]                                                                                        | —           |
| disabled                  | si el TimeSelect se encuentra deshabilitado                                                        | ^[boolean]                                                                                       | false       |
| editable                  | si el input puede ser editado                                                                      | ^[boolean]                                                                                       | true        |
| clearable                 | si mostrar el botón de borrado                                                                     | ^[boolean]                                                                                       | true        |
| include-end-time ^(2.9.3) | whether `end` is included in options                                                               | ^[boolean]                                                                                       | false       |
| size                      | tamaño del input                                                                                   | ^[enum]`'large' \| 'default' \| 'small'`                                                       | default     |
| placeholder               | placeholder en un modo fuera de rango                                                              | ^[string]                                                                                        | —           |
| name ^(2.13.3)            | como `name` en input nativo                                                                        | ^[string]                                                                                        | —           |
| effect                    | Popover tiene dos temas: `dark` y `light`                                                          | ^[string] / ^[enum]`'dark' \| 'light'`                                                          | light       |
| prefix-icon               | personaliza el componente de icono del prefijo                                                     | ^[string] / ^[Component]                                                                         | Clock       |
| clear-icon                | personaliza el componente de icono de limpieza                                                     | ^[string] / ^[Component]                                                                         | CircleClose |
| start                     | tiempo de inicio                                                                                   | ^[string]                                                                                        | 09:00       |
| end                       | tiempo de finalización                                                                             | ^[string]                                                                                        | 18:00       |
| step                      | salto de tiempo                                                                                    | ^[string]                                                                                        | 00:30       |
| min-time                  | tiempo mínimo, cualquier tiempo antes de éste será deshabilitado                                   | ^[string]                                                                                        | —           |
| max-time                  | tiempo máximo, cualquier tiempo después de éste será deshabilitado                                 | ^[string]                                                                                        | —           |
| format                    | establecer formato de hora                                                                         | ^[string] see [formats](https://day.js.org/docs/en/display/format#list-of-all-available-formats) | HH:mm       |
| empty-values ^(2.7.0)     | empty values of component, [see config-provider](./config-provider.md#empty-values-configurations) | ^[array]                                                                                         | —           |
| value-on-clear ^(2.7.0)   | clear return value, [see config-provider](./config-provider.md#empty-values-configurations)        | ^[string] / ^[number] / ^[boolean] / ^[Function]                                                 | —           |
| popper-class ^(2.11.4)    | custom class name for TimeSelect's dropdown                                                        | ^[string]                                                                                        | ''          |
| popper-style ^(2.11.4)    | custom style for TimeSelect's dropdown                                                             | ^[string] / ^[object]                                                                            | —           |

### Eventos

| Nombre         | Descripción                                                       | Tipo                                        |
| -------------- | ----------------------------------------------------------------- | ------------------------------------------- |
| change         | se lanza cuando el usuario confirma el valor                      | ^[Function]`(value: string) => void`     |
| blur           | se dispara cuando se pierde el foco                               | ^[Function]`(event: FocusEvent) => void` |
| focus          | se dispara cuando se obtiene el foco                              | ^[Function]`(event: FocusEvent) => void` |
| clear ^(2.7.7) | triggers when the clear icon is clicked in a clearable TimeSelect | ^[Function]`() => void`                  |

### Expuesto

| Método | Descripción                          | Tipo                       |
| ------ | ------------------------------------ | -------------------------- |
| focus  | coloca el foco en el elemento actual | ^[Function]`() => void` |
| blur   | quitar el foco en el input           | ^[Function]`() => void` |
