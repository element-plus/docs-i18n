---
title: Tag
lang: es-ES
---

# Tag

Se utiliza para marcar y seleccionar.

## Uso básico

:::demo Utilice el atributo `type` para definir el tipo de etiqueta. Además, el atributo `color` se puede utilizar para establecer el color de fondo de la etiqueta.

tag/basic

:::

## Etiqueta removible

:::demo el atributo `closable` puede usarse para definir una etiqueta removible. Acepta un `Boolean`. De forma predeterminada, la eliminación de la etiqueta tiene una animación que se desvanece. Si no quiere usarlo, puede configurar el atributo `disable-transitions` , que acepta `Boolean`, como `true`. Se dispara el evento `close` cuando la etiqueta es removida.

tag/removable

:::

## Editar dinámicamente

Puede utilizar el evento `close` para añadir y eliminar etiquetas dinámicamente.

:::demo

tag/editable

:::

## Tamaños

Además del tamaño predeterminado, el componente Tag proporciona tres tamaños adicionales para que pueda elegir entre diferentes escenarios.

:::demo Use el atributo `size` para setear tamaños adicionales con `large`, `default` o `small`.

tag/sizes

:::

## Tema

Tag proporciona tres temas diferentes: `dark``light` y `plain`

:::demo Use `effect` para cambiar el tema, por defecto es `light`

tag/theme

:::

## Rounded

La etiqueta también puede ser redondeada como el botón.

:::demo

tag/rounded

:::

## Checkable Tag

Sometimes because of the business needs, we might need checkbox like tag, but **button like checkbox** cannot meet our needs, here comes `check-tag`. You can use `type` prop in ^(2.5.4).

:::demo uso básico de check-tag, la API es bastante simple.

tag/checkable

:::

## APi de las etiquetas

### Tag Attributes

| Nombre              | Descripción                         | Tipo                                                                   | Por defecto |
| ------------------- | ----------------------------------- | ---------------------------------------------------------------------- | ----------- |
| type                | tipo de etiqueta                    | ^[enum]`'primary' \| 'success' \| 'info' \| 'warning' \| 'danger'` | primary     |
| closable            | si el Tag puede ser removido        | ^[boolean]                                                             | false       |
| disable-transitions | si se deshabilitan las animaciones  | ^[boolean]                                                             | false       |
| hit                 | si el  Tag tiene un borde resaltado | ^[boolean]                                                             | false       |
| color               | color de fondo del Tag              | ^[string]                                                              | —           |
| size                | tamaño de la etiqueta               | ^[enum]`'large' \| 'default' \| 'small'`                             | —           |
| effect              | tema de la etiqueta                 | ^[enum]`'dark' \| 'light' \| 'plain'`                                | light       |
| round               | si la etiqueta será redondeada      | ^[boolean]                                                             | false       |

### Tag Events

| Nombre | Descripción                          | Tipo                                      |
| ------ | ------------------------------------ | ----------------------------------------- |
| click  | se dispara cuando el Tag es clic     | ^[Function]`(evt: MouseEvent) => void` |
| close  | se dispara cuando el Tag es removido | ^[Function]`(evt: MouseEvent) => void` |

### Tag Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |

## API CheckTag

### CheckTag Attributes

| Nombre                    | Descripción                       | Tipo                                                                   | Por defecto |
| ------------------------- | --------------------------------- | ---------------------------------------------------------------------- | ----------- |
| checked / v-model:checked | si está comprobado                | ^[boolean]                                                             | false       |
| disabled ^(2.8.2)         | whether the check-tag is disabled | ^[boolean]                                                             | false       |
| type ^(2.5.4)             | type of CheckTag                  | ^[enum]`'primary' \| 'success' \| 'info' \| 'warning' \| 'danger'` | primary     |

### CheckTag Events

| Nombre | Descripción                                 | Tipo                                     |
| ------ | ------------------------------------------- | ---------------------------------------- |
| change | se dispara cuando se hace clic en Check-tag | ^[Function]`(value: boolean) => void` |

### CheckTag Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |
