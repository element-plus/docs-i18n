---
title: Upload
lang: es-ES
---

# Carga de archivos

Suba archivos haciendo clic o arrastrando y soltando.

## Uso básico

:::demo Personalice el tipo y texto del botón utilizando el `slot`. Defina las propiedades `limit` y `on-exceed` para limitar el número máximo de archivos a subir y especifique un método para cuando el límite ha sido excedido. Además, puede abortar el proceso de quitar un archivo con el gancho `before-remove`.

upload/basic

:::

## Carátula anterior

:::demo Establezca `límit` y `on-exceed` para reemplazar automáticamente el archivo anterior cuando seleccione un nuevo archivo.

upload/limit-cover

:::

## Avatar de usuario

Utilice el _hook_ `before-upload` para limitar el formato de archivo y su tamaño.

:::demo

upload/avatar

:::

## Pared de fotografías

Utilice la propiedad `list-type` para cambiar el estilo a un listado de archivos.

:::demo

upload/photo-wall

:::

## Miniaturas personalizadas

Use `scoped-slot` para cambiar la plantilla de miniatura predeterminada.

:::demo

upload/custom-thumbnail

:::

## Lista de archivos con miniatura

:::demo

upload/file-list-with-thumbnail

:::

## Control de lista de archivos

Use la función gancho `on-change` para controlar la lista de archivos subidos.

:::demo

upload/file-list

:::

## Arrastrar para cargar archivo

Puede arrastrar el archivo dentro de un área en especifico para cargar el archivo.

:::demo

upload/drag-and-drop

:::

## Upload Directory ^(2.13.1)

Enable folder upload via the `directory` prop.

:::demo After enabling it, only folders can be selected, and after selecting a folder, the files within the folder will be flattened.

upload/directory

:::

## Solo subida manual

:::demo

upload/manual

:::

## API

### Atributos

| Nombre                        | Descripción                                                                                                                                                                                                   | Tipo                                                                                                                                                                         | Por defecto                                                                                                        |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| action ^(required)            | URL de solicitud.                                                                                                                                                                                             | ^[string]                                                                                                                                                                    | #                                                                                                                  |
| headers                       | cabeceras de la petición.                                                                                                                                                                                     | ^[object]`Headers \| Record<string, any>`                                                                                                                             | —                                                                                                                  |
| method                        | establecer método de solicitud de subida.                                                                                                                                                                     | ^[string]                                                                                                                                                                    | post                                                                                                               |
| multiple                      | si se permite subir varios archivos.                                                                                                                                                                          | ^[boolean]                                                                                                                                                                   | false                                                                                                              |
| data                          | additions options of request. support `Awaitable` data and `Function` since v2.3.13.                                                                                                                          | ^[object]`Record<string, any> \| Awaitable<Record<string, any>>` / ^[Function]`(rawFile: UploadRawFile) => Awaitable<Record<string, any>>` | {}                                                                                                                 |
| name                          | nombre de clave para el archivo subido.                                                                                                                                                                       | ^[string]                                                                                                                                                                    | file                                                                                                               |
| with-credentials              | si se envían cookies.                                                                                                                                                                                         | ^[boolean]                                                                                                                                                                   | false                                                                                                              |
| show-file-list                | si desea mostrar la lista de archivos subidos.                                                                                                                                                                | ^[boolean]                                                                                                                                                                   | true                                                                                                               |
| drag                          | si activar el modo de arrastrar y soltar.                                                                                                                                                                     | ^[boolean]                                                                                                                                                                   | false                                                                                                              |
| accept                        | acepta [tipos de archivos](https://developer.mozilla.org/es/docs/Web/HTML/Element/input#attr-accept), puede no funcionar cuando `thumbnail-mode === true`.                                                    | ^[string]                                                                                                                                                                    | ''                                                                                                                 |
| crossorigin                   | native attribute [crossorigin](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/crossorigin).                                                                                                     | ^[enum]`'' \| 'anonymous' \| 'use-credentials'`                                                                                                                            | —                                                                                                                  |
| on-preview                    | función gancho al hacer clic en los archivos subidos.                                                                                                                                                         | ^[Function]`(uploadFile: UploadFile) => void`                                                                                                                             | —                                                                                                                  |
| on-remove                     | función gancho cuando se eliminan los archivos.                                                                                                                                                               | ^[Function]`(uploadFile: UploadFile, uploadFiles: UploadFiles) => void`                                                                                                   | —                                                                                                                  |
| on-success                    | función gancho cuando se sube con éxito.                                                                                                                                                                      | ^[Function]`(response: any, uploadFile: UploadFile, uploadFiles: UploadFiles) => void`                                                                                    | —                                                                                                                  |
| on-error                      | función gancho cuando se producen algunos errores.                                                                                                                                                            | ^[Function]`(error: Error, uploadFile: UploadFile, uploadFiles: UploadFiles) => void`                                                                                     | —                                                                                                                  |
| on-progress                   | función gancho cuando se produce algún progreso.                                                                                                                                                              | ^[Function]`(evt: UploadProgressEvent, uploadFile: UploadFile, uploadFiles: UploadFiles) => void`                                                                         | —                                                                                                                  |
| on-change                     | función gancho al seleccionar archivo o subir archivo con éxito o cargar archivo falla.                                                                                                                       | ^[Function]`(uploadFile: UploadFile, uploadFiles: UploadFiles) => void`                                                                                                   | —                                                                                                                  |
| on-exceed                     | función gancho cuando se supera el límite.                                                                                                                                                                    | ^[Function]`(files: File[], uploadFiles: UploadUserFile[]) => void`                                                                                                       | —                                                                                                                  |
| before-upload                 | función gancho anterior a subir el archivo ese archivo subido será el parámetro. Si se devuelve `falso` o se devuelve una `Promise` y luego se rechaza, la subida se cancelará.                               | ^[Function]`(rawFile: UploadRawFile) => Awaitable<void \| undefined \| null \| boolean \| File \| Blob>`                                                       | —                                                                                                                  |
| before-remove                 | _hook_ lanzado antes de eliminar un archivo. Los parámetros son el archivo y la lista de archivos. Si se devuelve `false` o se devuelve una `Promise` y que luego es rechazada, la eliminación será abortada. | ^[Function]`(uploadFile: UploadFile, uploadFiles: UploadFiles) => Awaitable<boolean>`                                                                               | —                                                                                                                  |
| file-list / v-model:file-list | archivos subidos por defecto.                                                                                                                                                                                 | ^[array]`UploadUserFile[]`                                                                                                                                                   | []                                                                                                                 |
| list-type                     | tipo de lista de archivos.                                                                                                                                                                                    | ^[enum]`'text' \| 'picture' \| 'picture-card'`                                                                                                                             | text                                                                                                               |
| auto-upload                   | si desea cargar el archivo automáticamente.                                                                                                                                                                   | ^[boolean]                                                                                                                                                                   | true                                                                                                               |
| http-request                  | sobrescribe el comportamiento por defecto de xhr, permitiendo implementar su propia petición de carga de archivos.                                                                                            | ^[Function]`(options: UploadRequestOptions) => XMLHttpRequest \| Promise<unknown>`                                                                                 | ajaxUpload [see](https://github.com/element-plus/element-plus/blob/dev/packages/components/upload/src/ajax.ts#L55) |
| disabled                      | si desea desactivar el upload.                                                                                                                                                                                | ^[boolean]                                                                                                                                                                   | false                                                                                                              |
| limit                         | número máximo de subidas permitidas.                                                                                                                                                                          | ^[number]                                                                                                                                                                    | —                                                                                                                  |
| directory ^(2.13.1)           | whether to support uploading directory. After enabling it, only folders can be selected, and after selecting a folder, the files within the folder will be flattened.                                         | ^[boolean]                                                                                                                                                                   | false                                                                                                              |

### Slots

| Nombre  | Descripción                                  | Tipo                                           |
| ------- | -------------------------------------------- | ---------------------------------------------- |
| default | personaliza el contenido por defecto.        | -                                              |
| trigger | contenido que activa el diálogo de archivos. | -                                              |
| tip     | contenido de los tips.                       | -                                              |
| file    | contenido de la plantilla en miniatura.      | ^[object]`{ file: UploadFile, index: number }` |

### Exposes

| Nombre       | Descripción                                                                                                                                             | Tipo                                                                                  |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| abort        | cancela la petición de carga. When a `file` is specified, abort the corresponding pending upload; when no file is specified, abort all pending uploads. | ^[Function]`(file?: UploadFile) => void`                                           |
| submit       | la lista de archivos se sube manualmente.                                                                                                               | ^[Function]`() => void`                                                            |
| clearFiles   | limpia la lista de archivos cargados (este método no está soportado en la función gancho `before-upload`).                                              | ^[Function]`(status?: UploadStatus[]) => void`                                     |
| handleStart  | selecciona el archivo manualmente.                                                                                                                      | ^[Function]`(rawFile: UploadRawFile) => void`                                      |
| handleRemove | elimina el archivo manualmente. `archivo` y `rawFile` han sido fusionados. `rawFile` se eliminará en `v2.2.0`.                                          | ^[Function]`(file: UploadFile \| UploadRawFile, rawFile?: UploadRawFile) => void` |

## Type Declarations

<details>
  <summary>Show declarations</summary>

```ts
type UploadFiles = UploadFile[]

type UploadUserFile = Omit<UploadFile, 'status' | 'uid'> &
  Partial<Pick<UploadFile, 'status' | 'uid'>>

type UploadStatus = 'ready' | 'uploading' | 'success' | 'fail'

type Awaitable<T> = Promise<T> | T

type Mutable<T> = { -readonly [P in keyof T]: T[P] }

interface UploadFile {
  name: string
  percentage?: number
  status: UploadStatus
  size?: number
  response?: unknown
  uid: number
  url?: string
  raw?: UploadRawFile
}

interface UploadProgressEvent extends ProgressEvent {
  percent: number
}

interface UploadRawFile extends File {
  uid: number
  isDirectory?: boolean
}

interface UploadRequestOptions {
  action: string
  method: string
  data: Record<string, string | Blob | [string | Blob, string] | string[]>
  filename: string
  file: UploadRawFile
  headers: Headers | Record<string, string | number | null | undefined>
  onError: (evt: UploadAjaxError) => void
  onProgress: (evt: UploadProgressEvent) => void
  onSuccess: (response: any) => void
  withCredentials: boolean
}
```

</details>
