---
title: Message
lang: es-ES
---

# Message Box

Un conjunto de cajas modales simulando un sistema de message box, principalmente para alertar información, confirmar operaciones y mostrar mensajes de aviso.

:::tip

Por diseño, MessageBox proporciona simulaciones de `alert` del sistema, `confirm` y `prompt`, por lo que su contenido debería ser simple. Para contenido más complejo, por favor utilice el componente Dialog.

:::

## Alerta

La alerta interrumpe la operación del usuario hasta que el usuario lo confirme.

:::demo Abre una alerta llamando al método `ElMessageBox.alert`. Simula la `alert` del sistema, y no puede ser cerrado al presionar la tecla ESC o al dar clic fuera de la caja. En este ejemplo, dos parámetros son recibidos `message` y `title`. Vale la pena mencionar que cuando la caja es cerrada, regresa una `Promise` para su procesamiento posterior. Si no está seguro de si sus navegadores de destino apoyan `Promise`, debería importar un polyfill de terceros o usar callbacks como este ejemplo.

message-box/alert

:::

## Confirmación

Confirm es utilizado para preguntar al usuario y recibir una confirmación.

:::demo Llamada al método `ElMessageBox.confirm` para abrir una confirmación, y simular la `confirmación (confirm)` del sistema. También podemos personalizar en gran medida el componente Message Box al mandar un tercer atributo llamado `options` que es un objeto. The attribute `type` indicates the message type, and it's value can be `primary`, `success`, `error`, `info` and `warning`. Se debe tener en cuenta que el segundo atributo `title` debe ser de tipo `string`, y si es de tipo `object`, será manejado como el atributo `options`. Aquí utilizamos `Promise` para manejar procesos posteriores. `primary` has been added in ^(2.9.11).

message-box/confirm

:::

## Preguntar

Prompt es utilizado cuando se requiere entrada de información del usuario.

:::demo Llamada al método `ElMessageBox.prompt` para abrir un diálogo que solicita un dato al usuario y simula el `prompt` del sistema. Puede utilizar el parámetro `inputPattern` para especificar su propio patrón RegExp. Utilice `inputValidator` para especificar el método de validación, y debe devolver `Boolean` o `String`. Al regresar `false` o `String` significa que la validación ha fallado, y la cadena regresada se usara como `inputErrorMessage`. Además, puedes personalizar el atributo placeholder del input box con el parámetro `inputPlaceholder`.

message-box/prompt

:::

## Use VNode

`mensaje` puede ser VNode.

:::demo

message-box/use-vnode

:::

## Use VNode With Action Handlers ^(2.14.0)

You can receive `{ confirm, cancel, close }` as parameters in `message`, which allows custom content to trigger the same MessageBox actions programmatically and automatically close the instance.

:::demo

message-box/use-vnode-with-action-handlers

:::

## Personalización

Se puede personalizar para mostrar varios contenidos.

:::demo Los tres métodos mencionados anteriormente son los reempaquetados del método `ElMessageBox`. Este ejemplo llama al método `ElMessageBox` directamente usando el atributo `showCancelButton`, que se utiliza para indicar si se muestra un botón de cancelación. Además, podemos usar `cancelButtonClass` para añadir un estilo personalizado y `cancelButtonText` para personalizar el texto del botón (el botón de confirmación también tiene estos campos, y una lista completa de campos se puede encontrar al final de esta documentación). Este ejemplo también usa el atributo `beforeClose`. Es un método y se activará cuando se cierre la instancia de MessageBox y su ejecución impedirá que la instancia se cierre. Tiene tres parámetros: `action`, `instance` y `done`. Utilizarlo le permite manipular la instancia antes de que se cierre, p.ej. activando `loading` para el botón de confirmar; puede invocar el método `done` para cerrar la instancia de MessageBox (si `done` no es llamado dentro de `beforeClose`, la instancia no se cerrará).

message-box/customization

:::

## Usando cadenas HTML

`mensaje` soporta cadena HTML.

:::demo Establezca el valor de `dangerouslyUseHTMLString` a true y el `message` será tratado como una cadena HTML.

message-box/use-html

:::

:::warning

Aunque la propiedad `message` soporta cadenas HTML, renderizando HTML arbitrario en su sitio web puede ser muy peligroso porque puede llevar fácilmente a [ataques XSS](https://en.wikipedia.org/wiki/Cross-site_scripting). Así que cuando `peligouslyUseHTMLString` esté encendido, por favor asegúrese de que el contenido del `menssage` es de confianza, y **nunca** asigne `menssage` al contenido proporcionado por el usuario.

:::

## Distinguir entre cancelar y cerrar

En algunos casos, hacer clic en el botón cancelar y cerrar puede tener diferentes significados.

:::demo por defecto, los parámetros de la devolución de llamada rechazada de Promise y `callback` son 'cancel' cuando el usuario cancela (haciendo clic en el botón cancelar) y cierra (haciendo clic en el botón cerrar o en la capa de máscara, presionando la tecla ESC) el MessageBox. Si `distinguishCancelAndClose` está establecido en true, los parámetros de las dos operaciones anteriores son 'cancel' y 'close' respectivamente.

message-box/distinguishable-close-cancel

:::

## Contenido centrado

El contenido de MessageBox se puede centrar.

:::demo Establezca `center` a `true` y centrará el contenido.

message-box/centered-content

:::

## Icono personalizado

El icono se puede personalizar a cualquier componente Vue o función de renderizado [(JSX)](https://vuejs.org/guide/extras/render-function.html).

:::demo

message-box/customized-icon

:::

## Draggable

MessageBox puede ser arrastrable.

:::demo Setting `draggable` to `true` allows user to drag MessageBox. Set `overflow` ^(2.5.4) to `true` can drag overflow the viewport.

message-box/draggable

:::

## Métodos Globales

Si Element Plus se importa completamente, se añadirán los siguientes métodos globales para `app.config.globalProperties`: `$msgbox`, `$alert`, `$confirm` y `$prompt`. Así que en una instancia de Vue puede llamar a `MessageBox` como lo que hicimos en esta página. Los parámetros son:

- `$msgbox(options)`
- `$alert(message, title, options)` or `$alert(message, options)`
- `$confirm(message, title, options)` or `$confirm(message, options)`
- `$prompt(message, title, options)` or `$prompt(message, options)`

## Herencia de contexto de aplicación <el-tag>> 2.0.4</el-tag>

Now message box accepts a `context` as second (fourth if you are using message box variants) parameter of the message constructor which allows you to inject current app's context to message which allows you to inherit all the properties of the app.

```ts
import { getCurrentInstance } from 'vue'
import { ElMessageBox } from 'element-plus'

// in your setup method
const { appContext } = getCurrentInstance()!
// You can pass it like:
ElMessageBox({}, appContext)
// or if you are using variants
ElMessageBox.alert('Hello world!', 'Title', {}, appContext)
```

## Importación local

Si prefiere importar `MessageBox` bajo demanda:

```ts
import { ElMessageBox } from 'element-plus'
```

Los métodos correspondientes son: `ElMessageBox`, `ElMessageBox.alert`, `ElMessageBox.confirm` y `ElMessageBox.prompt`. Los parámetros son los mismos que los anteriores.

## API

### Options

| Name                              | Descripción                                                                                                                                                 | Tipo                                                                                                                           | Default                                          |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------ |
| autofocus                         | autofocalización al abrir MessageBox                                                                                                                        | ^[boolean]                                                                                                                     | true                                             |
| title                             | título del componente MessageBox                                                                                                                            | ^[string]                                                                                                                      | ''                                               |
| message                           | contenido del componente MessageBox                                                                                                                         | ^[string] / ^[VNode] / ^[Function]`() => VNode` ^(2.2.17) / ^[Function]`({ confirm, cancel, close }) => VNode` ^(2.14.0) | —                                                |
| dangerouslyUseHTMLString          | utilizado para que `message` sea tratado como cadena HTML                                                                                                   | ^[boolean]                                                                                                                     | false                                            |
| type                              | tipo de mensaje, utilizado para mostrar el icono                                                                                                            | ^[enum]`'primary' (2.9.11) \| 'success' \| 'info' \| 'warning' \| 'error'`                                                 | ''                                               |
| icon                              | componente de icono personalizado, sobreescribe `type`                                                                                                      | ^[string] / ^[Component]                                                                                                       | ''                                               |
| closeIcon ^(2.9.5)                | custom close icon component, default is Close                                                                                                               | ^[string] / ^[Component]                                                                                                       | ''                                               |
| customClass                       | nombre de la clase personalizada para el componente MessageBox                                                                                              | ^[string]                                                                                                                      | ''                                               |
| customStyle                       | estilo en línea personalizado para MessageBox                                                                                                               | ^[CSSProperties]                                                                                                               | {}                                               |
| modal                             | si se muestra una máscara                                                                                                                                   | ^[boolean]                                                                                                                     | true                                             |
| modalClass                        | custom class names for mask                                                                                                                                 | string                                                                                                                         | —                                                |
| callback                          | Función de callback al cerrar MessageBox si no desea utilizar Promise                                                                                       | ^[Function]`(value: string, action: Action) => any \| (action: Action) => any`                                          | null                                             |
| showClose                         | si desea mostrar el icono cerrar de MessageBox                                                                                                              | ^[boolean]                                                                                                                     | true                                             |
| beforeClose                       | una función callback antes de que se cierre el MessageBox, y con esto se pueden tomar previsiones al cierre, incluso evitar que el cuadro pueda ser cerrado | ^[Function]`(action: Action, instance: MessageBoxState, done: () => void) => void`                                       | null                                             |
| distinguishCancelAndClose         | si distinguir cancelar y cerrar el MessageBox                                                                                                               | ^[boolean]                                                                                                                     | false                                            |
| lockScroll                        | si bloquear el desplazamiento del cuerpo                                                                                                                    | ^[boolean]                                                                                                                     | true                                             |
| showCancelButton                  | si desea mostrar un botón de cancelar                                                                                                                       | ^[boolean]                                                                                                                     | false (true when called with confirm and prompt) |
| showConfirmButton                 | si desea mostrar un botón de confirmar                                                                                                                      | ^[boolean]                                                                                                                     | true                                             |
| cancelButtonText                  | contenido de texto del botón cancelar                                                                                                                       | ^[string]                                                                                                                      | Cancel                                           |
| confirmButtonText                 | contenido de texto del botón confirmar                                                                                                                      | ^[string]                                                                                                                      | OK                                               |
| cancelButtonType ^(2.13.1)        | type of cancel button                                                                                                                                       | ^[enum]`'primary' \| 'success' \| 'warning' \| 'danger' \| 'info' \| 'text' (deprecated)`                                 | —                                                |
| confirmButtonType ^(2.13.1)       | type of confirm button                                                                                                                                      | ^[enum]`'primary' \| 'success' \| 'warning' \| 'danger' \| 'info' \| 'text' (deprecated)`                                 | primary                                          |
| cancelButtonLoadingIcon ^(2.7.7)  | loading icon content of cancel button                                                                                                                       | ^[string] / ^[Component]                                                                                                       | Loading                                          |
| confirmButtonLoadingIcon ^(2.7.7) | loading icon content of confirm button                                                                                                                      | ^[string] / ^[Component]                                                                                                       | Loading                                          |
| cancelButtonClass                 | nombre de la clase personalizada del botón cancelar                                                                                                         | ^[string]                                                                                                                      | ''                                               |
| confirmButtonClass                | nombre de la clase personalizada del botón confirmar                                                                                                        | ^[string]                                                                                                                      | ''                                               |
| closeOnClickModal                 | si MessageBox puede cerrarse haciendo clic en la máscara                                                                                                    | ^[boolean]                                                                                                                     | true (false when called with alert)              |
| closeOnPressEscape                | si MessageBox puede cerrarse presionando el ESC                                                                                                             | ^[boolean]                                                                                                                     | true (false when called with alert)              |
| closeOnHashChange                 | si cerrar MessageBox cuando el hash cambie                                                                                                                  | ^[boolean]                                                                                                                     | true                                             |
| showInput                         | si desea mostrar un input                                                                                                                                   | ^[boolean]                                                                                                                     | false (true when called with prompt)             |
| inputPlaceholder                  | placeholder del input                                                                                                                                       | ^[string]                                                                                                                      | ''                                               |
| inputType                         | type of input, see more in [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Form_%3Cinput%3E_types)                                    | ^[string]`'text' \| 'textarea' \| 'number' \| 'password' \| 'email' \| 'search' \| 'tel' \|  'url'`                     | text                                             |
| inputValue                        | valor inicial del input                                                                                                                                     | ^[string]                                                                                                                      | ''                                               |
| inputPattern                      | regexp para el input                                                                                                                                        | ^[regexp]                                                                                                                      | null                                             |
| inputValidator                    | función de validación del input. Debe regresar un valor de tipo boolean o string. Si regresa un valor tipo string, será asignado a inputErrorMessage        | ^[Function]`(value: string) => boolean \| string`/ `undefined`                                                             | undefined                                        |
| inputErrorMessage                 | mensaje de error cuando la validación falla                                                                                                                 | ^[string]                                                                                                                      | Illegal input                                    |
| center                            | si centrar el contenido                                                                                                                                     | ^[boolean]                                                                                                                     | false                                            |
| draggable                         | si MessageBox es arrastrable                                                                                                                                | ^[boolean]                                                                                                                     | false                                            |
| overflow ^(2.5.4)                 | draggable MessageBox can overflow the viewport                                                                                                              | ^[boolean]                                                                                                                     | false                                            |
| roundButton                       | si usar los botones redondos                                                                                                                                | ^[boolean]                                                                                                                     | false                                            |
| buttonSize                        | tamaño personalizado de botones de confirmación y cancelación                                                                                               | ^[string]`'small' \| 'default' \| 'large'`                                                                                   | default                                          |
| appendTo ^(2.2.19)                | establecer el elemento raíz para el message box                                                                                                             | ^[CSSSelector] / ^[HTMLElement]                                                                                                | —                                                |
