---
title: Affix
lang: es-ES
---

# Affix

Fija el elemento a una posición límite si el scrolling del usuario va a sacarlo de la visualización.

## Uso básico

Por defecto, el componente se fijará en la parte superior de la página.

:::demo Puede establecer el atributo `offset` para cambiar la parte superior del desplazamiento, el valor por defecto es 0.

affix/basic

:::

## Contenedor

Mediante el atributo `target` el elemento se mostrará solo dentro de los límites de su contenedor. Por lo tanto será arrastrado por su contendor si dicho contenedor queda fuera de la pantalla debido al scrolling del usuario.

:::demo Tenga en cuenta que el contenedor evita tener scrollbar.

affix/target

:::

## Posición fija

El componente affix proporciona dos posiciones fijas: `top` y `bottom`.

Puede establecer el atributo `position` para cambiar la posición arriba "top" o abajo "bottom". El valor predeterminado es `top`.

affix/posición

:::

## API

### Attributes

| Nombre               | Descripción                                                                                    | Tipo                            | Por defecto |
| -------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------- | ----------- |
| offset               | offset distance                                                                                | ^[number]                       | 0           |
| position             | position of affix                                                                              | ^[enum]`'top' \| 'bottom'`     | top         |
| target               | target container (CSS selector)                                                                | ^[string]                       | —           |
| z-index              | `z-index` de affix                                                                             | ^[number]                       | 100         |
| teleported ^(2.13.0) | whether affix element is teleported, if `true` it will be teleported to where `append-to` sets | ^[boolean]                      | false       |
| append-to ^(2.13.0)  | which element the affix element appends to                                                     | ^[CSSSelector] / ^[HTMLElement] | body        |

### Events

| Nombre | Descripción                       | Tipo                                                                   |
| ------ | --------------------------------- | ---------------------------------------------------------------------- |
| change | triggers when fixed state changed | ^[Function]`(fixed: boolean) => void`                               |
| scroll | triggers when scrolling           | ^[Function]`(value: { scrollTop: number, fixed: boolean }) => void` |

### Slots

| Nombre  | Descripción               |
| ------- | ------------------------- |
| default | customize default content |

### Exposes

| Name       | Descripción                       | Tipo                       |
| ---------- | --------------------------------- | -------------------------- |
| update     | actualizar el estado manualmente  | ^[Function]`() => void` |
| updateRoot | actualiza información de rootRect | ^[Function]`() => void` |
