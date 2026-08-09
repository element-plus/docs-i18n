---
title: Layout
lang: es-ES
---

# Layout

Crea diseños rápida y fácilmente con las 24 columnas básicas.

:::tip

El componente utiliza el diseño flex por defecto, no es necesario establecer `type="flex"` manualmente.

Tenga en cuenta que el contenedor padre debe evitar el uso de estilos relacionados con `inline`, lo cual hará que el componente no llene su ancho.

The basic unit of a column is 1, with a maximum of 24 and a minimum of 0.

:::

## Layout básico

Crea un diseño básico de cuadrícula con columnas.

:::demo Con `row` y `col`, puede fácilmente manipular el layout usando el atributo `span`.

layout/basic-layout

:::

## Espaciado de columnas

El espaciado de columnas está soportado.

:::demo Row provee el atributo `gutter` para especificar el espacio entre columnas y su valor por defecto es 0.

layout/column-spacing

:::

## Layout híbrido

Forme un diseño híbrido más complejo combinando las columnas básicas 1/24.

:::demo

layout/hybrid-layout

:::

## Desplazamiento de columnas

Puede especificar el desplazamiento de las columnas.

:::demo Puede especificar el número del desplazamiento de la columna estableciendo el valor en el atributo `offset` de Col.

layout/column-offset

:::

## Alineamiento

Por defecto se usa el diseño flex para hacer una alineación flexible de las columnas.

:::demo Puedes definir el diseño de elementos secundarios configurando el atributo `justify` con start, center, end, space-between (espacio entremedio), space-around (espacio alrededor) o space-evenly (espacio uniforme).

layout/alignment

:::

## Diseño responsive

Tomando el ejemplo de Bootstrap responsive design, existen 5 breakpoints: xs, sm, md, lg y xl.

:::demo

layout/responsive-layout

:::

## Clases útiles para ocultar elementos

Adicionalmente, Element Plus provee una serie de clases para ocultar elementos dadas ciertas condiciones. Estas clases pueden ser añadidas a cualquier elemento DOM o componentes personalizados. Necesita importar el siguiente archivo CSS para usar estas clases:

```js
import 'element-plus/theme-chalk/display.css'
```

Las clases son:

- `hidden-xs-only` - oculto en viewports extra pequeños solamente
- `hidden-sm-only` - oculto en viewports pequeños solamente
- `hidden-sm-and-down` - oculto en viewports pequeños y menores
- `hidden-sm-and-up` - oculto en viewports pequeños y superiores
- `hidden-md-only` - oculto en viewports medios solamente
- `hidden-md-and-down` - oculto en viewports medios y menores
- `hidden-md-and-up` - oculto en viewports medios y mayores
- `hidden-lg-only` - ocultos en viewports grandes solamente
- `hidden-lg-and-down` - ocultos en viewports grandes y menores
- `hidden-lg-and-up` - ocultos en viewports grandes y superiores
- `hidden-xl-only` - oculto en viewports extra grandes solamente

## API de fila

### Row Attributes

| Nombre  | Descripción                           | Tipo                                                                                              | Por defecto |
| ------- | ------------------------------------- | ------------------------------------------------------------------------------------------------- | ----------- |
| gutter  | espaciado en cuadrícula               | ^[number]                                                                                         | 0           |
| justify | alineación horizontal del layout flex | ^[enum]`'start' \| 'end' \| 'center' \| 'space-around' \| 'space-between' \| 'space-evenly'` | start       |
| align   | alineación vertical del layout flex   | ^[enum]`'top' \| 'middle' \| 'bottom'`                                                          | —           |
| tag     | etiqueta de elemento personalizada    | ^[string]                                                                                         | div         |

### Row Slots

| Nombre  | Descripción                          | Subtags |
| ------- | ------------------------------------ | ------- |
| default | personaliza el contenido por defecto | Col     |

## API de columna

### Col Attributes

| Nombre | Descripción                                                            | Tipo                                                                                  | Por defecto |
| ------ | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ----------- |
| span   | número de columnas que abarca la cuadrícula                            | ^[number]                                                                             | 24          |
| offset | número de espacio en el lado izquierdo de la cuadrícula                | ^[number]                                                                             | 0           |
| push   | número de columnas que la cuadrícula se mueve a la derecha             | ^[number]                                                                             | 0           |
| pull   | número de columnas que se mueve a la izquierda                         | ^[number]                                                                             | 0           |
| xs     | `<768px` Columnas responsive u objeto con propiedades de la columna | ^[number] / ^[object]`{span?: number, offset?: number, pull?: number, push?: number}` | —           |
| sm     | `≥768px` Columnas responsive u objeto con propiedades de la columna    | ^[number] / ^[object]`{span?: number, offset?: number, pull?: number, push?: number}` | —           |
| md     | `≥992px` Columnas responsive u objeto con propiedades de la columna    | ^[number] / ^[object]`{span?: number, offset?: number, pull?: number, push?: number}` | —           |
| lg     | `≥1200px` Columnas responsive u objeto con propiedades de la columna   | ^[number] / ^[object]`{span?: number, offset?: number, pull?: number, push?: number}` | —           |
| xl     | `≥1920px` Columnas responsive u objeto con propiedades de la columna   | ^[number] / ^[object]`{span?: number, offset?: number, pull?: number, push?: number}` | —           |
| tag    | etiqueta de elemento personalizada                                     | ^[string]                                                                             | div         |

### Col Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |

<style lang="scss">
@use '../../examples/layout/index.scss';
</style>
