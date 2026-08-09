---
title: Notification
lang: es-ES
---

# Notificación

Muestra un mensaje de notificación global en una esquina de la página.

## Uso básico

:::demo Element Plus ha registrado el método`$notify` y recibe un objeto como parámetro. En el caso más sencillo, puede establecer el campo de `title` y el campo de `message` para el título y el cuerpo de la notificación. De forma predeterminada, la notificación se cierra automáticamente después de 4500ms, pero configurando `duration` se puede controlar su duración. Específicamente, si está configurado en `0`, no se cerrará automáticamente. Tenga en cuenta que `duration` recibe un `Number` en milisegundos.

notification/basic

:::

## Tipos de notificaciones

Proporcionamos cuatro tipos: success, warning, info y error.

:::demo Element Plus provides four notification types: `primary`, `success`, `warning`, `info` and `error`. Se definen por el campo `type` y se ignorarán otros valores. También se han registrado métodos para estos tipos que se pueden invocar directamente como en el ejemplo `open3` y `open4` sin pasar un campo `type`. `primary` has been added in ^(2.9.11).

notification/different-types

:::

## Posición personalizada

La notificación puede surgir de cualquier rincón que uno desee.

:::demo El atributo `position` define desde qué esquina se desliza la notificación. Puede ser `top-right`, `top-left`, `bottom-right` o `bottom-left`. Predeterminado: `top-right`.

notification/positioning

:::

## Con desplazamiento

Personalice el desplazamiento de notificación desde el borde de la pantalla.

:::demo Configure el atributo `offset` para personalizar el desplazamiento de la notificación desde el borde de la pantalla. Tenga en cuenta que cada instancia de la notificación del mismo momento debe tener el mismo desplazamiento.

notification/offsetting

:::

## Usando cadenas HTML

`message` soporta cadenas HTML.

:::demo Establezca el valor de `dangerouslyUseHTMLString` a true y el `message` será tratado como una cadena HTML.

notification/raw-html

:::

:::warning

Aunque la propiedad `message` soporta cadenas HTML, realizar arbitrariamente render dinámico de HTML en nuestro sitio web puede ser muy peligroso, ya que puede conducir fácilmente a [ataques XSS](https://es.wikipedia.org/wiki/Cross-site_scripting). Entonces cuando `dangerouslyUseHTMLString` esta activada, asegúrese que el contenido de `message` sea de confianza, y **nunca** asignar `message` a contenido generado por el usuario.

:::

## Message using functions ^(2.9.0)

`message` can be VNode.

After ^(2.9.0), `message` supports a function whose return value is a VNode.

:::demo

notification/use-vnode

:::

## With progress bar ^(2.14.4)

Display a progress bar indicating the remaining time before the notification auto-closes.

:::demo Set `progress` to `true` to enable the progress bar. The progress bar will show a countdown matching the `duration`. Pass an object to `progress` to customize it with the options of [Progress](./progress.html#attributes), e.g. `color`, which overrides the `type`-based status color. When `pauseOnHover` is `true` (default), hovering over the notification will pause both the timer and the progress bar.

notification/progress-bar

:::

## Ocultar boton de cerrar

Es posible ocultar el botón de cerrar

:::demo Configure el atributo `showClose` como `false` para que el usuario no pueda cerrar la notificación.

notification/no-close

:::

## Métodos Globales

Element Plus ha añadido un método global `$notify` para `app.config.globalProperties`. Así que en una instancia de vue se puede llamar `Notification` como lo hacemos en esta página.

## Importación local

```javascript
import { ElNotification } from 'element-plus'
import { CloseBold } from '@element-plus/icons-vue'

ElNotification({
  title: 'Title',
  message: 'This is a message',
  closeIcon: CloseBold,
})
```

En este caso, debe llamar a `ElNotification(options)`. También se han registrado métodos para diferentes tipos, e.j. `ElNotification.success(options)`. Puede llamar al método `ElNotification.closeAll()` para cerrar manualmente todas las instancias. In ^(2.10.5) you can manually update the offsets of all instances in a specific direction by calling `ElNotification.updateOffsets(position)`.

## Herencia de contexto de aplicación <el-tag>> 2.0.4</el-tag>

Ahora la notificación acepta un `context` como segundo parámetro del constructor de mensajes que le permite inyectar el contexto de la aplicación actual a la notificación, lo que le permite heredar todas las propiedades de la aplicación.

Puede usarlo así:

:::tip

Si has registrado globalmente el componente ElNotification automáticamente heredará el contexto de la aplicación.

:::

```ts
import { getCurrentInstance } from 'vue'
import { ElNotification } from 'element-plus'

// in your setup method
const { appContext } = getCurrentInstance()!
ElNotification({}, appContext)
```

## API

### Opciones

| Nombre                   | Descripción                                                                                                                                                                                                                                        | Tipo                                                                                  | Por defecto |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ----------- |
| title                    | title                                                                                                                                                                                                                                              | ^[string]                                                                             | ''          |
| message                  | texto explicativo                                                                                                                                                                                                                                  | ^[string] / ^[VNode] / ^[Function]`() => VNode`                                    | ''          |
| dangerouslyUseHTMLString | si `message` es tratado como una cadena HTML                                                                                                                                                                                                       | ^[boolean]                                                                            | false       |
| type                     | tipo de notificación                                                                                                                                                                                                                               | ^[enum]`'primary' (2.9.11) \| 'success' \| 'warning' \| 'info' \| 'error' \| ''` | ''          |
| icon                     | componente de icono personalizado. Será anulado por `type`                                                                                                                                                                                         | ^[string] / ^[Component]                                                              | —           |
| customClass              | nombre de clase personalizado para la notificación                                                                                                                                                                                                 | ^[string]                                                                             | ''          |
| duration                 | duración antes de cerrar. Si no se quiere que se cierre automáticamente, este valor debe estar a 0                                                                                                                                                 | ^[number]                                                                             | 4500        |
| position                 | posición personalizada                                                                                                                                                                                                                             | ^[enum]`'top-right' \| 'top-left' \| 'bottom-right' \| 'bottom-left'`              | top-right   |
| showClose                | si se muestra el botón de cerrar                                                                                                                                                                                                                   | ^[boolean]                                                                            | true        |
| onClose                  | función que se ejecuta cuando la notificación se cierra                                                                                                                                                                                            | ^[Function]`() => void`                                                            | —           |
| onClick                  | función que se ejecuta cuando se hace clic en la notificación                                                                                                                                                                                      | ^[Function]`() => void`                                                            | —           |
| offset                   | desplazamiento desde el borde superior de la pantalla. Cada instancia de notificación del mismo momento debe tener siempre el mismo desplazamiento                                                                                                 | ^[number]                                                                             | 0           |
| appendTo                 | establecer el elemento raíz para la notificación, por defecto `document.body`                                                                                                                                                                      | ^[CSSSelector] / ^[HTMLElement]                                                       | —           |
| zIndex                   | zIndex inicial                                                                                                                                                                                                                                     | ^[number]                                                                             | 0           |
| closeIcon ^(2.9.8)       | custom close icon                                                                                                                                                                                                                                  | ^[string] / ^[Component]                                                              | Close       |
| progress ^(2.14.4)       | progress bar indicating auto-close countdown. Set `true` to show a default bar, or pass an object with [Progress options](./progress.html#attributes) to customize it (`percentage`, `type`, `duration`, `indeterminate` and `width` are excluded) | ^[boolean] / ^[object]                                                                | false       |
| pauseOnHover ^(2.14.4)   | whether to pause the timer when hovering over the notification                                                                                                                                                                                     | ^[boolean]                                                                            | true        |

### Método

`Notification` y `this.$notify` devuelven la instancia de la notificación actual. Para cerrar manualmente la instancia, se puede llamar a `close` para ello.

| Nombre | Descripción            | Tipo                       |
| ------ | ---------------------- | -------------------------- |
| close  | cierra la notificación | ^[Function]`() => void` |
