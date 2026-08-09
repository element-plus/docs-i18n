---
title: Badge
lang: es-ES
---

# Badge

Un número o una marca de estado en botones e iconos.

## Uso básico

Muestra la cantidad de mensajes nuevos.

:::demo La cantidad se define con un valor que acepta Número o Cadena.

badge/basic

:::

## Valor máximo

Puede personalizar el valor máximo.

:::demo El valor máximo se define por la propiedad max que es un número. Tenga en cuenta que sólo funciona cuando el valor es también un número.

badge/max

:::

## Personalizaciones

Displays text content other than numbers. Or you can use the `content` slot to customize content.

:::demo Cuando el valor es una cadena, puede mostrar texto personalizado. Or use the `content` slot.

badge/customize

:::

## Punto rojo

Usa un punto rojo para marcar contenido que necesita ser notado.

:::demo Use el atributo `is-dot`. Es booleano.

badge/dot

:::

## Offset ^(2.7.0)

:::demo Set offset of the badge dot, the format is [left, top], which represents the offset of the status dot from the left and top of the default position.

badge/offset

:::

## API

### Atributos

| Nombre               | Descripción                                                                              | Tipo                                                                   | Por defecto |
| -------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- | ----------- |
| value                | valor a mostrar.                                                                         | ^[string] / ^[number]                                                  | ''          |
| max                  | valor máximo, muestra `{max}+` cuando se excede. Sólo funciona si el valor es un número. | ^[number]                                                              | 99          |
| is-dot               | si se debe mostrar un pequeño punto rojo.                                                | ^[boolean]                                                             | false       |
| hidden               | oculta el Badge.                                                                         | ^[boolean]                                                             | false       |
| type                 | tipo de badge.                                                                           | ^[enum]`'primary' \| 'success' \| 'warning' \| 'danger' \| 'info'` | danger      |
| show-zero ^(2.6.0)   | Whether to show badge when value is zero.                                                | ^[boolean]                                                             | true        |
| color ^(2.6.3)       | background color of the dot                                                              | ^[string]                                                              |             |
| offset ^(2.7.0)      | offset of badge                                                                          | ^[array]`[number, number]`                                             | [0, 0]      |
| badge-style ^(2.7.1) | custom style of badge                                                                    | ^[object]`CSSProperties`                                               | —           |
| badge-class ^(2.7.1) | custom class of badge                                                                    | ^[string]                                                              | —           |

### Slots

| Nombre           | Descripción                          | Type                         |
| ---------------- | ------------------------------------ | ---------------------------- |
| default          | personaliza el contenido por defecto | -                            |
| content ^(2.9.1) | customize badge content              | ^[object]`{ value: string }` |
