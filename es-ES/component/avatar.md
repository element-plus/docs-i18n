---
title: Avatar
lang: es-ES
---

# Avatar

Los avatares pueden utilizarse para representar personas u objetos. Soporta imágenes, iconos y caracteres.

## Uso básico

Use las propiedades `shape` y `size` para establecer la forma y el tamaño del avatar.

:::demo

avatar/basic

:::

## Tipos

Soporta imágenes, iconos o caracteres.

:::demo

avatar/types

:::

## Fallback

fallback cuando se produce un error de carga de imagen.

:::demo

avatar/fallback

:::

## Fijar al contenedor

Para ajustar la imagen a su contenedor, use la propiedad "fit". Los valores que admite son los mismos que la propiedad CSS [object-fit](https://developer.mozilla.org/es/docs/Web/CSS/object-fit).

:::demo

avatar/fit

:::

## Avatar Group ^(2.13.1)

Displayed as a avatar group.

:::demo Use tag `<el-avatar-group>` to group your avatars.

avatar/group

:::

## API del Avatar

### Atributos del Avatar

| Nombre  | Descripcíon                                                                                      | Tipo                                                                  | Por defecto |
| ------- | ------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------- | ----------- |
| icon    | establece el tipo de representación a "icono". Para más información vea el componente "el-icon". | ^[string] / ^[Component]                                              | —           |
| size    | tamaño del avatar.                                                                               | ^[number] / ^[enum]`'large' \| 'default' \| 'small'`                | —           |
| shape   | forma del avatar.                                                                                | ^[enum]`'circle' \| 'square'`                                        | —           |
| src     | la dirección URL de la imagen elegida para el avatar.                                            | `string`                                                              | —           |
| src-set | atributo nativo `srcset` del avatar de imagen.                                                   | `string`                                                              | —           |
| alt     | atributo nativo `alt` del avatar de imagen.                                                      | `string`                                                              | —           |
| fit     | determina cómo encaja la imagen en su contenedor para un avatar de imagen.                       | ^[enum]`'fill' \| 'contain' \| 'cover' \| 'none' \| 'scale-down'` | cover       |

### Eventos del Avatar

| Nombre | Descripción                                    | Tipo                               |
| ------ | ---------------------------------------------- | ---------------------------------- |
| error  | se dispara cuando la carga de la imagen falla. | ^[Function]`(e: Event) => void` |

### Slots del Avatar

| Nombre  | Descripción                           |
| ------- | ------------------------------------- |
| default | personaliza el contenido por defecto. |

## AvatarGroup API ^(2.13.1)

### AvatarGroup Attributes

| Nombre                   | Descrición                                                                                                                    | Tipo                                                                                                                                                                                   | Por defecto |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| size                     | control the size of avatars in this avatar-group                                                                              | ^[number] / ^[enum]`'large' \| 'default' \| 'small'`                                                                                                                                 | —           |
| shape                    | control the shape of avatars in this avatar-group                                                                             | ^[enum]`'circle' \| 'square'`                                                                                                                                                         | —           |
| collapse-avatars         | whether to collapse avatars                                                                                                   | ^[boolean]                                                                                                                                                                             | false       |
| collapse-avatars-tooltip | whether show all collapsed avatars when mouse hover text of the collapse-avatar. To use this, `collapse-avatars` must be true | ^[boolean]                                                                                                                                                                             | false       |
| max-collapse-avatars     | the max avatars number to be shown. To use this, `collapse-avatars` must be true                                              | ^[number]                                                                                                                                                                              | 1           |
| effect                   | tooltip theme, built-in theme: `dark` / `light`                                                                               | ^[enum]`'dark' \| 'light'` / ^[string]                                                                                                                                                | light       |
| placement                | placement of tooltip                                                                                                          | ^[enum]`'top' \| 'top-start' \| 'top-end' \| 'bottom' \| 'bottom-start' \| 'bottom-end' \| 'left' \| 'left-start' \| 'left-end' \| 'right' \| 'right-start' \| 'right-end'` | top         |
| popper-class             | custom class name for tooltip                                                                                                 | ^[string]                                                                                                                                                                              | ''          |
| popper-style             | custom style for tooltip                                                                                                      | ^[string] / ^[object]                                                                                                                                                                  | —           |
| collapse-class           | custom class name for the collapse-avatar                                                                                     | ^[string]                                                                                                                                                                              | ''          |
| collapse-style           | custom style for the collapse-avatar                                                                                          | ^[string] / ^[object]                                                                                                                                                                  | —           |
