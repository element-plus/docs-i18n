---
title: Radio
lang: es-ES
---

# Radio

Selección única entre múltiples opciones.

:::warning

`label` act as `value` has been **deprecated**, `label` is used only as display text, this action **will be** removed in ^(3.0.0), consider switching to new API.

:::

:::tip

New API `value` has been added in ^(2.6.0), the examples in the document all use the `value`. If you are using a version **less than** ^(2.6.0), please refer to:

:::

```vue
<template>
  <el-radio-group v-model="radio1">
    <!-- works when >=2.6.0, recommended ✔️ not work when <2.6.0 ❌ -->
    <el-radio value="Value 1">Option 1</el-radio>
    <!-- works when <2.6.0, deprecated act as value when >=3.0.0 -->
    <el-radio label="Label 2 & Value 2">Option 2</el-radio>
  </el-radio-group>
</template>
```

## Uso básico

La radio no debería tener demasiadas opciones. De lo contrario, utilice el componente Select en su lugar.

:::demo Crear un componente de radio es fácil, solo necesita vincular una variable al `v-model` de Radio. It equals to the value of `value` of the chosen radio. The type of `value` is `String`, `Number` or `Boolean`.

radio/basic-usage

:::

## Deshabilitar

El atributo `disabled` es utilizado para deshabilitar un Radio.

:::demo Solo necesita agregar el atributo `disabled`.

radio/disabled

:::

## Radio Group

Recomendado para seleccionar opciones que se excluyen mutuamente.

:::demo Combine `el-radio-group` con `el-radio` para mostrar un grupo de Radio. Enlace la variable con `v-model` del elemento `el-radio-group` y asigne el valor del label en `el-radio`. Se provee el evento `change` con el valor actual como parámetro.

radio/radio-group

:::

## Con bordes

:::demo El atributo `border` agrega un borde al elemento Radio.

radio/with-borders

:::

## Options attribute ^(2.11.2)

:::demo Shortcut from basic `el-radio-group` usage. You can customize the alias of the `options` through the `props` attribute.

radio/options

:::

## Radio Button

Radio with button group visual effect.

:::demo Solo necesita cambiar el elemento `el-radio` a `el-radio-button`. You can also set the style of the button when it is active by using `fill` and `text-color`.

radio/radio-button

:::

## API de Radio

### Radio Attributes

| Nombre                | Descripción                                                            | Tipo                                       | Por defecto |
| --------------------- | ---------------------------------------------------------------------- | ------------------------------------------ | ----------- |
| model-value / v-model | valor vinculado                                                        | ^[string] / ^[number] / ^[boolean]         | —           |
| value ^(2.6.0)        | el valor de Radio                                                      | ^[string] / ^[number] / ^[boolean]         | —           |
| label                 | the label of Radio. If there's no `value`, `label` will act as `value` | ^[string] / ^[number] / ^[boolean]         | —           |
| disabled              | si el radio está desactivado                                           | ^[boolean]                                 | false       |
| border                | si añadir un borde alrededor del radio                                 | ^[boolean]                                 | false       |
| size                  | tamaño del radio                                                       | ^[enum]`'large' \| 'default' \| 'small'` | —           |
| name                  | atributo nativo `name`                                                 | ^[string]                                  | —           |

### Radio Events

| Nombre | Descripción                       | Tipo                                                           |
| ------ | --------------------------------- | -------------------------------------------------------------- |
| change | se dispara cuando el valor cambia | ^[Function]`(value: string \| number \| boolean) => void` |

### Radio Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |

## API de RadioGroup

### RadioGroup Attributes

| Nombre                      | Descripción                                                                                    | Tipo                                                            | Por defecto                                              |
| --------------------------- | ---------------------------------------------------------------------------------------------- | --------------------------------------------------------------- | -------------------------------------------------------- |
| model-value / v-model       | valor enlazado                                                                                 | ^[string] / ^[number] / ^[boolean]                              | —                                                        |
| size                        | el tamaño de los botones de radio o radios bordeados                                           | ^[string]                                                       | default                                                  |
| disabled                    | si la anidación de radios está deshabilitada                                                   | ^[boolean]                                                      | false                                                    |
| validate-event              | si se activa la validación del formulario                                                      | ^[boolean]                                                      | true                                                     |
| text-color                  | color de fuente cuando el botón está activo                                                    | ^[string]                                                       | #ffffff                                                  |
| fill                        | color de borde y de fondo cuando el botón está activo                                          | ^[string]                                                       | #409eff                                                  |
| aria-label ^(a11y) ^(2.7.2) | igual que `aria-label` en RadioGroup                                                           | ^[string]                                                       | —                                                        |
| name                        | atributo nativo `name`                                                                         | ^[string]                                                       | —                                                        |
| id                          | atributo nativo `id`                                                                           | ^[string]                                                       | —                                                        |
| label ^(a11y) ^(deprecated) | same as `aria-label` in RadioGroup                                                             | ^[string]                                                       | —                                                        |
| options ^(2.11.2)           | data of the options, the key of `value` and `label` and `disabled` can be customize by `props` | ^[array]`Array<{[key: string]: any}>`                     | —                                                        |
| props ^(2.11.2)             | configuration options                                                                          | ^[object]`{ value?: string, label?: string, disabled?: string}` | `{value: 'value', label: 'label', disabled: 'disabled'}` |
| type ^(2.11.5)              | component type to render options (e.g. `'button'`)                                             | ^[enum]`'radio' \| 'button'`                                   | 'radio'                                                  |

### RadioGroup Events

| Nombre | Descripción                       | Tipo                                                           |
| ------ | --------------------------------- | -------------------------------------------------------------- |
| change | se dispara cuando el valor cambia | ^[Function]`(value: string \| number \| boolean) => void` |

### RadioGroup Slots

| Nombre  | Descripción                          | Subtags             |
| ------- | ------------------------------------ | ------------------- |
| default | personaliza el contenido por defecto | Radio / RadioButton |

## API RadioButton

### RadioButton Attributes

| Name           | Description                                                            | Tipo                               | Por defecto |
| -------------- | ---------------------------------------------------------------------- | ---------------------------------- | ----------- |
| value ^(2.6.0) | el valor de Radio                                                      | ^[string] / ^[number] / ^[boolean] | —           |
| label          | the label of Radio. If there's no `value`, `label` will act as `value` | ^[string] / ^[number] / ^[boolean] | —           |
| disabled       | si el radio está desactivado                                           | ^[boolean]                         | false       |
| name           | atributo 'name' nativo                                                 | ^[string]                          | —           |

### RadioButton Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |
