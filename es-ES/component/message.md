---
title: Message
lang: es-ES
---

# Message

Utilizado para mostrar comentarios después de una actividad. La diferencia con el componente Notification es que este último es utilizado para mostrar una notificación pasiva.

## Uso básico

Displays at the top by default, and disappears after 3 seconds. You can control the position using the `placement` property.

:::demo La configuración del componente Message es muy similar al del componente notification, así que parte de las opciones no serán explicadas en detalle aquí. Puedes consultar la tabla de opciones en la parte inferior combinada con la documentación del componente notification para comprenderla. Element Plus ha registrado el método `$message` para poder invocarlo. Message puede tomar una cadena o un Vnode como parámetro, y lo mostrara como el cuerpo principal.

message/basic

:::

## Tipos

Utilizado para mostrar los comentarios de Éxito, Advertencia, Mensaje y Error de las actividades.

:::demo Cuando necesite mas personalización, el componente Message también puede tomar un objeto como parámetro. Por ejemplo, estableciendo el valor de `type` puede definir diferentes tipos, el predeterminado es `info`. En tales casos el cuerpo principal se pasa como el valor de `message`. También, hay registrados métodos para los diferentes tipos, así que, puedes llamarlos sin necesidad de pasar un tipo como `open4`. `primary` has been added in ^(2.9.11).

message/different-types

:::

## Plain ^(2.6.3)

Set `plain` to have a plain background.

:::demo

message/plain

:::

## Cerrable

Un botón para cerrar que puede ser agregado.

:::demo Un componente Message predeterminado no se puede cerrar manualmente. Si necesita un componente message que pueda cerrarse, puede establecer el campo `showClose`. Además, al igual que las notificaciones, message tiene un atributo `duration` que puede ser controlado. Por defecto la duración es de 3000 ms, y no desaparecerá al llegar a `0`.

message/closable

:::

## Usando cadenas HTML

`message` soporta cadenas HTML.

:::demo Establezca el valor de `dangerouslyUseHTMLString` a true y `message` será tratado como una cadena HTML.

message/raw-html

:::

:::warning

Aunque la propiedad `message` soporta cadenas HTML, realizar arbitrariamente render dinámico de HTML en nuestro sitio web puede ser muy peligroso, ya que puede conducir fácilmente a [ataques XSS](https://es.wikipedia.org/wiki/Cross-site_scripting). Entonces, cuando `dangerouslyUseHTMLString` está activada, asegúrese que el contenido de `message` sea de confianza, y **nunca** asigne a `message` contenido generado por el usuario.

:::

## Agrupando

fusiona mensajes con el mismo contenido.

:::demo Asigne true a `grouping` y el mismo contenido de `message` será fusionado.

message/grouping

:::

## Placement ^(2.11.0)

Control the position where messages appear. Messages can be displayed at the top (default) or other placements of the viewport.

:::demo

message/placement

:::

## Métodos Globales

Element Plus ha agregado un método global llamado `$message` para `app.config.globalProperties`. Así en una instancia de vue puede llamar a `Mensaje` como lo que hicimos en esta página.

## Importación local

```ts
import { ElMessage } from 'element-plus'
```

En este caso debería llamar al método `ElMessage(options)`. También se han registrado métodos para los diferentes tipos, e.g. `ElMessage.success(options)`. Puede llamar al método `ElMessage.closeAll()` para cerrar manualmente todas las instancias.

## App context inheritance ^(2.0.3)

Ahora Message acepta un `context` como segundo parámetro del constructor de mensajes que le permite inyectar el contexto de la aplicación actual al mensaje, lo que le permite heredar todas las propiedades de la aplicación.

Puede usarlo así:

:::tip

Si ha registrado globalmente el componente ElMessage, automáticamente heredará el contexto de la aplicación.

:::

```ts
import { getCurrentInstance } from 'vue'
import { ElMessage } from 'element-plus'

// in your setup method
const { appContext } = getCurrentInstance()!
ElMessage({}, appContext)
```

## API

### Opciones

| Nombre                   | Descripción                                                                                                       | Tipo                                                                                            | Por defecto |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------- |
| message                  | texto del mensaje                                                                                                 | ^[string] / ^[VNode] / ^[Function]`() => VNode`                                              | ''          |
| type                     | tipo de mensaje                                                                                                   | ^[enum]`'primary' (2.9.11) \| 'success' \| 'warning' \| 'info' \| 'error'`                  | info        |
| plain ^(2.6.3)           | whether message is plain                                                                                          | ^[boolean]                                                                                      | false       |
| icon                     | componente de icono personalizado, sobreescribe `type`                                                            | ^[string] / ^[Component]                                                                        | —           |
| dangerouslyUseHTMLString | utilizado para que `message` sea tratado como cadena HTML                                                         | ^[boolean]                                                                                      | false       |
| customClass              | nombre de clase personalizado para el componente Message                                                          | ^[string]                                                                                       | ''          |
| duration                 | duración del tiempo en que será mostrado, en milisegundos. Si se establece a 0, no se desactivará automáticamente | ^[number]                                                                                       | 3000        |
| showClose                | si se muestra el botón de cerrar                                                                                  | ^[boolean]                                                                                      | false       |
| onClose                  | función callback ejecutada cuando se cierra con una instancia de message como parámetro                           | ^[Function]`() => void`                                                                      | —           |
| offset                   | set the distance to the viewport edge (top when placement is 'top', bottom when placement is 'bottom')            | ^[number]                                                                                       | 16          |
| placement ^(2.11.0)      | message placement position                                                                                        | ^[enum]`'top' \| 'top-left' \| 'top-right' \| 'bottom' \| 'bottom-left' \| 'bottom-right'` | top         |
| appendTo                 | establecer el elemento raíz del mensaje, por defecto `document.body`                                              | ^[CSSSelector] / ^[HTMLElement]                                                                 | —           |
| grouping                 | combinar mensajes con el mismo contenido, el tipo de mensaje VNode no está soportado                              | ^[boolean]                                                                                      | false       |
| repeatNum                | The number of repetitions, similar to badge, is used as the initial number when used with `grouping`              | ^[number]                                                                                       | 1           |

### Métodos

`Message` y `this.$message` regresan una instancia del componente Message. Para cerrar manualmente la instancia, puede llamar al método `close`.

| Nombre | Descripción                  | Tipo                       |
| ------ | ---------------------------- | -------------------------- |
| close  | cierra el componente Message | ^[Function]`() => void` |
