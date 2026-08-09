---
title: Page
lang: es-ES
---

# Encabezado de página

Si la ruta de la página es simple, se recomienda usar PageHeader en lugar de Breadcrumb.

## Ejemplo completo

:::demo

page-header/complete

:::

## Uso Básico

Encabezado de página estándar, para escenarios simples.

:::demo

page-header/basic

:::

## Icono personalizado

El icono por defecto puede no cumplir con su satisfacción, puede personalizar el icono configurando el atributo `icon` como en el ejemplo.

:::demo

page-header/custom-icon

:::

## Sin icono

Sometimes the page is just full of elements, and you might not want the icon to show up on the page, you can set the `icon` attribute to `""` to get rid of it.

:::demo

page-header/no-icon

:::

## Breadcrumbs

El encabezado de la página le permite añadir breadcrumbs para dar información de ruta a los usuarios por medio del slot `breadcrumb`.

:::demo

page-header/breadcrumb

:::

## Sección de operación adicional

El encabezado puede ser tan complicado como sea necesario, puede añadir secciones adicionales a la cabecera, para permitir interacciones enriquecidas.

:::demo

page-header/additional-sections

:::

## Contenido principal

A veces queremos que la cabecera se muestre con algún contenido correspondiente, puede usar el slot `defaut` para hacerlo.

:::demo

page-header/main-content

:::

## Anatomía

El componente está compuesto por estas partes

```vue
<template>
  <el-page-header>
    <!-- Line 1 -->
    <template #breadcrumb />
    <!-- Line 2 -->
    <template #icon />
    <template #title />
    <template #content />
    <template #extra />
    <!-- Lines after 2 -->
    <template #default />
  </el-page-header>
</template>
```

## API

### Atributos

| Nombre  | Descripción                                                                       | Tipo                     | Por defecto |
| ------- | --------------------------------------------------------------------------------- | ------------------------ | ----------- |
| icon    | componente de icono del encabezado de página                                      | ^[string] / ^[Component] | Back        |
| title   | título principal del encabezado de la página, por defecto es con a11y incorporada | ^[string]                | ''          |
| content | contenido del encabezado de la página                                             | ^[string]                | ''          |

### Eventos

| Nombre | Descripción                                       | Tipo                       |
| ------ | ------------------------------------------------- | -------------------------- |
| back   | se dispara cuando se hace clic en el lado derecho | ^[Function]`() => void` |

### Slots

| Nombre     | Descripción                 |
| ---------- | --------------------------- |
| icon       | contenido como icono        |
| title      | contenido como título       |
| content    | contenido                   |
| extra      | extra                       |
| breadcrumb | contenido como migas de pan |
| default    | contenido principal         |
