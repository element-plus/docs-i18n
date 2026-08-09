---
title: Development FAQ
lang: es-ES
---

# FAQ de desarrollo

Estos son los problemas que son fáciles de encontrar en el desarrollo.

## Si encuentras problemas relacionados con la dependencia

```shell
rm -rf node_modules
pnpm i
```

## Enlazar dependencias locales

```shell
# obtiene dist
pnpm build
cd dist/element-plus
# set cur element-plus to global `node_modules`
pnpm link --global
# para esm también necesita link element-plus para dist
pnpm link --global element-plus

# ir a tu proyecto, enlace a `element-plus`
cd your-project
pnpm link --global element-plus
```

> Más información vea [pnpm link](https://pnpm.io/cli/link).

## Temas

No deberíamos escribir comentarios chinos en archivos scss.

Generará la advertencia `@charset "UTF-8";` en el encabezado del archivo css cuando se construya con vite.

> Más información vea [#3219](https://github.com/element-plus/element-plus/issues/3219).
