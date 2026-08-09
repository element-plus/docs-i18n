---
title: Pagination
lang: es-ES
---

# Paginación

Si tiene que mostrar muchos datos en una página, utilice la paginación.

## Uso básico

:::demo Asigne en el atributo `layout` los diferentes elementos que quiere utilizar separados por coma. Pagination elements are: `prev` (a button navigating to the previous page), `next` (a button navigating to the next page), `pager` (page list), `jumper` (a jump-to input), `total` (total item count), `sizes` (a select to determine page size) and `->`(every element after this symbol will be pulled to the right).

pagination/basic-usage

:::

## Número de páginas

:::demo De forma predeterminada, Pagination colapsa los botones del paginador adicionales cuando tiene más de 7 páginas. Esto se puede configurar con el atributo `pager-count`.

pagination/number-of-pagers

:::

## Botones con color de fondo

:::demo Establecer el atributo `background` y los botones tendrán un color de fondo.

pagination/background-color

:::

## Paginación pequeña

Use paginación pequeña en caso de espacio limitado.

:::demo set size to change the `size`. Here is a demonstration of `small`

pagination/small-pagination

:::

## Oculte la paginación cuando solo hay una página

Cuando solo hay una página, oculte la paginación configurando el atributo `hide-on-single-page`.

:::demo

pagination/auto-hide-pagination

:::

## Más elementos

Añade más módulos basados en tu escenario.

:::demo Este ejemplo es un completo caso de uso. Utilice los eventos `size-change` y `current-change` para manejar el tamaño de página y el cambio de página. El atributo `page-sizes` acepta un arreglo de enteros, cada uno representa un diferente valor del atributo `sizes` que es un select, ejemplo: `[100, 200, 300, 400]` indicará que el select tendrá las opciones: 100, 200, 300 o 400 elementos por página.

pagination/more-elements

:::

## API

### Attributes

| Nombre                              | Descripción                                                                                                                   | Tipo                                                                                 | Por defecto                          |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ | ------------------------------------ |
| size ^(2.7.6)                       | pagination size                                                                                                               | ^[enum]`'large' \| 'default' \| 'small'`                                           | 'default'                            |
| background                          | si los botones tienen un color de fondo                                                                                       | ^[boolean]                                                                           | false                                |
| page-size / v-model:page-size       | contador de elementos de cada página                                                                                          | ^[number]                                                                            | —                                    |
| default-page-size                   | default initial value of page size, not setting is the same as setting 10                                                     | ^[number]                                                                            | —                                    |
| total                               | total de elementos                                                                                                            | ^[number]                                                                            | —                                    |
| page-count                          | total de páginas. Asigne `total` o `page-count` y las páginas serán mostradas; si necesita `page-sizes`, `total` es requerido | ^[number]                                                                            | —                                    |
| pager-count                         | número de paginadores. La paginación colapsa cuando el número total de páginas excede este valor                              | ^[number]`5 \| 7 \| 9 \| 11 \| 13 \| 15 \| 17 \| 19 \| 21`                   | 7                                    |
| current-page / v-model:current-page | número de página actual                                                                                                       | ^[number]                                                                            | —                                    |
| default-current-page                | default initial value of current-page, not setting is the same as setting 1                                                   | ^[number]                                                                            | —                                    |
| layout                              | disposición de la paginación, elementos separados con una coma                                                                | ^[string]`string (consists of sizes, prev, pager, next, jumper, ->, total, slot)` | prev, pager, next, jumper, ->, total |
| page-sizes                          | opciones de conteo de elementos por página                                                                                    | ^[array]`number[]`                                                                   | [10, 20, 30, 40, 50, 100]            |
| append-size-to ^(2.8.4)             | which element the size dropdown appends to                                                                                    | ^[string]                                                                            | —                                    |
| popper-class                        | nombre de clase personalizado para el tamaño de página del select desplegable                                                 | ^[string]                                                                            | ''                                   |
| popper-style ^(2.11.5)              | custom style for the page size Select's dropdown                                                                              | ^[string] / ^[object]                                                                | —                                    |
| prev-text                           | texto para el botón anterior                                                                                                  | ^[string]                                                                            | ''                                   |
| prev-icon                           | icon for the prev button, has a lower priority than `prev-text`                                                               | ^[string] / ^[Component]                                                             | ArrowLeft                            |
| next-text                           | texto para el siguiente botón                                                                                                 | ^[string]                                                                            | ''                                   |
| next-icon                           | icon for the next button, has a lower priority than `next-text`                                                               | ^[string] / ^[Component]                                                             | ArrowRight                           |
| disabled                            | si la paginación está deshabilitada                                                                                           | ^[boolean]                                                                           | false                                |
| teleported ^(2.3.13)                | whether Pagination select dropdown is teleported to the body                                                                  | ^[boolean]                                                                           | true                                 |
| hide-on-single-page                 | whether to hide when there's only one page                                                                                    | ^[boolean]                                                                           | false                                |
| small ^(deprecated)                 | si desea utilizar una paginación pequeña                                                                                      | ^[boolean]                                                                           | false                                |

:::warning

Detectaremos algunos usos obsoletos, si la paginación no apareció o funcionó como se esperaba, por favor revise las siguientes reglas:

- Tiene que definir uno de `total` y `page-count`, de lo contrario no podemos determinar el número total de páginas. Si ambos están definidos, `page-count` se toma de forma prioritaria.
- Si `current-page` está definida, tiene que escuchar los cambios de `current-page`, por definirlo también `@update:current-page`, de lo contrario la paginación no funcionara.
- Si `page-size` está definido mientras se muestra el selector de tamaño de página (`sizes` incluido en `layout`), tienes que escuchar también el cambio `page-size` definido por `@update:page-size`, de lo contrario el cambio del tamaño de la página no funcionara.

:::

### Events

| Nombre          | Descripción                                                              | Tipo                                                            |
| --------------- | ------------------------------------------------------------------------ | --------------------------------------------------------------- |
| size-change     | se dispara cuando `page-size` cambia                                     | ^[Function]`(value: number) => void`                         |
| current-change  | se dispara cuando `current-page` cambia                                  | ^[Function]`(value: number) => void`                         |
| change ^(2.4.4) | triggers when `current-page` or `page-size` changes                      | ^[Function]`(currentPage: number, pageSize: number) => void` |
| prev-click      | se dispara cuando el botón prev recibe el clic y la página actual cambia | ^[Function]`(value: number) => void`                         |
| next-click      | se dispara cuando el botón next recibe el clic y la página actual cambia | ^[Function]`(value: number) => void`                         |

:::warning

Los eventos anteriores no son recomendados (pero siguen siendo soportados por una razón de compatibilidad), mejor opción es usar el enlace de datos bidireccionales por `v-model`.

:::

### Slots

| Nombre  | Descripción                                                                          |
| ------- | ------------------------------------------------------------------------------------ |
| default | contenido personalizado. Para utilizar esto necesitas declarar `slot` en el `layout` |
