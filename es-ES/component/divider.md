---
title: Divider
lang: es-ES
---

# Divider

La línea divisoria que separa el contenido.

## Uso básico

Divide el texto de los diferentes párrafos.

:::demo

divider/basic-usage

:::

## Contenido personalizado

Puede personalizar el contenido en la línea divisoria.

:::demo

divider/custom-content

:::

## línea discontinua

Puede establecer el estilo del separador.

:::demo

divider/line-dashed

:::

## División vertical

:::demo

divider/vertical-divider

:::

## API

### Atributos

| Nombre           | Descripción                                                | Tipo                                                                                                                                            | Por defecto |
| ---------------- | ---------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| direction        | Indica la dirección del separador                          | ^[enum]`'horizontal' \| 'vertical'`                                                                                                            | horizontal  |
| border-style     | Establecer el estilo del separador                         | ^[enum]`'none' \| 'solid' \| 'hidden' \| 'dashed' \| ...` [css/border-style](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border-style) | solid       |
| content-position | The position of the customized content on the divider line | ^[enum]`'left' \| 'right' \| 'center'`                                                                                                        | center      |

### Slots

| Nombre  | Descripción                            |
| ------- | -------------------------------------- |
| default | Customized content on the divider line |
