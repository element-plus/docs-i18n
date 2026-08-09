---
title: Descriptions
lang: es-ES
---

# Descripciones

Muestra múltiples campos con formato de lista.

## Uso básico

:::demo

descriptions/basic-usage

:::

## Tamaños

:::demo

descriptions/sizes

:::

## Lista vertical

:::demo

descriptions/vertical-list

:::

## Rowspan ^(2.8.1)

:::demo

descriptions/rowspan

:::

## Estilos personalizados

:::demo

descriptions/customized-style

:::

## Descriptions API

### Descriptions Attributes

| Nombre               | Descripción                                               | Tipo                                              | Default    |
| -------------------- | --------------------------------------------------------- | ------------------------------------------------- | ---------- |
| border               | con o sin borde                                           | ^[boolean]                                        | false      |
| column               | números de `ítems de la descripción` en una línea         | ^[number]                                         | 3          |
| direction            | dirección de la lista                                     | ^[enum]`'vertical' \| 'horizontal'`              | horizontal |
| size                 | tamaño de la lista                                        | ^[enum]`'' \| 'large' \| 'default' \| 'small'` | —          |
| title                | texto del título, mostrado en la parte superior izquierda | ^[string]                                         | ''         |
| extra                | texto extra, mostrado en la parte superior derecha        | ^[string]                                         | ''         |
| label-width ^(2.8.8) | label width of every column                               | ^[string] / ^[number]                             | —          |

### Descriptions Slots

| Nombre  | Descripción                                                     | Subtags           |
| ------- | --------------------------------------------------------------- | ----------------- |
| default | personaliza el contenido por defecto                            | Descriptions Item |
| title   | título personalizado, mostrado en la parte superior izquierda   | —                 |
| extra   | área extra personalizada, mostrado en la parte superior derecha | —                 |

## DescriptionsItem API

### DescriptionsItem Attributes

| Nombre               | Descripción                                                                                                                                                                                                                     | Tipo                                     | Default |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------- | ------- |
| label                | texto de la etiqueta                                                                                                                                                                                                            | ^[string]                                | ''      |
| span                 | colspan de la columna                                                                                                                                                                                                           | ^[number]                                | 1       |
| rowspan ^(2.8.1)     | the number of rows a cell should span                                                                                                                                                                                           | ^[number]                                | 1       |
| width                | el ancho de la columna, el ancho de la misma columna en diferentes filas es establecido por el valor máximo (Si no hay `border`, width incluye etiqueta y contenido)                                                            | ^[string] / ^[number]                    | ''      |
| min-width            | el ancho mínimo de la columna, las columnas con `width` tienen un ancho fijo, mientras que las columnas con `min-width` tiene un ancho que se distribuye en proporción (Si no hay `border`, width incluye etiqueta y contenido) | ^[string] / ^[number]                    | ''      |
| label-width ^(2.8.8) | column label width, if not set, it will be the same as the width of the column. Higher priority than the `label-width` of `Descriptions`                                                                                        | ^[string] / ^[number]                    | —       |
| align                | alineación del contenido de la columna (Si no hay `border`, afecta tanto a la etiqueta como al contenido)                                                                                                                       | ^[enum]`'left' \| 'center' \| 'right'` | left    |
| label-align          | alineamiento de la etiqueta de la columna, si se omite, el valor del atributo anterior `align` se aplicará (Si no hay `border`, por favor use el atributo `align`)                                                              | ^[enum]`'left' \| 'center' \| 'right'` | —       |
| class-name           | nombre de clase personalizada del contenido de la columna                                                                                                                                                                       | ^[string]                                | ''      |
| label-class-name     | nombre de clase personalizada para la etiqueta de la columna                                                                                                                                                                    | ^[string]                                | ''      |

### DescriptionsItem Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |
| label   | personaliza la etiqueta              |
