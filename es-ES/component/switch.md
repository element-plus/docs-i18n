---
title: Switch
lang: es-ES
---

# Switch

Switch es utilizado para realizar cambios entre dos estados opuestos.

## Uso básico

:::demo Enlace `v-model` a una variable de tipo `Boolean`. Las variables CSS `--el-switch-on-color` y `--el-switch-off-color` definen el color de fondo de los dos estados.

switch/basic

:::

## Tamaños

:::demo

switch/sizes

:::

## Texto de descripción

Puede añadir `active-text` y `inactive-text` para mostrar textos. usar el atributo `inline-prompt` para controlar si el texto se muestra dentro del punto.

:::demo Puede agregar los atributos `active-text` y `inactive-text` para mostrar los textos.

switch/text-description

:::

## Mostrar iconos personalizados

:::tip

Utilice el atributo `active-icon` y `inactive-icon` para añadir iconos. Puede pasarle ya sea el nombre del componente (registrado de antemano) o el propio componente que es un componente SVG Vue. Element Plus has provided a set of icon that you can find at [icon](./icon.md)

:::

:::demo Puede añadir `active-icon` y `inactive-icon` para mostrar iconos. usar el atributo `inline-prompt` para controlar si el texto se muestra dentro del punto.

switch/custom-icons

:::

## Tipos de valores extendidos

:::demo Puede establecer los atributos `active-value` y `inactive-value`. Ambos reciben valores de tipo `Boolean`, `String` o `Number`.

switch/extended-value-types

:::

## Deshabilitado

:::demo Agregar el atributo `disabled` desactiva el componente Switch.

switch/disabled

:::

## Cargando

:::demo Ajuste el atributo `loading` a `true` para mostrar el estado de carga en el switch.

switch/loading

:::

## Prevent switching

:::demo establecer la propiedad `before-change`. Si se devuelve `false` o se devuelve una `Promise` y luego se rechaza, dejará de cambiar.

switch/prevent-switching

:::

## Custom action icon ^(2.3.9)

:::demo You can add `active-action-icon` and `inactive-action-icon` attribute to show icons.

switch/custom-action-icon

:::

## Custom action slot ^(2.4.4)

:::demo You can use `active-action` and `inactive-action` slot to customize action.

switch/custom-action-slot

:::

## API

### Attributes

| Name                          | Descripción                                                                                                                                     | Tipo                                                     | Default |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- | ------- |
| model-value / v-model         | valor vinculante, debe ser equivalente al `active-value` o al `inactive-value`. El tipo por defecto es el tipo `boolean`.                       | ^[boolean] / ^[string] / ^[number]                       | false   |
| disabled                      | si Switch esta deshabilitado                                                                                                                    | ^[boolean]                                               | false   |
| loading                       | si el interruptor está en estado de carga                                                                                                       | ^[boolean]                                               | false   |
| size                          | tamaño del interruptor                                                                                                                          | ^[enum]`'' \| 'large' \| 'default' \| 'small'`        | ''      |
| width                         | ancho del componente Switch                                                                                                                     | ^[number] / ^[string]                                    | ''      |
| inline-prompt                 | si el icono o el texto se muestran dentro de un punto, sólo el primer carácter será renderizado para el texto                                   | ^[boolean]                                               | false   |
| active-icon                   | componente del icono que se muestra en `on`, anula `active-text`                                                                                | ^[string] / ^[Component]                                 | —       |
| inactive-icon                 | componente del icono que se muestra cuando está en `off`, anula `inactive-text`                                                                 | ^[string] / ^[Component]                                 | —       |
| active-action-icon ^(2.3.9)   | component of the icon displayed in action when in `on` state                                                                                    | ^[string] / ^[Component]                                 | —       |
| inactive-action-icon ^(2.3.9) | component of the icon displayed in action when in `off` state                                                                                   | ^[string] / ^[Component]                                 | —       |
| active-text                   | text displayed when in `on` state                                                                                                               | ^[string]                                                | ''      |
| inactive-text                 | text displayed when in `off` state                                                                                                              | ^[string]                                                | ''      |
| active-value                  | switch value when in `on` state                                                                                                                 | ^[boolean] / ^[string] / ^[number]                       | true    |
| inactive-value                | switch value when in `off` state                                                                                                                | ^[boolean] / ^[string] / ^[number]                       | false   |
| name                          | input name of Switch                                                                                                                            | ^[string]                                                | ''      |
| validate-event                | whether to trigger form validation                                                                                                              | ^[boolean]                                               | true    |
| before-change                 | before-change hook before the switch state changes. If `false` is returned or a `Promise` is returned and then is rejected, will stop switching | ^[Function]`() => Promise<boolean> \| boolean` | —       |
| id                            | id for input                                                                                                                                    | ^[string]                                                | —       |
| tabindex                      | tabindex for input                                                                                                                              | ^[string] / ^[number]                                    | —       |
| aria-label ^(a11y) ^(2.7.2)   | same as `aria-label` in native input                                                                                                            | ^[string]                                                | —       |
| active-color ^(deprecated)    | background color when in `on` state ( use CSS var `--el-switch-on-color` instead )                                                              | ^[string]                                                | ''      |
| inactive-color ^(deprecated)  | background color when in `off` state ( use CSS var `--el-switch-off-color` instead )                                                            | ^[string]                                                | ''      |
| border-color ^(deprecated)    | border color of the switch ( use CSS var `--el-switch-border-color` instead )                                                                   | ^[string]                                                | ''      |
| label ^(a11y) ^(deprecated)   | same as `aria-label` in native input                                                                                                            | ^[string]                                                | —       |

### Events

| Name   | Descripción                       | Type                                                         |
| ------ | --------------------------------- | ------------------------------------------------------------ |
| change | se dispara cuando el valor cambia | ^[Function]`(val: boolean \| string \| number) => void` |

### Switch Slots

| Name                     | Descripción                |
| ------------------------ | -------------------------- |
| active-action ^(2.4.4)   | customize active action    |
| inactive-action ^(2.4.4) | customize inactive action  |
| active ^(2.13.0)         | customize active content   |
| inactive ^(2.13.0)       | customize inactive content |

### Exposes

| Método | Description                          | Type                       |
| ------ | ------------------------------------ | -------------------------- |
| focus  | manual focus to the switch component | ^[Function]`() => void` |
