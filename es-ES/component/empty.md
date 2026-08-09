---
title: Empty
lang: es-ES
---

# Empty

Sugerencias para estados vacíos.

## Uso básico

:::demo

empty/basic-usage

:::

## Imagen personalizada

Utilice la propiedad `image` para establecer la URL de la imagen.

:::demo

empty/custom-image

:::

## Tamaño de la imagen

Use la propiedad `image-size` para controlar el tamaño de la imagen.

:::demo

empty/image-size

:::

## Contenido personalizado de la parte inferior

Utilice el slot por defecto para insertar contenido en la parte inferior.

:::demo

empty/bottom-content

:::

## Estilos personalizados

Ahora puede establecer un estilo personalizado para el componente empty. Use el lenguaje `css/scss` para cambiar el color global o local. Establecemos algunas variables de color globales: `--el-empty-fill-color-0`, `--el-empty-fill-color-1`, `--el-empty-fill-color-2`, ......, `--el-empty-fill-color-9`. Usted puede hacer algo así: `:root { --el-empty-fill-color-0: red; --el-empty-fill-color-1: blue; }`. Pero normalmente, si quieres cambiar de estilo, necesitas cambiar todo el color, porque estos colores son una combinación.

### Variables por defecto

| Variable                | Color                 |
| ----------------------- | --------------------- |
| --el-empty-fill-color-0 | var(--el-color-white) |
| --el-empty-fill-color-1 | #fcfcfd               |
| --el-empty-fill-color-2 | #f8f9fb               |
| --el-empty-fill-color-3 | #f7f8fc               |
| --el-empty-fill-color-4 | #eeeff3               |
| --el-empty-fill-color-5 | #edeef2               |
| --el-empty-fill-color-6 | #e9ebef               |
| --el-empty-fill-color-7 | #e5e7e9               |
| --el-empty-fill-color-8 | #e0e3e9               |
| --el-empty-fill-color-9 | #d5d7de               |

## API

### Atributos

| Nombre      | Descripción                                         | Tipo      | Por defecto |
| ----------- | --------------------------------------------------- | --------- | ----------- |
| image       | URL de la imagen para el contenido vacío            | ^[string] | ''          |
| image-size  | tamaño (ancho) de la imagen para el contenido vacío | ^[number] | —           |
| description | descripción del contenido vacío                     | ^[string] | ''          |

### Slots

| Nombre      | Descripción                       |
| ----------- | --------------------------------- |
| default     | contenido como contenido inferior |
| image       | contenido como imagen             |
| description | contenido como descripción        |
