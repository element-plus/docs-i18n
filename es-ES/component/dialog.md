---
title: Dialog
lang: es-ES
---

# Dialog

Informa a usuarios preservando el estado de la página actual.

## Uso básico

Dialog abre una caja de diálogo, y es bastante personalizable.

:::demo Establezca el `model-value / v-model` con un `Boolean`, y el Dialog se mostrará cuando el valor enlazado sea `true`. El diálogo tiene dos partes: `body` y `footer`, este último requiere un `slot` llamado `footer`. El atributo opcional `title` (vacío por defecto) es para definir un título. Por último, este ejemplo muestra cómo se utiliza `before-close`.

dialog/basic-usage

:::

:::tip

`before-close` solo funciona cuando el usuario hace clic en el icono de cerrar o en el backdrop. Si tiene botones que cierran el diálogo en el slot con nombre `footer`, puede añadir lo que se debería hacer con `before-close` en el manejador de eventos de clic de los botones.

:::

## Contenido personalizado

El contenido del Diálogo puede ser cualquier cosa, incluso una tabla o un formulario. Este ejemplo muestra cómo usar Element Plus Table y Form con Dialog.

:::demo

dialog/customization-content

:::

## Cabecera personalizada

El slot `header` se puede utilizar para personalizar el área donde se muestra el título. Para mantener la accesibilidad, utilice el atributo `title` cuando use el slot, o utilice la propiedad `titleId` para especificar qué elemento debe ser leído como el título del diálogo.

:::demo

dialog/customization-header

:::

## Diálogo anidado

Si un Diálogo está anidado en otro Diálogo, se requiere `append-to-body`.

:::demo Normalmente no recomendamos usar Dialog anidado. Si necesita múltiples Diálogos mostrados en la página, puede aplanarlos para que sean hermanos. Si debe anidar un Diálogo dentro de otro Diálogo, establezca `append-to-body` del Diálogo anidado como true, y lo añadirá al cuerpo en lugar de su nodo padre, para que ambos Diálogos puedan ser correctamente renderizados.

dialog/nested-dialog

:::

## Contenido centrado

El contenido del diálogo se puede centrar.

:::demo Establezca `center` en `true` para centrar horizontalmente el encabezado y el pie de página del cuadro de diálogo. `center` solo afecta al encabezado y pie de página de Dialog. El cuerpo del diálogo puede ser cualquier cosa, así que a veces puede que no se vea bien cuando se centra. Necesita escribir algo de CSS si desea centrar el cuerpo también.

dialog/centered-content

:::

:::tip

El contenido del Diálogo se muestra perezosamente, lo que significa que el slot por defecto se renderiza en el DOM después de que se abra. Por lo tanto, si necesita realizar una manipulación DOM o acceder a un componente usando `ref`, hágalo en el callback del evento `open`.

:::

## Alinear el diálogo al centro

Abrir diálogo desde el centro de la pantalla.

:::demo Configurando `align-center` a `true` centrará el diálogo tanto horizontal como verticalmente. La propiedad `top` no funcionará al mismo tiempo porque el diálogo está centrado verticalmente en una flexbox.

dialog/align-center

:::

## Destruir al cerrar

Cuando esta característica está activada, el contenido en el slot predeterminado se destruirá con una directiva `v-if`. Habilite esto cuando tenga problemas de rendimiento.

:::demo Note que al activar esta función, el contenido no será renderizado antes del `transition.beforeEnter` enviado, solo habrá `overlay` `header (si existe)` y `footer (si existe)`.

dialog/destroy-on-close

:::

## Diálogo arrastrable

Intento de arrastre para la parte del `header`.

:::demo Set `draggable` to `true` to drag. Set `overflow` ^(2.5.4) to `true` can drag overflow the viewport.

dialog/draggable-dialog

:::

:::tip

Cuando se usa `modal` = false, por favor asegúrese de que `append-to-body` se estableció a **true**, porque `Dialog` es posicionado por `position: relative`, cuando `modal` es removido, `Dialog` se colocará basándose en la posición actual en el DOM, en lugar de `Document.Body`, por lo que el estilo será desordenado.

:::

## Fullscreen

Set the `fullscreen` attribute to open fullscreen dialog.

:::demo

dialog/fullscreen

:::

:::tip

If `fullscreen` is true, `width` `top` `draggable` attributes don't work.

:::

## Modal

Setting `modal` to `false` will hide modal (overlay) of dialog.

Starting from version ^(2.10.5), `modal-penetrable` attribute is added, which can be penetrable.

:::demo

dialog/modal

:::

## Custom Animation ^(2.10.5)

Customize dialog animation through the `transition` attribute, which accepts either:

- ​Transition name​​ (string)

- ​​Vue transition configuration​​ (object)

:::demo Examples include scale, slide, fade, bounce animations and object-based configurations with custom event handlers.

dialog/custom-animation

:::

:::tip

Animation classes are dynamically generated based on the transition name. For granular control over animation behavior, you may explicitly define these classes. Refer to [custom-transition-classes](https://vuejs.org/guide/built-ins/transition.html#custom-transition-classes) for details.

:::

## Events

Open developer console (ctrl + shift + J), to see order of events.

:::demo

dialog/events

:::

## API

### Attributes

| Nombre                     | Descripción                                                                                                                    | Tipo                                   | Default     |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------- | ----------- |
| model-value / v-model      | visibilidad del diálogo                                                                                                        | ^[boolean]                             | false       |
| title                      | título del diálogo. También se puede pasar con un slot con nombre (ver la tabla siguiente)                                     | ^[string]                              | ''          |
| width                      | width of Dialog, default is 50%                                                                                                | ^[string] / ^[number]                  | ''          |
| fullscreen                 | si el diálogo ocupa la pantalla completa                                                                                       | ^[boolean]                             | false       |
| top                        | value for `margin-top` of Dialog CSS, default is 15vh                                                                          | ^[string]                              | ''          |
| modal                      | si se muestra una máscara                                                                                                      | ^[boolean]                             | true        |
| modal-penetrable ^(2.10.5) | whether the mask is penetrable. The modal attribute must be `false`.                                                           | ^[boolean]                             | false       |
| modal-class                | custom class names for mask                                                                                                    | ^[string]                              | —           |
| header-class ^(2.9.3)      | custom class names for header wrapper                                                                                          | ^[string]                              | —           |
| body-class ^(2.9.3)        | custom class names for body wrapper                                                                                            | ^[string]                              | —           |
| footer-class ^(2.9.3)      | custom class names for footer wrapper                                                                                          | ^[string]                              | —           |
| append-to-body             | whether to append Dialog itself to body. A nested Dialog should have this attribute set to `true`                              | ^[boolean]                             | false       |
| append-to ^(2.4.3)         | which element the Dialog appends to. Will override `append-to-body`                                                            | ^[CSSSelector] / ^[HTMLElement]        | body        |
| lock-scroll                | whether scroll of body is disabled while Dialog is displayed                                                                   | ^[boolean]                             | true        |
| open-delay                 | the Time(milliseconds) before open                                                                                             | ^[number]                              | 0           |
| close-delay                | the Time(milliseconds) before close                                                                                            | ^[number]                              | 0           |
| close-on-click-modal       | whether the Dialog can be closed by clicking the mask                                                                          | ^[boolean]                             | true        |
| close-on-press-escape      | whether the Dialog can be closed by pressing ESC                                                                               | ^[boolean]                             | true        |
| show-close                 | whether to show a close button                                                                                                 | ^[boolean]                             | true        |
| before-close               | callback before Dialog closes, and it will prevent Dialog from closing, use done to close the dialog                           | ^[Function]`(done: DoneFn) => void` | —           |
| draggable                  | enable dragging feature for Dialog                                                                                             | ^[boolean]                             | false       |
| overflow ^(2.5.4)          | draggable Dialog can overflow the viewport                                                                                     | ^[boolean]                             | false       |
| center                     | whether to align the header and footer in center                                                                               | ^[boolean]                             | false       |
| align-center ^(2.2.16)     | whether to align the dialog both horizontally and vertically                                                                   | ^[boolean]                             | false       |
| destroy-on-close           | destroy elements in Dialog when closed                                                                                         | ^[boolean]                             | false       |
| close-icon                 | custom close icon, default is Close                                                                                            | ^[string] / ^[Component]               | —           |
| z-index                    | same as z-index in native CSS, z-order of dialog                                                                               | ^[number]                              | —           |
| header-aria-level ^(a11y)  | header's `aria-level` attribute                                                                                                | ^[string]                              | 2           |
| transition ^(2.10.5)       | custom transition configuration for dialog animation. Can be a string (transition name) or an object with Vue transition props | ^[string] / ^[object]`TransitionProps` | dialog-fade |
| custom-class ^(deprecated) | custom class names for Dialog                                                                                                  | ^[string]                              | ''          |

:::warning

`custom-class` has been **deprecated**, and **will be** removed in ^(2.4.0), please use `class`.

:::

### Slots

| Nombre              | Descripción                                                                                               |
| ------------------- | --------------------------------------------------------------------------------------------------------- |
| default             | default content of Dialog                                                                                 |
| header              | contenido de la cabecera del diálogo. Reemplazar esto elimina el título, pero no elimina el botón cerrar. |
| footer              | contenido del pie de página del diálogo                                                                   |
| title ^(deprecated) | works the same as the header slot. Use el slot header en lugar de este slot.                              |

:::warning

`title` has been **deprecated**, and **will be** removed in ^(3.0.0), please use `header`.

:::

### Events

| Name             | Description                                                               | Type                       |
| ---------------- | ------------------------------------------------------------------------- | -------------------------- |
| open             | se dispara cuando se abre el Dialog                                       | ^[Function]`() => void` |
| opened           | se dispara cuando la animación de apertura del Dialog termina             | ^[Function]`() => void` |
| close            | se dispara cuando el Diálogo se cierra                                    | ^[Function]`() => void` |
| closed           | se dispara cuando finaliza la animación de cierre del Diálog              | ^[Function]`() => void` |
| open-auto-focus  | se dispara después que el Dialog se abre y el contenido obtiene el foco   | ^[Function]`() => void` |
| close-auto-focus | se dispara después que el Dialog se cierra y el contenido obtiene el foco | ^[Function]`() => void` |

### Exposes

| Name                   | Description    | Type                       |
| ---------------------- | -------------- | -------------------------- |
| resetPosition ^(2.8.1) | reset position | ^[Function]`() => void` |
| handleClose ^(2.9.8)   | close dialog   | ^[Function]`() => void` |

## FAQ

#### Using dialog in SFC, the scope style does not take effect

Typical issue: [#10515](https://github.com/element-plus/element-plus/issues/10515)

PS: Since the dialog is rendered using `Teleport`, the style of the root node is recommended to be written globally.

#### When the dialog is displayed and hidden, there is a situation where the page elements are displaced back and forth

Typical issue: [#10481](https://github.com/element-plus/element-plus/issues/10481)

PS: It is recommended to place the scroll area inside a vue mounted node, e.g. `<div id="app" />`, and use the `overflow: hidden` style for the body.
