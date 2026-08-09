---
title: Dark Mode
lang: es-ES
---

# Modo Oscuro ^(2.2.0)

Después de un largo tiempo, Element Plus soporta modo oscuro!

Extrajimos y unificamos todas las variables necesarias para hacer posible la implementación basada en variables CSS.

## ¿Cómo activarlo?

Puede crear un switch para cambiar la clase `dark` del Html.

> Si solo necesita el modo oscuro, solo tiene que añadir la clase `dark` al Html.

```html
<html class="dark">
  <head></head>
  <body></body>
</html>
```

> Si quiere alternarlo, le recomendamos [useDark | VueUse](https://vueuse.org/core/useDark/).

Entonces, puede activarlo rápidamente con una sola línea de código para importar CSS en su entrada.

```ts [main.ts]
// if you just want to import css
import 'element-plus/theme-chalk/dark/css-vars.css'
```

> Si quiere un ejemplo, puede referirse a [element-plus-vite-starter](https://github.com/element-plus/element-plus-vite-starter).

## Variables personalizadas

### Por CSS

Solo sobrescriba las variables CSS.

Por ejemplo, nuevo archivo `styles/dark/css-vars.css`:

```css
html.dark {
  /* custom dark bg color */
  --el-bg-color: #626aef;
}
```

Impórtelo después de los estilos de Element Plus:

```ts [main.ts]
import 'element-plus/theme-chalk/dark/css-vars.css'
import './styles/dark/css-vars.css'
```

### Por SCSS

Si utiliza scss, también puede importar el archivo scss para compilar.

> Puedes referirse a [Tema](./theming.md) para obtener más información.

```scss [styles/element/index.scss]
/*just override what you need*/
@forward 'element-plus/theme-chalk/src/dark/var.scss' with (
  $bg-color: (
    'page': #0a0a0a,
    '': #626aef,
    'overlay': #1d1e1f,
  )
);
```

```ts [main.ts]
import './styles/element/index.scss'

// or just want to import scss?
// import 'element-plus/theme-chalk/src/dark/css-vars.scss'
```
