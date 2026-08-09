---
title: Checkbox
lang: es-ES
---

# Checkbox

Un grupo de opciones para manejar múltiples elecciones.

:::warning

`label` act as `value` has been **deprecated**, `label` is used only as display text, this action **will be** removed in ^(3.0.0), consider switching to new API.

:::

:::tip

New API `value` has been added in ^(2.6.0), the examples in the document all use the `value`. If you are using a version **less than** ^(2.6.0) and using `checkbox-group`, please refer to:

:::

```vue
<template>
  <el-checkbox-group v-model="checkList">
    <!-- works when >=2.6.0, recommended ✔️ value not work when <2.6.0 ❌ -->
    <el-checkbox label="Option 1" value="Value 1" />
    <!-- works when <2.6.0, deprecated act as value when >=3.0.0 -->
    <el-checkbox label="Option 2 & Value 2" />
  </el-checkbox-group>
</template>
```

## Uso básico

El checkbox solo se puede utilizar para cambiar entre dos estados.

:::demo Define `v-model`(variable enlazada) en `el-checkbox`. El valor por defecto es un `Boolean` para un `checkbox`, y se convierte en `true` cuando este es seleccionado. El contenido dentro de la etiqueta `el-checkbox` se convertirá en la descripción después del checkbox.

checkbox/basic

:::

## Estado deshabilitado

Estado deshabilitado para el checkbox.

:::demo Establezca el atributo `disabled`.

checkbox/disabled

:::

## Grupo de Checkboxes

Es usado por múltiples checkboxes los cuales están enlazados a un grupo, indica si una opción está seleccionada verificando si esta está marcada.

:::demo El elemento `checkbox-group` puede manejar múltiples checkboxes en un grupo usando `v-model` enlazando a un `Array`. Inside the `el-checkbox` element, `value` is the value of the checkbox. Si en la etiqueta no hay contenido anidado, `label` se mostrara como la descripción al lado del botón del checkbox. `value` also corresponds with the element values in the array. Estará seleccionado si el valor especificado existe en el array y viceversa.

checkbox/grouping

:::

## Options attribute ^(2.11.2)

:::demo Shortcut from basic `el-checkbox-group` usage. You can customize the alias of the `options` through the `props` attribute.

checkbox/options

:::

## Indeterminado

La propiedad `indeterminate` puede ser usada para generar el efecto de marcar todos (check all).

:::demo

checkbox/intermediate

:::

## Mínimo / Máximo de elementos marcados

Las propiedades `min` y `max` pueden limitar la cantidad de elementos seleccionados.

:::demo

checkbox/limitation

:::

## Estilo del botón

Checkbox tipo Botón.

:::demo Solo debe cambiar el elemento `el-checkbox` por el elemento `el-checkbox-button`. Se provee el atributo `size`.

checkbox/button-style

:::

## Con bordes

:::demo El atributo `border` agrega un borde a los Checkboxes.

checkbox/with-border

:::

## API Checkbox

### Checkbox Attributes

| Nombre                         | Descripción                                                                                                                                                             | Tipo                                           | Por defecto |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- | ----------- |
| model-value / v-model          | valor enlazado                                                                                                                                                          | ^[string] / ^[number] / ^[boolean]             | —           |
| value ^(2.6.0)                 | valor del checkbox cuando es usado dentro de un `checkbox-group`                                                                                                        | ^[string] / ^[number] / ^[boolean] / ^[object] | —           |
| label                          | label of the Checkbox when used inside a `checkbox-group`. If there's no value, `label` will act as `value`                                                             | ^[string] / ^[number] / ^[boolean] / ^[object] | —           |
| true-value ^(2.6.0)            | valor del Checkbox si está marcado                                                                                                                                      | ^[string] / ^[number]                          | —           |
| false-value ^(2.6.0)           | valor del Checkbox si no está marcado                                                                                                                                   | ^[string] / ^[number]                          | —           |
| disabled                       | específica si el Checkbox está deshabilitado                                                                                                                            | ^[boolean]                                     | false       |
| border                         | especifica si agrega un borde alrededor del Checkbox                                                                                                                    | ^[boolean]                                     | false       |
| size                           | tamaño del Checkbox                                                                                                                                                     | ^[enum]`'large' \| 'default' \| 'small'`     | —           |
| name                           | atributo `name` nativo                                                                                                                                                  | ^[string]                                      | —           |
| checked                        | especifica si el Checkbox está marcado                                                                                                                                  | ^[boolean]                                     | false       |
| indeterminate                  | Establecer estado indeterminado, sólo responsable del control de estilo                                                                                                 | ^[boolean]                                     | false       |
| validate-event                 | si se activa la validación del formulario                                                                                                                               | ^[boolean]                                     | true        |
| tabindex                       | input tabindex                                                                                                                                                          | ^[string] / ^[number]                          | —           |
| id                             | input id                                                                                                                                                                | ^[string]                                      | —           |
| aria-controls ^(a11y) ^(2.7.2) | igual que [aria-controls](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-controls), tendrá efecto cuando `indeterminar` es `verdadero` | ^[string]                                      | —           |
| aria-label ^(a11y)             | native `aria-label` attribute                                                                                                                                           | ^[string]                                      | —           |
| true-label ^(deprecated)       | value of the Checkbox if it's checked                                                                                                                                   | ^[string] / ^[number]                          | —           |
| false-label ^(deprecated)      | value of the Checkbox if it's not checked                                                                                                                               | ^[string] / ^[number]                          | —           |
| controls ^(a11y) ^(deprecated) | same as [aria-controls](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-controls), takes effect when `indeterminate` is `true`          | ^[string]                                      | —           |

### Checkbox Events

| Nombre | Descripción                       | Tipo                                                           |
| ------ | --------------------------------- | -------------------------------------------------------------- |
| change | se dispara cuando el valor cambia | ^[Function]`(value: string \| number \| boolean) => void` |

### Checkbox Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |

## API de CheckboxGroup

### CheckboxGroup Attributes

| Nombre                      | Descripción                                                                                    | Tipo                                                            | Por defecto                                              |
| --------------------------- | ---------------------------------------------------------------------------------------------- | --------------------------------------------------------------- | -------------------------------------------------------- |
| model-value / v-model       | valor enlazado                                                                                 | ^[array]`string[] \| number[]`                                 | []                                                       |
| size                        | tamaño del Checkbox                                                                            | ^[enum]`'large' \| 'default' \| 'small'`                      | —                                                        |
| disabled                    | específica si los checkboxes anidados están deshabilitados                                     | ^[boolean]                                                      | false                                                    |
| min                         | cantidad mínima de checkboxes que deben ser marcados                                           | ^[number]                                                       | —                                                        |
| max                         | cantidad máxima de checkboxes que pueden ser marcados                                          | ^[number]                                                       | —                                                        |
| aria-label ^(a11y) ^(2.7.2) | native `aria-label` attribute                                                                  | ^[string]                                                       | —                                                        |
| text-color                  | color de las letras cuando el botón está activo                                                | ^[string]                                                       | #ffffff                                                  |
| fill                        | color del borde y de fondo cuando el botón está activo                                         | ^[string]                                                       | #409eff                                                  |
| tag                         | etiqueta de elemento del grupo de checkbox                                                     | ^[string]                                                       | div                                                      |
| validate-event              | si se activa la validación del formulario                                                      | ^[boolean]                                                      | true                                                     |
| label ^(a11y) ^(deprecated) | native `aria-label` attribute                                                                  | ^[string]                                                       | —                                                        |
| options ^(2.11.2)           | data of the options, the key of `value` and `label` and `disabled` can be customize by `props` | ^[array]`Array<{[key: string]: any}>`                     | —                                                        |
| props ^(2.11.2)             | configuration options                                                                          | ^[object]`{ value?: string, label?: string, disabled?: string}` | `{value: 'value', label: 'label', disabled: 'disabled'}` |
| type ^(2.11.5)              | component type to render options (e.g. `'button'`)                                             | ^[enum]`'checkbox' \| 'button'`                                | 'checkbox'                                               |

### CheckboxGroup Events

| Nombre | Descripción                       | Tipo                                                   |
| ------ | --------------------------------- | ------------------------------------------------------ |
| change | se dispara cuando el valor cambia | ^[Function]`(value: string[] \| number[]) => void` |

### CheckboxGroup Slots

| Nombre  | Descripción                          | Subtags                    |
| ------- | ------------------------------------ | -------------------------- |
| default | personaliza el contenido por defecto | Checkbox / Checkbox-button |

## CheckboxButton API

### CheckboxButton Attributes

| Name                      | Description                                                                                                 | Tipo                                           | Por defecto |
| ------------------------- | ----------------------------------------------------------------------------------------------------------- | ---------------------------------------------- | ----------- |
| value ^(2.6.0)            | valor del checkbox cuando es usado dentro de un `checkbox-group`                                            | ^[string] / ^[number] / ^[boolean] / ^[object] | —           |
| label                     | label of the checkbox when used inside a `checkbox-group`. If there's no value, `label` will act as `value` | ^[string] / ^[number] / ^[boolean] / ^[object] | —           |
| true-value ^(2.6.0)       | valor del checkbox si este está marcado                                                                     | ^[string] / ^[number]                          | —           |
| false-value ^(2.6.0)      | valor del checkbox si este no está marcado                                                                  | ^[string] / ^[number]                          | —           |
| disabled                  | especifica si el checkbox está deshabilitado                                                                | ^[boolean]                                     | false       |
| name                      | atributo 'name' nativo                                                                                      | ^[string]                                      | —           |
| checked                   | si el checkbox está marcado                                                                                 | ^[boolean]                                     | false       |
| true-label ^(deprecated)  | value of the checkbox if it's checked                                                                       | ^[string] / ^[number]                          | —           |
| false-label ^(deprecated) | value of the checkbox if it's not checked                                                                   | ^[string] / ^[number]                          | —           |

### CheckboxButton Slots

| Nombre      | Descripción                          |
| ----------- | ------------------------------------ |
| por defecto | personaliza el contenido por defecto |
