---
title: Card
lang: es-ES
---

# Card

Muestra información dentro de un contenedor `card`.

## Uso básico

`Card` incluye título, contenido y operaciones.

:::demo Card is made up of `header`, `body` and `footer`. `header` and `footer` are optional, and its content distribution depends on a named slot.

card/basic

:::

## Tarjeta simple

La parte de la cabecera puede omitirse.

:::demo

card/simple

:::

## Con imágenes

Muestre un contenido más rico añadiendo algunas configuraciones.

:::demo The `body-style` attribute defines CSS style of custom `body`.

card/with-images

:::

## Sombra

Puede definir cuándo mostrar las sombras

:::demo El atributo `shadow` determina cuándo se muestran las sombras de la tarjeta. Puede ser `always`, `hover` o `never`.

card/shadow

:::

## API

### Atributos

| Nombre                | Descripción                                                    | Tipo                                | Por defecto |
| --------------------- | -------------------------------------------------------------- | ----------------------------------- | ----------- |
| header                | título del card. También acepta DOM pasado por `slot#header`   | ^[string]                           | —           |
| footer ^(2.4.3)       | footer of the card. Also accepts a DOM passed by `slot#footer` | ^[string]                           | —           |
| body-style            | CSS style of card body                                         | ^[object]`CSSProperties`            | —           |
| header-class ^(2.9.8) | custom class name of card header                               | ^[string]                           | —           |
| body-class ^(2.3.10)  | custom class name of card body                                 | ^[string]                           | —           |
| footer-class ^(2.9.8) | custom class name of card footer                               | ^[string]                           | —           |
| shadow                | when to show card shadows                                      | ^[enum]`always \| never \| hover` | always      |

### Slots

| Nombre  | Descripción                            |
| ------- | -------------------------------------- |
| default | personaliza el contenido por defecto   |
| header  | contenido del encabezado de la tarjeta |
| footer  | content of the Card footer             |
