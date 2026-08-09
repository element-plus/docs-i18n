---
title: Collapse
lang: es-ES
---

# Collapse

Use Collapse para almacenar contenidos.

## Uso básico

Puede expandir múltiples paneles

:::demo

collapse/basic

:::

## Acordeón

En modo acordeón solo un panel puede ser expandido a la vez

:::demo Active el modo acordeón usado el atributo `accordion`.

collapse/accordion

:::

## Título personalizado

Además de usar el atributo `title`, se puede personalizar el título del panel con slots con nombre, esto hace posible agregar contenido personalizado, por ejemplo: iconos.

:::tip

Starting from version ^(2.9.10), the `title` slot provides an `isActive` property that indicates whether the current collapse item is active.

:::

:::demo

collapse/customization

:::

## Custom icon ^(2.8.3)

Besides using the `icon` attribute, you can customize icon of panel item with named slots, which makes adding custom content.

:::demo

collapse/custom-icon

:::

## Custom icon position ^(2.9.10)

using the `expand-icon-position` attribute, you can customize icon position.

:::demo

collapse/custom-icon-position

:::

## Prevent collapsing ^(2.9.11)

set the `before-collapse` property, If `false` is returned or a `Promise` is returned and then is rejected, will stop collapsing.

:::demo

collapse/prevent-collapsing

:::

## Collapse API

### Collapse Attributes

| Nombre                         | Descripción                                                                                                                                          | Tipo                                                     | Default |
| ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- | ------- |
| model-value / v-model          | currently active panel, the type is `string` in accordion mode, otherwise it is `array`                                                              | ^[string] / ^[array]                                     | []      |
| accordion                      | si desea activar el modo de acordeón                                                                                                                 | ^[boolean]                                               | false   |
| expand-icon-position ^(2.9.10) | set expand icon position                                                                                                                             | ^[enum]`'left' \| 'right'`                              | right   |
| before-collapse ^(2.9.11)      | before-collapse hook before the collapse state changes. If `false` is returned or a `Promise` is returned and then is rejected, will stop collapsing | ^[Function]`() => Promise<boolean> \| boolean` | —       |

### Collapse Events

| Nombre | Descripción                                                                                                   | Type                                                    |
| ------ | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| change | triggers when active panels change, the parameter type is `string` in accordion mode, otherwise it is `array` | ^[Function]`(activeNames: array \| string) => void` |

### Collapse Slots

| Nombre  | Descripción                          | Subtags       |
| ------- | ------------------------------------ | ------------- |
| default | personaliza el contenido por defecto | Collapse Item |

### Collapse Exposes

| Nombre         | Descripción                  | Tipo                                                         |
| -------------- | ---------------------------- | ------------------------------------------------------------ |
| activeNames    | currently active panel names | ^[object]`ComputedRef<(string \| number)[]>`          |
| setActiveNames | set active panel names       | ^[Function]`(activeNames: (string \| number)[]) => void` |

## Collapse Item API

### Collapse Item Attributes

| Nombre        | Descripción                   | Type                     | Default    |
| ------------- | ----------------------------- | ------------------------ | ---------- |
| name          | identificador único del panel | ^[string] / ^[number]    | —          |
| title         | título del panel              | ^[string]                | ''         |
| icon ^(2.8.3) | icon of the collapse item     | ^[string] / ^[Component] | ArrowRight |
| disabled      | deshabilita el collapse ítem  | ^[boolean]               | false      |

### Collapse Item Slot

| Name          | Description                   | Type                             |
| ------------- | ----------------------------- | -------------------------------- |
| default       | contenido del Collapse Ítem   | —                                |
| title         | contenido del Collapse Ítem   | ^[object]`{ isActive: boolean }` |
| icon ^(2.8.3) | content of Collapse Item icon | ^[object]`{ isActive: boolean }` |

### Collapse Item Exposes

| Name     | Description                                 | Type                                                |
| -------- | ------------------------------------------- | --------------------------------------------------- |
| isActive | whether the current collapse item is active | ^[object]`ComputedRef<boolean \| undefined>` |
