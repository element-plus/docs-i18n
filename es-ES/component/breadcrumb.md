---
title: Breadcrumb
lang: es-ES
---

# Breadcrumb

Muestra la ubicación de la página actual, facilitando la navegación hacia atrás.

## Uso básico

:::demo En `el-breadcrumb`, cada `el-breadcrumb-item` es una etiqueta que significa cada nivel comenzando desde la página principal. Este componente tiene un atributo `String` llamado `separator` y que determina el carácter separador. El valor por defecto es '/'.

breadcrumb/basic

:::

## Icono separador

:::demo Asigne al `separator-icon` uno de los valores de `svg icon` como separador，este se usara en lugar del valor de `separator`

breadcrumb/icon

:::

## Breadcrumb API

### Breadcrumb Attributes

| Nombre         | Descripción                             | Tipo                     | Por defecto |
| -------------- | --------------------------------------- | ------------------------ | ----------- |
| separator      | carácter separador                      | ^[string]                | /           |
| separator-icon | componente de icono del icono separador | ^[string] / ^[Component] | —           |

### Breadcrumb Slots

| Nombre  | Descripción                          | Subtags         |
| ------- | ------------------------------------ | --------------- |
| default | personaliza el contenido por defecto | Breadcrumb Item |

## BreadcrumbItem API

### BreadcrumbItem Attributes

| Nombre  | Descripción                                                    | Tipo                                    | Por defecto |
| ------- | -------------------------------------------------------------- | --------------------------------------- | ----------- |
| to      | ruta del link, lo mismo que `to` de `vue-router`               | ^[string] / ^[object]`RouteLocationRaw` | ''          |
| replace | si es `true`, la navegación no dejará un registro de historial | ^[boolean]                              | false       |

### BreadcrumbItem Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |
