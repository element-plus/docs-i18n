---
title: Text
lang: es-ES
---

# Texto

Utilizado para texto.

## Básico

:::demo Utilice el atributo `type` para definir el tipo de texto.

text/basic

:::

## Tamaños

:::demo Use el atributo `size` para establecer tamaños adicionales con los siguientes valores `large`, `default` o `small`.

text/sizes

:::

## Elipsis

:::demo Pass the `truncated` prop to render an ellipsis when the text exceeds the width of the viewport or max-width set. `line-clamp` prop to render multiline ellipsis.

text/truncated

:::

## Sobrescribir

:::demo Use el atributo `tag` para sobreescribir el elemento HTML contenedor

text/override

:::

## Mixto

:::demo Combinando otros componentes con Text

text/mixed

:::

## API

### Atributos

| Nombre              | Descripción                        | Tipo                                                                   | Por defecto |
| ------------------- | ---------------------------------- | ---------------------------------------------------------------------- | ----------- |
| type                | tipo de texto                      | ^[enum]`'primary' \| 'success' \| 'warning' \| 'danger' \| 'info'` | —           |
| size                | tamaño del texto                   | ^[enum]`'large' \| 'default' \| 'small'`                             | default     |
| truncated           | mostrar puntos suspensivos         | ^[boolean]                                                             | false       |
| line-clamp ^(2.4.0) | maximum lines                      | ^[string] / ^[number]                                                  | —           |
| tag                 | etiqueta de elemento personalizada | ^[string]                                                              | span        |

### Slots

| Nombre  | Descripción           |
| ------- | --------------------- |
| default | contenido por defecto |
