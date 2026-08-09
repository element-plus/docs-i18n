---
title: Image
lang: es-ES
---

# Image

Además de las características nativas de img, soporta la carga perezosa, marcador de posición personalizado y fallo de carga, etc.

## Uso básico

:::demo Indica cómo la imagen debe ser redimensionada para que se adapte a su contenedor por medio de `fit`, al igual que de forma nativa, [object-fit](https://developer.mozilla.org/es/docs/Web/Css/object-fit).

image/basic-usage

:::

## Placeholder

:::demo Personalice el placeholder del contenido mientras la imagen aún no ha sido cargada por medio de `slot = placeholder`

image/placeholder

:::

## Fallo de carga

:::demo Custom failed content when error occurs to image load by `slot = error` and `slot = viewer-error`.

image/load-failed

:::

## Carga perezosa

:::tip

La carga nativa `loading` ha sido soportada desde ^(2.2.3), puede usar `loading = "lazy"` para reemplazar `lazy = true`.

Si el navegador actual soporta carga perezosa nativa, la carga perezosa nativa se utilizará primero, de lo contrario se implementará a través de scroll.

:::

:::demo Use la carga perezosa por medio de `lazy = true`. La imagen se cargará hasta que se desplace a la vista cuando esté configurada. Puede indicar el contenedor de desplazamiento que añade el listener de desplazamiento a través del `scroll-container`. Si no está definido, será el contenedor padre más cercano cuya propiedad overflow es auto o scroll.

image/lazy-load

:::

## Vista previa de la imagen

:::demo permita una vista previa grande configurando la propiedad `previewSrcList`. Puede indicar la primera imagen previsualizada con `initial-index`. La posición inicial por defecto es 0.

image/image-preview

:::

## Manually Open Preview ^(2.9.4)

:::demo

image/manually-preview

:::

## Custom Toolbar ^(2.9.4)

:::demo Custom toolbar content by `toolbar` slot, starting from version ^(2.9.7), the slot has a new `setActiveItem` function, which can be switched according to the index.

image/custom-toolbar

:::

## Custom progress ^(2.9.4)

:::demo By setting the `show-progress` prop to control whether to display progress when previewing an image. After version ^(2.9.8), the progress content will be displayed as long as the `progress` slot is used.

image/custom-progress

:::

## API de imagen

### Image Attributes

| Nombre                 | Descripción                                                                                                                                                                                                | Tipo                                                                         | Por defecto |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ----------- |
| src                    | origen de la imagen, igual que nativa.                                                                                                                                                                     | ^[string]                                                                    | ''          |
| fit                    | indica cómo la imagen debe ser redimensionada para que se adapte a su contenedor por medio de `fit`, al igual que de forma nativa, [object-fit](https://developer.mozilla.org/es/docs/Web/CSS/object-fit). | ^[enum]`'' \| 'fill' \| 'contain' \| 'cover' \| 'none' \| 'scale-down'` | ''          |
| hide-on-click-modal    | al habilitar la vista previa, utilice esta bandera para controlar si al hacer clic en el fondo puede salir del modo de vista previa.                                                                       | ^[boolean]                                                                   | false       |
| loading ^(2.2.3)       | Indicates how the browser should load the image, same as [native](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-loading).                                                             | ^[enum]`'eager' \| 'lazy'`                                                  | —           |
| lazy                   | si se usara la carga perezosa.                                                                                                                                                                             | ^[boolean]                                                                   | false       |
| scroll-container       | the container to add scroll listener when using lazy load. By default, the container to add scroll listener when using lazy load.                                                                          | ^[string] / ^[object]`HTMLElement`                                           | —           |
| alt                    | atributo nativo `alt`.                                                                                                                                                                                     | ^[string]                                                                    | —           |
| referrerpolicy         | atributo nativo [referrerPolicy](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/referrerPolicy).                                                                                        | ^[string]                                                                    | —           |
| crossorigin            | native attribute [crossorigin](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/crossorigin).                                                                                                  | ^[enum]`'' \| 'anonymous' \| 'use-credentials'`                            | —           |
| preview-src-list       | permite vista previa de imágenes grandes.                                                                                                                                                                  | ^[array]`string[]`                                                           | []          |
| z-index                | establecer el z-index de la vista previa de la imagen.                                                                                                                                                     | ^[number]                                                                    | —           |
| initial-index          | índice de imagen de vista previa inicial, debe ser menor que la longitud de `url-list`.                                                                                                                    | ^[number]                                                                    | 0           |
| close-on-press-escape  | whether the image-viewer can be closed by pressing ESC.                                                                                                                                                    | ^[boolean]                                                                   | true        |
| preview-teleported     | si adjuntar la visualización previa al body. Un atributo anidado del elemento padre debe tener este atributo establecido en `true`.                                                                        | ^[boolean]                                                                   | false       |
| infinite               | whether the viewer preview is infinite.                                                                                                                                                                    | ^[boolean]                                                                   | true        |
| zoom-rate              | the zoom rate of the image viewer zoom event.                                                                                                                                                              | ^[number]                                                                    | 1.2         |
| scale ^(2.11.3)        | the preview image scale.                                                                                                                                                                                   | ^[number]                                                                    | 1           |
| min-scale ^(2.4.0)     | the min scale of the image viewer zoom event.                                                                                                                                                              | ^[number]                                                                    | 0.2         |
| max-scale ^(2.4.0)     | the max scale of the image viewer zoom event.                                                                                                                                                              | ^[number]                                                                    | 7           |
| show-progress ^(2.9.4) | whether to display the preview image progress content.                                                                                                                                                     | ^[boolean]                                                                   | false       |

### Image Events

| Nombre | Descripción                                                                                                      | Tipo                                    |
| ------ | ---------------------------------------------------------------------------------------------------------------- | --------------------------------------- |
| load   | igual que el load nativo.                                                                                        | ^[Function]`(e: Event) => void`      |
| error  | igual que el error nativo.                                                                                       | ^[Function]`(e: Event) => void`      |
| switch | se dispara cuando las imágenes cambian.                                                                          | ^[Function]`(index: number) => void` |
| close  | se dispara al hacer clic en el botón de cerrar o con `hide-on-click-modal` habilitado haciendo clic en el fondo. | ^[Function]`() => void`              |
| show   | trigger when the viewer displays                                                                                 | ^[Function]`() => void`              |

### Image Slots

| Nombre                                    | Descripción                                                           | Tipo |
| ----------------------------------------- | --------------------------------------------------------------------- | ---- |
| placeholder                               | contenido personalizado cuando la imagen no se ha cargado todavía.    | -    |
| error                                     | contenido personalizado cuando la carga de imagen falle.              | -    |
| [image viewer slots](#image-viewer-slots) | when you allow big image preview, image viewer slots all can be used. | -    |

### Image Exposes

| Nombre               | Descripción                     | Tipo                       |
| -------------------- | ------------------------------- | -------------------------- |
| showPreview ^(2.9.4) | manually open preview big image | ^[Function]`() => void` |

## API del visor de imágenes

### Image Viewer Attributes

| Nombre                 | Descripción                                                                                                               | Type                  | Por defecto |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------- | --------------------- | ----------- |
| url-list               | lista de enlaces de la vista previa.                                                                                      | ^[array]`string[]`    | []          |
| z-index                | z-index del fondo de la previsualización.                                                                                 | ^[number] / ^[string] | —           |
| initial-index          | índice de imagen de vista previa inicial, debe ser menor que la longitud de `url-list`.                                   | ^[number]             | 0           |
| infinite               | si la vista previa es infinita.                                                                                           | ^[boolean]            | true        |
| hide-on-click-modal    | si el usuario puede emitir un evento de cierre al hacer clic en el fondo.                                                 | ^[boolean]            | false       |
| teleported             | si añadir la imagen misma al body. Un atributo anidado del elemento padre debe tener este atributo establecido en `true`. | ^[boolean]            | false       |
| zoom-rate ^(2.2.27)    | the zoom rate of the image viewer zoom event.                                                                             | ^[number]             | 1.2         |
| scale ^(2.11.3)        | the preview image scale.                                                                                                  | ^[number]             | 1           |
| min-scale ^(2.4.0)     | the min scale of the image viewer zoom event.                                                                             | ^[number]             | 0.2         |
| max-scale ^(2.4.0)     | the max scale of the image viewer zoom event.                                                                             | ^[number]             | 7           |
| close-on-press-escape  | whether the image-viewer can be closed by pressing ESC.                                                                   | ^[boolean]            | true        |
| show-progress ^(2.9.4) | whether to display the preview image progress content                                                                     | ^[boolean]            | false       |

### Image Viewer Events

| Name             | Descripción                                                                                                      | Type                                    |
| ---------------- | ---------------------------------------------------------------------------------------------------------------- | --------------------------------------- |
| close            | se dispara al hacer clic en el botón de cerrar o con `hide-on-click-modal` habilitado haciendo clic en el fondo. | ^[Function]`() => void`              |
| error ^(2.11.3)  | igual que el error nativo.                                                                                       | ^[Function]`(e: Event) => void`      |
| switch           | se dispara cuando las imágenes cambian.                                                                          | ^[Function]`(index: number) => void` |
| rotate ^(2.3.13) | trigger when rotating images.                                                                                    | ^[Function]`(deg: number) => void`   |

### Image Viewer Slots

| Name                   | Description                                                            | Type                                                                                                                                                                                                                               |
| ---------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| viewer                 | custom content                                                         | -                                                                                                                                                                                                                                  |
| progress ^(2.9.4)      | custom progress content (Priority is higher than `show-progress` prop) | ^[object]`{ activeIndex: number, total: number }`                                                                                                                                                                                  |
| toolbar ^(2.9.4)       | custom toolbar content                                                 | ^[object]`{ actions: (action: ImageViewerAction, options?: ImageViewerActionOptions) => void, prev: () => void, next: () => void, reset: () => void, activeIndex: number, setActiveItem: (index: number) => void }` |
| viewer-error ^(2.11.3) | contenido personalizado cuando la carga de imagen falle.               | ^[object]`{ activeIndex: number, src: string }`                                                                                                                                                                                    |

### Image Viewer Exposes

| Nombre        | Descripción                | Tipo                                    |
| ------------- | -------------------------- | --------------------------------------- |
| setActiveItem | cambiar imagen manualmente | ^[Function]`(index: number) => void` |

## Type Declarations

<details>
  <summary>Mostrar declaraciones</summary>

```ts
type ImageViewerAction = 'zoomIn' | 'zoomOut' | 'clockwise' | 'anticlockwise'
type ImageViewerActionOptions = {
  enableTransition?: boolean
  zoomRate?: number
  rotateDeg?: number
}
```

</details>
