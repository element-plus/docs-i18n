---
title: Link
lang: es-ES
---

# Link

Texto con hipervinculo

:::warning Security Warning The `href` prop will be rendered directly to an `<a>` tag. If you pass a value such as `javascript:alert(1)` or a malicious URL, it may cause **XSS** or **open redirect vulnerabilities**.

Always validate and sanitize the URL before use. For example:

<details>
<summary>Show code example</summary>

```js
function sanitizeUrl(url) {
  const allowedProtocols = ['http:', 'https:']
  try {
    const parsed = new URL(url, window.location.origin)
    return allowedProtocols.includes(parsed.protocol) ? parsed.href : '#'
  } catch {
    return '#'
  }
}
```

</details>

:::

## Básico

Enlace de texto básico

:::demo

link/basic

:::

## Deshabilitar

Deshabilita el hipervínculo

:::demo

link/disabled

:::

## Subrayado

Controlling when underlines should appear

:::warning

The `boolean` value has been **deprecated**, and **will be** removed in ^(3.0.0) , consider switching to new values.

:::

:::tip

Starting from ^(2.9.9) , you can use `'always' | 'hover' | 'never'` to control when underlines should appear. The examples in the document all use these values. If you are using a version **less than** ^(2.9.9) , please refer to:

:::

```vue
<template>
  <!-- works before 2.9.9, use 'hover' after, removed in 3.0.0 -->
  <el-link underline>link</el-link>
  <!-- works before 2.9.9, use 'never' after, removed in 3.0.0 -->
  <el-link :underline="false">link</el-link>
</template>
```

:::demo

link/underline

:::

## Icono

Enlace con icono

:::tip

Use el atributo `icon` para agregar un icono. Puede pasarle ya sea el nombre del componente (registrado de antemano) o el propio componente que es un componente SVG Vue. Element Plus has provided a set of icon that you can find at [icon](./icon.md)

:::

:::demo

link/with-icon

:::

## API

### Atributos

| Nombre    | Descripción                                          | Tipo                                                                                 | Por defecto |
| --------- | ---------------------------------------------------- | ------------------------------------------------------------------------------------ | ----------- |
| type      | tipo                                                 | ^[enum]`'primary' \| 'success' \| 'warning' \| 'danger' \| 'info' \| 'default'` | default     |
| underline | when underlines should appear                        | ^[enum]`'always' \| 'hover' \| 'never' \| boolean`                                | hover       |
| disabled  | si el componente está deshabilitado                  | ^[boolean]                                                                           | false       |
| href      | lo mismo que el valor nativo del hipervínculo `href` | ^[string]                                                                            | —           |
| target    | same as native hyperlink's `target`                  | ^[enum]`'_blank' \| '_parent' \| '_self' \| '_top'`                               | \_self    |
| icon      | componente de icono                                  | ^[string] / ^[Component]                                                             | —           |

### Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |
| icon    | personaliza el componente de icono   |
