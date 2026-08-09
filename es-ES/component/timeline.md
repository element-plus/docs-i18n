---
title: Timeline
lang: es-ES
---

# Timeline

Línea de tiempo visual.

## Uso básico

El Timeline puede ser dividido en múltiples actividades. Las marcas de tiempo son características importantes que los distinguen de otros componentes. Observe la diferencia con Steps.

:::demo

timeline/basic

:::

## Mode ^(2.13.1)

Use `mode` to control the relative position of timeline and content.

:::tip

After ^(2.13.1), `el-timeline` explicitly sets padding styles. If you have overridden padding styles of `ul` tag in your project, please check to ensure the layout is correct.

:::

:::demo

timeline/mode

:::

## Nodo personalizado

El tamaño, el color y los iconos se pueden personalizar en el nodo.

:::demo

timeline/custom-node

:::

## Marcas de tiempo personalizadas

Las marcas de tiempo ( timestamp )  puede colocarse encima del contenido cuando éste es demasiado alto.

:::demo

timeline/custom-timestamp

:::

## Centrado verticalmente

Timeline-Item se centra verticalmente.

:::demo

timeline/center

:::

## Reverse ^(2.11.9)

Use the reverse property to control the order of the nodes.

:::demo

timeline/reverse

:::

## Timeline API

### Timeline Attributes

| Nombre            | Descripción                               | Tipo                                                               | Por defecto |
| ----------------- | ----------------------------------------- | ------------------------------------------------------------------ | ----------- |
| reverse ^(2.11.9) | whether reverse order                     | ^[boolean]                                                         | false       |
| mode ^(2.13.1)    | relative position of timeline and content | ^[enum]`'start' \| 'alternate' \| 'alternate-reverse' \| 'end'` | start       |

### Timeline Slots

| Nombre  | Descripción                                                   | Subtags       |
| ------- | ------------------------------------------------------------- | ------------- |
| default | personalizar el contenido por defecto para la línea de tiempo | Timeline-Item |

## Timeline-Item API

### Timeline-Item Attributes

| Nombre         | Descripción                                   | Tipo                                                                   | Por defecto |
| -------------- | --------------------------------------------- | ---------------------------------------------------------------------- | ----------- |
| timestamp      | Contenido personalizado del ítem del timeline | ^[string]                                                              | ''          |
| hide-timestamp | Definición personalizada del nodo             | ^[boolean]                                                             | false       |
| center         | si se centra verticalmente                    | ^[boolean]                                                             | false       |
| placement      | la posición de timestamp                      | ^[enum]`'top' \| 'bottom'`                                            | bottom      |
| type           | tipo de nodo                                  | ^[enum]`'primary' \| 'success' \| 'warning' \| 'danger' \| 'info'` | ''          |
| color          | color de fondo del nodo                       | ^[string]                                                              | ''          |
| size           | tamaño del nodo                               | ^[enum]`'normal' \| 'large'`                                          | normal      |
| icon           | componente de icono                           | ^[string] / ^[Component]                                               | —           |
| hollow         | icono es hueco                                | ^[boolean]                                                             | false       |

### Timeline-Item Slots

| Nombre  | Descrición                                                 |
| ------- | ---------------------------------------------------------- |
| default | personaliza el contenido predeterminado para timeline-item |
| dot     | personaliza nodo definido para el timeline-item            |
