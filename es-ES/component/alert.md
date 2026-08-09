---
title: Alert
lang: es-ES
---

# Alert

Muestra mensajes importantes como alertas.

## Uso básico

Los componentes de alertas no son elementos overlay de la página y no desaparecen automáticamente.

:::demo Alert provides 5 types of themes defined by `type`, whose default value is `info`. `primary` has been added in ^(2.9.11).

alert/basic

:::

## Temas

Alert provee dos diferentes temas `light` y `dark`.

:::demo Use `effect` para cambiar el tema, por defecto es `light`.

alert/theme

:::

## Botón de cierre personalizable

Personalice el botón cerrar con texto u otros símbolos.

:::demo Alert permite configurar si el usuario lo puede cerrar. El texto del botón de cierre y los callbacks de cierre también son personalizables. El atributo `closable` define si el componente puede cerrarse o no. Acepta un `boolean`, que por defecto es `true`. También puede configurar el atributo `close-text` para reemplazar el símbolo de cerrado que se muestra por defecto. El atributo `close-text` debe ser un string. El evento `close` se dispara cuando el componente se cierra.

alert/close-button

:::

## Con icono

Muestra un icono para mejorar la legibilidad.

:::demo Setting the `show-icon` attribute displays an icon that corresponds with the current Alert type. Or use the `icon` slot to customize icon.

alert/icon

:::

## Centrar texto

Para centrar el texto utilice el atributo `center`.

:::demo

alert/center

:::

## Con descripción

La descripción incluye un mensaje con información más detallada.

:::demo Además del atributo requerido `title`, se puede agregar el atributo `description` para ayudar a describir la alerta con más detalles. La descripción puede contener solamente un string y va a usar word wrap automáticamente.

alert/description

:::

## Con icono y descripción

:::demo Finalmente, este es un ejemplo utilizando icono y descripción.

alert/icon-description

:::

## API del Alert

### Atributos

| Nombre      | Descripción                                     | Tipo                                                                           | Por defecto |
| ----------- | ----------------------------------------------- | ------------------------------------------------------------------------------ | ----------- |
| title       | título de la alerta.                            | ^[string]                                                                      | —           |
| type        | tipo de alerta.                                 | ^[enum]`'primary' (2.9.11) \| 'success' \| 'warning' \| 'info' \| 'error'` | info        |
| description | texto descriptivo.                              | ^[string]                                                                      | —           |
| closable    | si la alerta puede ser descartada.              | ^[boolean]                                                                     | true        |
| center      | si el contenido se coloca en el centro.         | ^[boolean]                                                                     | false       |
| close-text  | texto personalizado del botón de cierre.        | ^[string]                                                                      | —           |
| show-icon   | si el icono del tipo de alerta se debe mostrar. | ^[boolean]                                                                     | false       |
| effect      | estilo del tema.                                | ^[enum]`'light' \| 'dark'`                                                    | light       |

### Eventos

| Nombre | Descripción                            | Tipo                                        |
| ------ | -------------------------------------- | ------------------------------------------- |
| close  | se dispara cuando la alerta se cierra. | ^[Function]`(event: MouseEvent) => void` |

### Slots

| Nombre        | Descripción                               |
| ------------- | ----------------------------------------- |
| default       | contenido de la descripción de la alerta. |
| title         | contenido del título.                     |
| icon ^(2.9.7) | content of the alert icon.                |
