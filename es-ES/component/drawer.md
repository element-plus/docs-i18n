---
title: Drawer
lang: es-ES
---

# Drawer

A veces, `Dialog` no satisface nuestros requisitos, digamos que tiene un formulario masivo, o necesita espacio para mostrar algo como `terminos & condiciones`, `Drawer` tiene una API casi idéntica a `Dialog`, pero introduce una experiencia de usuario diferente.

:::tip

Dado que v-model es nativamente soportado para todos los componentes, `visible.sync` ha sido desaprobado, use `v-model="visibilityBinding"` para controlar la visibilidad del drawer actual.

:::

## Uso básico

Llamada de un drawer temporal, desde varias direcciones

:::demo Debe establecer `model-value` para `Drawer` como lo hace `Dialog` para controlar la visibilidad, con un valor del tipo `boolean`. `Drawer` tiene tres partes: `title` & `body` & `footer`, el `title` es un slot con nombre, también puede establecer el título a través de un atributo llamado `title`, por defecto a una cadena vacía, la parte `body` es el área principal de `Drawer`, con contenido definido por el usuario. Al abrir, `Drawer` se expande desde la **esquina derecha a la izquierda** cuyo tamaño es **30%** de la ventana del navegador por defecto. Puede cambiar ese comportamiento predeterminado estableciendo los atributos `direction` y `size`. Este caso de demostración también muestra cómo utilizar la API `before-close`, consulte la sección Atributos para obtener más detalles

drawer/basic-usage

:::

## Sin título

Cuando ya no necesite un título, puede eliminarlo del drawer.

:::demo Establezca el atributo `withHeader` a **false**, para eliminar el título del drawer, así puede tener más espacio en la pantalla. Si quiere ser accesible, asegúrese de establecer el atributo `title`.

drawer/no-title

:::

## Contenido personalizado

Al igual que `Dialog`, `Drawer` se puede utilizar para mostrar una multitud de interacciones diversas.

:::demo

drawer/customization-content

:::

## Cabecera personalizada

El slot `header` se puede utilizar para personalizar el área donde se muestra el título. Para mantener la accesibilidad, utilice el atributo `title` cuando use el slot, o utilice la propiedad `titleId` para especificar qué elemento debe ser leído como el título del diálogo.

:::demo

drawer/customization-header

:::

## Resizable Drawer ^(2.11.0)

Try to drag the edge part.

:::demo Set `resizable` to `true` to resize.

drawer/resizable

:::

## Drawer anidados

También puede tener varias capas de `Drawer` al igual que con `Dialog`.

:::demo Si necesita varios drawer en diferentes capas, debe establecer el atributo `append-to-body` en **true**

drawer/nested-drawer

:::

## Modal

Setting `modal` to `false` will hide modal (overlay) of drawer.

Starting from version ^(2.11.7), `modal-penetrable` attribute is added, which can be penetrable.

:::demo

drawer/modal

:::

:::tip

El contenido dentro del Drawer se renderiza de forma perezosa, lo que significa que el contenido dentro del Drawer no afectará al rendimiento inicial del renderizado, por lo que cualquier operación DOM debe realizarse a través de `ref` o después de que se emita el evento `open`.

:::

:::tip

Drawer provides an API called `destroy-on-close`, which is a flag variable that indicates should destroy the children content inside Drawer after Drawer was closed. Puede utilizar esta API en el ciclo de vida `mounted` del componente para que sea llamado cada vez que se abra el Drawer.

:::

## API

### Attributes

| Nombre                     | Descripción                                                                                                                                                                                                                                                                                                             | Tipo                                                                                                                                                                                                 | Default |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| model-value / v-model      | Si se muestra el Drawer                                                                                                                                                                                                                                                                                                 | ^[boolean]                                                                                                                                                                                           | false   |
| append-to-body             | Los controles deberían insertar Drawer en el elemento DocumentBody, los Drawer anidados deben asignar este parámetro a **true**                                                                                                                                                                                         | ^[boolean]                                                                                                                                                                                           | false   |
| append-to ^(2.8.0)         | which element the Drawer appends to. Will override `append-to-body`                                                                                                                                                                                                                                                     | ^[CSSSelector] / ^[HTMLElement]                                                                                                                                                                      | body    |
| lock-scroll                | si el scroll del cuerpo está desactivado mientras se muestra el drawer                                                                                                                                                                                                                                                  | ^[boolean]                                                                                                                                                                                           | true    |
| before-close               | Si se establece, se detendrá el procedimiento de cierre                                                                                                                                                                                                                                                                 | ^[Function]`(done: (cancel?: boolean) => void) => void(done is function type that accepts a boolean as parameter, calling done with true or without parameter will abort the close procedure)` | —       |
| close-on-click-modal       | si el drawer puede ser cerrado haciendo clic en la máscara                                                                                                                                                                                                                                                              | ^[boolean]                                                                                                                                                                                           | true    |
| close-on-press-escape      | Indica si el Drawer puede cerrarse pulsando ESC                                                                                                                                                                                                                                                                         | ^[boolean]                                                                                                                                                                                           | true    |
| open-delay                 | Tiempo en (milisegundos) antes de abrir el drawer                                                                                                                                                                                                                                                                       | ^[number]                                                                                                                                                                                            | 0       |
| close-delay                | Tiempo en (milisegundos) antes de cerrar el drawer                                                                                                                                                                                                                                                                      | ^[number]                                                                                                                                                                                            | 0       |
| destroy-on-close           | Indica si los children deben ser destruidos después de cerrar el Drawer                                                                                                                                                                                                                                                 | ^[boolean]                                                                                                                                                                                           | false   |
| modal                      | Mostrará una capa de sombra                                                                                                                                                                                                                                                                                             | ^[boolean]                                                                                                                                                                                           | true    |
| modal-penetrable ^(2.11.7) | whether the mask is penetrable. The modal attribute must be `false`.                                                                                                                                                                                                                                                    | ^[boolean]                                                                                                                                                                                           | false   |
| direction                  | Dirección de apertura del Drawer                                                                                                                                                                                                                                                                                        | ^[enum]`'rtl' \| 'ltr' \| 'ttb' \| 'btt'`                                                                                                                                                         | rtl     |
| resizable ^(2.11.0)        | enable resizable feature for Drawer                                                                                                                                                                                                                                                                                     | ^[boolean]                                                                                                                                                                                           | false   |
| show-close                 | Se mostrará el botón de cerrar en la parte superior derecha del Drawer                                                                                                                                                                                                                                                  | ^[boolean]                                                                                                                                                                                           | true    |
| size                       | Si el Drawer está en modo horizontal, afecta a la propiedad width, de lo contrario afecta a la propiedad height, cuando el tamaño es tipo `number`, describe el tamaño por unidad de píxeles; cuando el tamaño es tipo `string`, se debe usar con notación `x%`, de lo contrario se interpretará como unidad de píxeles | ^[number] / ^[string]                                                                                                                                                                                | 30%     |
| title                      | El título del Drawer, también se puede establecer por slot con nombre, las descripciones detalladas se pueden encontrar en el formulario de slot                                                                                                                                                                        | ^[string]                                                                                                                                                                                            | —       |
| with-header                | Flag that controls the header section's existence, default to true, when withHeader set to false, both `title attribute` and `title slot` won't work                                                                                                                                                                    | ^[boolean]                                                                                                                                                                                           | true    |
| modal-class                | Nombre extra de clase para capa de sombra                                                                                                                                                                                                                                                                               | ^[string]                                                                                                                                                                                            | —       |
| header-class ^(2.9.3)      | custom class names for header wrapper                                                                                                                                                                                                                                                                                   | ^[string]                                                                                                                                                                                            | —       |
| body-class ^(2.9.3)        | custom class names for body wrapper                                                                                                                                                                                                                                                                                     | ^[string]                                                                                                                                                                                            | —       |
| footer-class ^(2.9.3)      | custom class names for footer wrapper                                                                                                                                                                                                                                                                                   | ^[string]                                                                                                                                                                                            | —       |
| z-index                    | establece z-index                                                                                                                                                                                                                                                                                                       | ^[number]                                                                                                                                                                                            | —       |
| header-aria-level ^(a11y)  | header's `aria-level` attribute                                                                                                                                                                                                                                                                                         | ^[string]                                                                                                                                                                                            | 2       |
| custom-class ^(deprecated) | Extra class names for Drawer                                                                                                                                                                                                                                                                                            | ^[string]                                                                                                                                                                                            | —       |

:::warning

`custom-class` es **deprecated** y **será **removido en ^(2.3.0), por favor utilice `class`.

:::

### Events

| Nombre                 | Descripción                                                          | Type                                                    |
| ---------------------- | -------------------------------------------------------------------- | ------------------------------------------------------- |
| open                   | Se dispara antes de que comience la animación de apertura del Drawer | ^[Function]`() => void`                              |
| opened                 | Se dispara cuando finaliza la animación de apertura del Drawer       | ^[Function]`() => void`                              |
| close                  | Se dispara antes de que comience la animación de cierre del Drawer   | ^[Function]`() => void`                              |
| closed                 | Se dispara después de que finalice la animación de cierre del Drawer | ^[Function]`() => void`                              |
| open-auto-focus        | triggers after Drawer opens and content focused                      | ^[Function]`() => void`                              |
| close-auto-focus       | triggers after Drawer closed and content focused                     | ^[Function]`() => void`                              |
| resize-start ^(2.11.8) | Triggered when resizing starts (when `resizable` is enabled)         | ^[Function]`(evt: MouseEvent, size: number) => void` |
| resize ^(2.11.8)       | Triggered while resizing (when `resizable` is enabled)               | ^[Function]`(evt: MouseEvent, size: number) => void` |
| resize-end ^(2.11.8)   | Triggered when resizing ends (when `resizable` is enabled)           | ^[Function]`(evt: MouseEvent, size: number) => void` |

### Slots

| Nombre              | Descripción                                                                                               |
| ------------------- | --------------------------------------------------------------------------------------------------------- |
| default             | El contenido del Drawer                                                                                   |
| header              | Contenido de la cabecera del diálogo. Reemplazar esto elimina el título, pero no elimina el botón cerrar. |
| footer              | El pie de página de la sección del Drawer                                                                 |
| title ^(deprecated) | Funciona igual que el slot header. Use el slot header en lugar de este slot.                              |

:::warning

`title` has been **deprecated**, and **will be** removed in ^(3.0.0), please use `header`.

:::

### Exposes

| Name        | Description                                               |
| ----------- | --------------------------------------------------------- |
| handleClose | Para cerrar Drawer, este método llamará a `before-close`. |
