---
title: Button
lang: es-ES
---

# Button

Botones comúnmente usados.

## Uso básico

:::demo Use `type`, `plain`, `round`, `dashed` and `circle` to define Button's style.

button/basic

:::

## Botón deshabilitado

El atributo `disabled` determina si un botón está deshabilitado.

:::demo Use el atributo `disabled` para determinar si un botón esta deshabilitado. Acepta un valor `Boolean`.

button/disabled

:::

## Botón de enlace

:::warning

`type="text"` ha sido **descontinuado** y **será** eliminado en ^(3.0.0), considere cambiar a la nueva API.

Una nueva API del `link` ha sido añadido en ^(2.2.1), puede usar `type` para establecer el tema de su botón de enlace

:::

:::demo

button/link

:::

## Botón de texto

:::tip

El botón de texto ha sido actualizado con un nuevo diseño desde <el-tag round effect="plain" size="small">2.2.0</el-tag> , si quiere usar el botón como en la versión anterior, tal vez quiera revisar [Link](./link.md#basic).

La API también se actualizó, porque el atributo `type` también representa el estilo del botón. Así que tenemos que crear una nueva API `text: boolean` para el botón de texto.

:::

Botones sin borde ni fondo.

:::demo

button/text

:::

## Botón de icono

Use iconos para añadir más significado al botón. Se puede usar simplemente un icono o un icono con texto.

:::demo Use el atributo `icon` para agregar un icono. Puede encontrar la lista de iconos en el componente de iconos de Element Plus. Agregar iconos a la derecha del texto se puede conseguir con un tag `<i>`. También se pueden usar iconos personalizados.

button/icon

:::

## Grupo de botones

Mostrar un grupo de botones puede ser usado para mostrar un grupo de operaciones similares.

In ^(2.11.9) you can use the `direction` attribute.

:::demo Use el tag `<el-button-group>` para agrupar sus botones.

button/group

:::

## Botón de carga

Cuando se hace clic en un botón para descargar datos, el botón muestra un estado de carga.

Ajuste el atributo `loading` a `true` para mostrar el estado de carga.

:::tip

Puede utilizar el slot `loading` o `loadingIcon` para personalizar el componente de carga

ps: el slot `loading` tiene mayor prioridad que loadingIcon

:::

:::demo

button/loading

:::

## Tamaños

Además del tamaño predeterminado, el componente Button proporciona dos tamaños adicionales para que usted elija entre diferentes escenarios.

:::demo Use el atributo `size` para aplicar tamaños adicionales con `large` o `small`.

button/size

:::

## Etiqueta ^(2.3.4)

Puede personalizar la etiqueta del elemento, Por ejemplo, botón, div, a, router-link, nuxt-link.

:::demo

button/tag

:::

## Color personalizado ^(beta)

Puede personalizar el color del botón.

Calcularemos automáticamente el color del hover & del activo.

The `color` prop also works with `link` and `text` buttons since ^(2.13.7).

:::demo

button/custom

:::

## API del Botón

### Button Attributes

| Nombre            | Descripción                                                                                                                                          | Tipo                                                                                                                | Por defecto |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ----------- |
| size              | tamaño del botón                                                                                                                                     | ^[enum]`'large' \| 'default' \| 'small'`                                                                          | —           |
| type              | button type, when setting `color`, the latter prevails                                                                                               | ^[enum]`'default' \| 'primary' \| 'success' \| 'warning' \| 'danger' \| 'info' \| '' \| 'text' (deprecated)` | —           |
| plain             | determina si es un botón plano                                                                                                                       | ^[boolean]                                                                                                          | false       |
| text ^(2.2.0)     | determinar si es un botón de texto                                                                                                                   | ^[boolean]                                                                                                          | false       |
| bg ^(2.2.0)       | determinar si el color de fondo del botón de texto está siempre encendido                                                                            | ^[boolean]                                                                                                          | false       |
| link ^(2.2.1)     | determinar si es un botón de enlace                                                                                                                  | ^[boolean]                                                                                                          | false       |
| round             | determinar si es un botón redondo                                                                                                                    | ^[boolean]                                                                                                          | false       |
| circle            | determina si es un botón circular                                                                                                                    | ^[boolean]                                                                                                          | false       |
| dashed ^(2.13.3)  | determine whether it's a dashed button                                                                                                               | ^[boolean]                                                                                                          | false       |
| loading           | determina si está cargando                                                                                                                           | ^[boolean]                                                                                                          | false       |
| loading-icon      | personalizar el componente de icono de carga                                                                                                         | ^[string] / ^[Component]                                                                                            | Loading     |
| disabled          | desactiva el botón                                                                                                                                   | ^[boolean]                                                                                                          | false       |
| icon              | componente de icono                                                                                                                                  | ^[string] / ^[Component]                                                                                            | —           |
| autofocus         | igual que en el botón nativo `autofocus`                                                                                                             | ^[boolean]                                                                                                          | false       |
| native-type       | igual que en el botón nativo `type`                                                                                                                  | ^[enum]`'button' \| 'submit' \| 'reset'`                                                                          | button      |
| auto-insert-space | automatically insert a space between two chinese characters(this will only take effect when the text length is 2 and all characters are in Chinese.) | ^[boolean]                                                                                                          | false       |
| color             | custom button color, automatically calculate `hover` and `active` color. Works with `link`/`text` buttons since ^(2.13.7)                            | ^[string]                                                                                                           | —           |
| dark              | modo oscuro, que convierte automáticamente `color` a colores oscuros                                                                                 | ^[boolean]                                                                                                          | false       |
| tag ^(2.3.4)      | etiqueta de elemento personalizada                                                                                                                   | ^[string] / ^[Component]                                                                                            | button      |

### Button Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |
| loading | personaliza componente de carga      |
| icon    | personaliza el componente de icono   |

### Button Exposes

| Nombre         | Descripción             | Tipo                                                                                                                        |
| -------------- | ----------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| ref            | elemento html del botón | ^[object]`Ref<HTMLButtonElement>`                                                                                     |
| size           | tamaño del botón        | ^[object]`ComputedRef<'' \| 'small' \| 'default' \| 'large'>`                                                      |
| type           | button type             | ^[object]`ComputedRef<'' \| 'default' \| 'primary' \| 'success' \| 'warning' \| 'info' \| 'danger' \| 'text'>` |
| disabled       | botón deshabilitado     | ^[object]`ComputedRef<boolean>`                                                                                       |
| shouldAddSpace | si agrega espacio       | ^[object]`ComputedRef<boolean>`                                                                                       |

## API de ButtonGroup

### ButtonGroup Attributes

| Nombre              | Descripción                                                | Tipo                                                                   | Por defecto |
| ------------------- | ---------------------------------------------------------- | ---------------------------------------------------------------------- | ----------- |
| size                | controla el tamaño de los botones en este grupo de botones | ^[enum]`'large' \| 'default' \| 'small'`                             | —           |
| type                | controlar el tipo de botones en este grupo de botones      | ^[enum]`'primary' \| 'success' \| 'warning' \| 'danger' \| 'info'` | —           |
| direction ^(2.11.9) | dirección en la que se muestra el contenido                | ^[enum]`'horizontal' \| 'vertical'`                                   | horizontal  |

### ButtonGroup Slots

| Nombre  | Descripción                                   | Subetiquetas |
| ------- | --------------------------------------------- | ------------ |
| default | personaliza el contenido del grupo de botones | Button       |
