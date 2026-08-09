---
title: Space
lang: es-ES
---

# Space

Even though we have [Divider](./divider.md), but sometimes we need more than one [Divider](./divider.md) to split the elements apart, so we stack each elements upon [Divider](./divider.md), but doing so not only makes our code ugly but also makes it difficult to maintain. **Space** es el tipo de componente que nos proporciona productividad y elegancia.

## Uso básico

En este caso de uso básico usamos este componente para proporcionar espacio unificado entre los otros componentes

:::demo usando space para proporcionar espacio

space/basic

:::

## Distribución vertical

Use el atributo `direction` para controlar la dirección de diseño, usamos `flex-direction` para implementar esto.

:::demo También proporcionamos un diseño vertical.

space/vertical-layout

:::

## Controla el tamaño del espacio

Controla el tamaño del espacio a través de la API con el atributo `size`.

You can set the size with built-in sizes `small`, `default`, `large`, these size corresponds to `8px`, `12px`, `16px`. El tamaño predeterminado es `small`, A.K.A. `8px`

También puede usar un tamaño personalizado para sobreescribirlo. Consulte la siguiente parte.

:::demo

space/control-size

:::

## Tamaño personalizado

A veces los tamaños incorporados pueden no satisfacer las necesidades de la empresa, podemos utilizar el tamaño personalizado (tipo número) para controlar el espacio entre los elementos.

:::demo

space/customized-size

:::

:::tip

No utilice `ElSpace` con componentes que dependen del ancho de los ancestros (altura), p. ej. `ElSlider`, en este caso cuando arrastra el botón disparador, la barra crecerá lo que causa un error de colocación entre el cursor y el botón disparador.

:::

## Auto wrapping

En el modo **horizontal**, use `wrap` (**bool**) para controlar el comportamiento de wrapping automático.

:::demo Usando `wrap` para controlar el wrap de línea

space/auto-wrapping

:::

## Espaciador

A veces queremos algo más que espacio en blanco, así que tenemos (espaciador) para ayudarnos.

## Espacio de tipo literal

:::demo

space/literal-type-spacer

:::

## El espaciador también puede ser VNode

:::demo

space/vnode-type-spacer

:::

## Alineamiento

Configurando este atributo puede ajustar la alineación de nodos secundarios, el valor deseable puede encontrarse en [align-items](https://developer.mozilla.org/es/docs/Web/CSS/align-items).

:::demo Usando `alignment`

space/alignment

:::

## Rellenar el contenedor

A través del parámetro `fill` **(tipo booleano)**, puede controlar si el nodo hijo rellenará automáticamente el contenedor.

En el siguiente ejemplo, cuando se establece `fill`, el ancho del nodo hijo se adaptará automáticamente al ancho del contenedor.

:::demo Usar fill para rellenar automáticamente el contenedor con nodos hijos

space/fill

:::

También puede utilizar el parámetro `fillRatio` para personalizar el ratio de relleno. El valor predeterminado es `100`, lo que representa el relleno basado en el ancho del contenedor padre en `100%`.

Cabe señalar que la expresión del diseño horizontal y el diseño vertical es ligeramente diferente, el efecto específico se puede ver en el ejemplo siguiente.

:::demo Usar fillRatio para personalizar la relación de relleno

space/fill-ratio

:::

## API

### Atributos

| Nombre     | Descripción                         | Tipo                                                                                                                             | Por defecto |
| ---------- | ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| alignment  | Controla la alineación de elementos | ^[enum]`'center' \| 'normal' \| 'stretch' \| ...` [align-items](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items) | center      |
| class      | className                           | ^[string] / ^[object] / ^[array]                                                                                                 | —           |
| direction  | Dirección de emplazamiento          | ^[enum]`'vertical' \| 'horizontal'`                                                                                             | horizontal  |
| prefix-cls | Prefijo para espacio-elementos      | ^[string]                                                                                                                        | —           |
| style      | Reglas de estilo extra              | ^[string] / ^[object]`CSSProperties \| CSSProperties[] \| string[]`                                                            | —           |
| spacer     | Espaciador                          | ^[string] / ^[number] / ^[VNode]                                                                                                 | —           |
| size       | Tamaño del espacio                  | ^[enum]`'default' \| 'small' \| 'large'` / ^[number] / ^[array]`[number, number]`                                              | small       |
| wrap       | Auto wrapping                       | ^[boolean]                                                                                                                       | false       |
| fill       | Si rellenar el contenedor           | ^[boolean]                                                                                                                       | false       |
| fill-ratio | Ratio de relleno                    | ^[number]                                                                                                                        | 100         |

### Slots

| Nombre  | Descripción                |
| ------- | -------------------------- |
| default | Elementos a ser espaciados |
