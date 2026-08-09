---
title: Loading
lang: es-ES
---

# Loading

Se muestra una animación mientras se cargan los datos.

## Cargando dentro de un contenedor

Muestra una animación en un contenedor (como en una tabla) mientras se cargan los datos.

:::demo Element Plus provee dos maneras para invocar el componente de Loading: por directiva y por servicio. Para la directiva personalizada `v-loading`, solo necesitas enlazarlo a un valor `boolean`. Por defecto, la máscara de carga se agregará al elemento donde se usa la directiva. Al agregar el modificador `body`, la máscara se agrega al elemento body.

loading/basic

:::

## Personalización

Puede personalizar el texto de carga, spinner de carga y color de fondo.

:::demo Agregue el atributo `element-loading-text` al elemento en el que `v-loading` está vinculado, y su valor se mostrará debajo del spinner. De manera similar, los atributos `element-loading-spinner / element-loading-svg` y `element-loading-background` se utilizan para establecer el spinner de carga y el color de fondo, respectivamente.

loading/customization

:::

:::warning

Aunque los atributos `element-loading / element-loading-svg` admiten fragmentos HTML entrantes, es muy peligroso representar dinámicamente HTML arbitrario en el sitio web porque es fácil causar [ataques XSS](https://en.wikipedia.org/wiki/Cross-site_scripting). Por favor, asegúrese de que el contenido de `element-loading-spinner / element-loading-svg` es de confianza. **Nunca** asigne contenido enviado por el usuario a los atributos `element-loading-spinner / element-loading-svg`.

:::

## Cargando a pantalla completa

Muestra una animación de pantalla completa mientras se cargan los datos.

:::demo Cuando se utiliza como una directiva, la carga a pantalla completa requiere el modificador `fullscreen`, y este puede ser agregado al body. En este caso, si desea deshabilitar el desplazamiento en body, puede agregar otro modificador `lock`. Cuando se utiliza como un servicio, el componente puede ser mostrado a pantalla completa por defecto.

loading/fullscreen

:::

## Servicio

Puede invocar el componente como un servicio. Importe el servicio:

```ts
import { ElLoading } from 'element-plus'
```

Invocarlo:

```ts
ElLoading.service(options)
```

El parámetro `options` es la configuración del componente, y estos detalles pueden ser encontrados en la siguiente tabla. `LoadingService` devuelve una instancia del componente, y puede cerrarlo invocando el método `close`:

```ts
const loadingInstance = ElLoading.service(options)
nextTick(() => {
  // Loading should be closed asynchronously
  loadingInstance.close()
})
```

Tenga en cuenta que, en este caso, el componente a pantalla completa es una instancia única. Si un nuevo componente de pantalla completa es invocado antes de que se cierre la existente, se devolverá la instancia existente en lugar de crear la otra instancia:

```ts
const loadingInstance1 = ElLoading.service({ fullscreen: true })
const loadingInstance2 = ElLoading.service({ fullscreen: true })
console.log(loadingInstance1 === loadingInstance2) // true
```

Llamar al método `close` en cualquiera de ellas puede cerrarlo.

Si Element Plus es importado completamente, un método global `$loading` puede ser registrado en `app.config.globalProperties`. Puede invocarlo como esto: `this.$loading(options)`, y también devuelve una instancia del componente.

## App context inheritance ^(2.9.10)

Now loading accepts a `context` as second parameter of the loading constructor which allows you to inject current app's context to loading which allows you to inherit all the properties of the app.

You can use it like this:

:::tip

If you globally registered ElLoading component, it will automatically inherit your app context.

:::

```ts
import { getCurrentInstance } from 'vue'
import { ElLoading } from 'element-plus'

// in your setup method
const { appContext } = getCurrentInstance()!
ElLoading.service({}, appContext)
```

## API

### Opciones

| Nombre               | Descripción                                                                                                                                                                                        | Tipo                                     | Por defecto   |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------- | ------------- |
| target               | el nodo del DOM que el componente debe cubrir. Acepta un objecto DOM o una cadena. Si está es una cadena, este será pasado a `document.querySelector` para obtener el correspondiente nodo del DOM | ^[string] / ^[HTMLElement]               | document.body |
| body                 | igual que el modificador `body` de `v-loading`                                                                                                                                                     | ^[boolean]                               | false         |
| fullscreen           | igual que el modificador `fullscreen` de `v-loading`                                                                                                                                               | ^[boolean]                               | true          |
| lock                 | igual que el modificador `lock` de `v-loading`                                                                                                                                                     | ^[boolean]                               | false         |
| text                 | texto de carga que se muestra debajo del spinner                                                                                                                                                   | ^[string] / ^[VNode] / ^[array]`VNode[]` | —             |
| spinner              | nombre de clase del spinner personalizado                                                                                                                                                          | ^[string]                                | —             |
| background           | color de fondo de la máscara                                                                                                                                                                       | ^[string]                                | —             |
| customClass          | custom class name for loading                                                                                                                                                                      | ^[string]                                | —             |
| svg                  | custom SVG element to override the default loading spinner                                                                                                                                         | ^[string]                                | —             |
| svgViewBox           | sets the viewBox attribute for loading svg element                                                                                                                                                 | ^[string]                                | —             |
| beforeClose ^(2.7.8) | Function executed before loading attempts to close. If this function returns false, the closing process will be aborted. Otherwise, the loading will close.                                        | ^[Function]`() => boolean`            | —             |
| closed ^(2.7.8)      | Function triggered after loading has completely closed                                                                                                                                             | ^[Function]`() => void`               | —             |

### Directivas

| Nombre                       | Descripción                                                         | Tipo                           |
| ---------------------------- | ------------------------------------------------------------------- | ------------------------------ |
| v-loading                    | se muestra una animación mientras se cargan los datos               | ^[boolean] / ^[LoadingOptions] |
| element-loading-text         | texto de carga que se muestra debajo del spinner                    | ^[string]                      |
| element-loading-spinner      | icono del spinner personalizado                                     | ^[string]                      |
| element-loading-svg          | icono del spinner personalizado (igual que element-loading-spinner) | ^[string]                      |
| element-loading-svg-view-box | sets the viewBox attribute for loading svg element                  | ^[string]                      |
| element-loading-background   | color de fondo de la máscara                                        | ^[string]                      |
| element-loading-custom-class | custom class name for loading                                       | ^[string]                      |
