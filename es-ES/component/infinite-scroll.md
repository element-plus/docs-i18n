---
title: Infinite
lang: es-ES
---

:::warning Deprecated directive

We no longer maintain this directive. It will be **removed** in ^(3.0.0), please use the [el-scrollbar infinite scroll](./scrollbar#infinite-scroll) instead.

:::

# Infinite Scroll

Cargar más datos al llegar a la parte inferior de la página

## Uso básico

Añada `v-infinite-scroll` a la lista para ejecutar automáticamente el método de carga cuando se desplace hacia abajo.

:::demo

infinite-scroll/basic

:::

## Desactivar la carga

:::demo

infinite-scroll/disable-loading

:::

## Directivas

| Nombre                    | Descripción                                                                                                           | Tipo        | Por defecto |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------- | ----------- | ----------- |
| v-infinite-scroll         | Carga más datos al llegar a la parte inferior de la página                                                            | ^[Function] | —           |
| infinite-scroll-disabled  | si está deshabilitado                                                                                                 | ^[boolean]  | false       |
| infinite-scroll-delay     | retardo del acelerador (ms)                                                                                           | ^[number]   | 200         |
| infinite-scroll-distance  | distancia desencadenante (px)                                                                                         | ^[number]   | 0           |
| infinite-scroll-immediate | Si ejecutar el método de carga inmediatamente, en caso de que el contenido no se pueda rellenar en el estado inicial. | ^[boolean]  | true        |
