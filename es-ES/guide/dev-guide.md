---
title: Local Development
lang: es-ES
---

# Desarrollo local

## Inicio del proyecto

Con el comando

```shell
pnpm i
```

el proyecto instalará todas las dependencias.

## Vista previa del sitio web

Con el comando

```shell
pnpm docs:dev
```

el proyecto lanzará el sitio web para que usted previsualice todos los componentes existentes.

## Desarrollo local

Ver [Guía de desarrollo local](https://github.com/element-plus/element-plus/blob/dev/CONTRIBUTING.md)

1. Con el comando

```shell
pnpm dev
```

iniciará el entorno de desarrollo local.

2. Añade tu componente a `play/src/App.vue`

```vue [App.vue]
<template>
  <ComponentYouAreDeveloping />
</template>

<script setup lang="ts">
// make sure this component is registered in @element-plus/components
</script>
```

Modifique el archivo `App.vue` para que las cosas funcionen.

## The following commands are also useful during development

### Generate component template

Con el comando

```shell
pnpm gen <component-name>
# eg.
pnpm gen awesome
pnpm gen awesome-button
```

will generate a component template in `packages/components/awesome` and `packages/components/awesome-button` directory.

### Sync locale files

Con el comando

```shell
pnpm locale:sync
```

will sync the new fields from the `en.ts` locale file to other locale files and add the comment `// to be translated`.
