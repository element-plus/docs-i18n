---
title: Carousel
lang: es-ES
---

# Carousel

Presenta una serie de imágenes o textos en un espacio limitado

## Uso básico

:::demo Combine `el-carousel` con `el-carousel-item`, para conseguir el carrusel. El contenido de cada diapositiva es completamente personalizable, y solo tiene que colocarla dentro de la etiqueta `el-carousel-item`. Por defecto, el carrusel cambia cuando el ratón pasa por encima de un indicador. Fije `trigger` para `click`, si lo que se desea es que el carrusel cambie solo cuando se haga clic en un indicador.

carousel/basic

:::

## Motion blur ^(2.6.0)

Add motion blur to infuse dynamism and smoothness into the carousel.

:::demo Enabling motion blur enhances the dynamism and smoothness of the carousel. By default, the `motion-blur` parameter is set to `false`, activating this feature and providing a visually engaging experience.

carousel/motion-blur

:::

## Indicadores

Los indicadores pueden mostrarse fuera del carrusel

:::demo El atributo `indicator-position` determina dónde están ubicados los indicadores. Por defecto están dentro del carrusel, y el ajuste de `indicator-position` a `outside` los mueve hacia fuera; en cambio `indicator-position` a `none` los oculta.

carousel/indicator

:::

## Flechas

Puede definir cuando se visualizan las flechas

:::demo El atributo `arrow` determina cuándo se visualizan las flechas. Por defecto aparecen cuando el ratón pasa sobre el carrusel. Ajuste `arrow` a `always` o `never` para mostrar u ocultar las flechas permanentemente.

carousel/arrows

:::

## Altura automática

Cuando el `height` de `carousel` se establece en `auto`, la altura del `carousel` se establecerá automáticamente según la altura de cada elemento del `carousel`

:::demo

carousel/auto-height

:::

## Modo Card

Cuando una página es suficientemente ancha, pero tiene una altura limitada, puede activar el modo card para carrusel

:::demo Ajuste `type` a `card` para activar el modo card. Aparte de la apariencia, la mayor diferencia entre el modo card y el modo común es que al hacer clic en las diapositivas de ambos lados, el carrusel cambia directamente en modo card.

carousel/card

:::

## Vertical

Por defecto, `direction` es `horizontal`. El carrusel puede ser mostrado de forma vertical cambiando `direction` a `vertical`.

:::demo

carousel/vertical

:::

## Carousel API

### Carousel Attributes

| Nombre               | Descripción                                                            | Tipo                                      | Default    |
| -------------------- | ---------------------------------------------------------------------- | ----------------------------------------- | ---------- |
| height               | altura del carrusel                                                    | ^[string]                                 | ''         |
| initial-index        | índice del slider inicial activo (empieza desde 0)                     | ^[number]                                 | 0          |
| trigger              | cómo se activan los indicadores                                        | ^[enum]`'hover' \| 'click'`              | hover      |
| autoplay             | si los sliders hacen el bucle de forma automática                      | ^[boolean]                                | true       |
| interval             | intervalo del bucle automático, en milisegundos                        | ^[number]                                 | 3000       |
| indicator-position   | posición de los indicadores                                            | ^[enum]`'' \| 'none' \| 'outside'`      | ''         |
| arrow                | cuando se muestran las flechas                                         | ^[enum]`'always' \| 'hover' \| 'never'` | hover      |
| type                 | tipo de carrusel                                                       | ^[enum]`'' \| 'card'`                    | ''         |
| card-scale ^(2.7.8)  | when type is card, scaled size of secondary cards                      | ^[number]                                 | 0.83       |
| loop                 | si se muestra en bucle                                                 | ^[boolean]                                | true       |
| direction            | dirección en la que se muestra el contenido                            | ^[enum]`'horizontal' \| 'vertical'`      | horizontal |
| pause-on-hover       | si se pausa el bucle automático cuando el ratón pase sobre el carrusel | ^[boolean]                                | true       |
| motion-blur ^(2.6.0) | infuse dynamism and smoothness into the carousel                       | ^[boolean]                                | false      |

### Carousel Events

| Nombre | Descripción                                                                                                                                              | Tipo                                                    |
| ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| change | triggers when the active slide switches, it has two parameters, the one is the index of the new active slide, and other is index of the old active slide | ^[Function]`(current: number, prev: number) => void` |

### Carousel Slots

| Nombre  | Descripción                          | Subtags       |
| ------- | ------------------------------------ | ------------- |
| default | personaliza el contenido por defecto | Carousel-Item |

### Carousel Exposes

| Método               | Descripción                                                                                                                     | Type                                               |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------- |
| activeIndex ^(2.7.8) | active slide index                                                                                                              | ^[number]                                          |
| setActiveItem        | manually switch slide, index of the slide to be switched to, starting from 0; or the `name` of corresponding `el-carousel-item` | ^[Function]`(index: string \| number) => void` |
| prev                 | cambia al slider anterior                                                                                                       | ^[Function]`() => void`                         |
| next                 | cambia al slider siguiente                                                                                                      | ^[Function]`() => void`                         |

## Carousel-Item API

### Carousel-Item Attributes

| Nombre | Descripción                                          | Type                  | Por defecto |
| ------ | ---------------------------------------------------- | --------------------- | ----------- |
| name   | nombre del ítem, puede ser usado en `setActiveItem`  | ^[string]             | ''          |
| label  | contenido de texto para el indicador correspondiente | ^[string] / ^[number] | ''          |

### Carousel-Item Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |
