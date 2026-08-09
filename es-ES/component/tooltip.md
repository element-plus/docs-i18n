---
title: Tooltip
lang: es-ES
---

# Tooltip

Mostrar aviso de información con el hover del mouse.

## Uso básico

Tooltip tiene 9 colocaciones.

:::demo Use el atributo `content` para establecer el contenido que se mostrará al hacer hover. El atributo `placement` determina la posición del tooltip. Su valor es `[orientation]-[alignment]` con cuatro orientaciones `top`, `left`, `right`, `bottom` y tres alineaciones `start`, `end`, `null`, la alineación default es null. Tome `placement="left-end"` como ejemplo, Tooltip será mostrado en la izquierda del elemento en que se esté haciendo hover y el fondo del tooltip se alineará con el fondo del elemento.

tooltip/basic

:::

## Temas

Tooltip tiene dos temas: `dark` y `light`.

:::tip

Para utilizar un tema personalizado, tendrá que saber en dónde se renderiza la información, si el tooltip se procesa en el elemento raíz necesitará establecer la regla css globalmente.

Se recomienda que no utilice degradado lineal para el color de fondo cuando use el tema personalizado y que muestre la flecha al mismo tiempo, porque la flecha emergente y el contenido son dos elementos diferentes, el estilo de la flecha emergente debe establecerse individualmente, y cuando se trata del color de fondo con degradado, puede parecer un poco raro.

:::

:::demo Use `effect` para modificar el tema, el valor por defecto es `dark`.

tooltip/theme

:::

## Más Contenido

Desplegar múltiples líneas de texto y establecer su formato.

:::demo Sobrescriba el atributo `content` del `el-tooltip` añadiendo un slot llamado `content`.

tooltip/rich-content

:::

## Uso Avanzado

Además de los usos básicos, hay algunos atributos que le permiten personalización:

el atributo `transition` permite personalizar la animación con la que el Tooltip se muestra o se esconde, el valor por defecto es el-fade-in-linear.

el atributo `disabled` permite deshabilitar el `tooltip`. Solo es necesario definirlo como `true`.

De hecho, Tooltip es una extensión basada en [ElPopper](https://github.com/element-plus/element-plus/tree/dev/packages/components/popper), puede usar cualquier atributo permitido en ElPopper.

:::demo

tooltip/advanced-usage

:::

:::tip

El componente `router-link` no está soportado en tooltip, por favor use `vm.$router.push`.

Los elementos de formulario deshabilitados no son compatibles con Tooltip, se puede encontrar más información en [MDN](https://developer.mozilla.org/en-US/docs/Web/Events/mouseenter). Necesita envolver el elemento del formulario deshabilitado con un elemento contenedor para que la Tooltip funcione.

:::

## Contenido HTML

El atributo de contenido puede establecerse a cadena HTML.

:::warning

Aunque la propiedad `content` soporta cadenas HTML, renderizar HTML arbitrario en su sitio web puede ser muy peligroso porque puede llevar fácilmente a [ataques XSS](https://en.wikipedia.org/wiki/Cross-site_scripting). Así que cuando `raw-content` está usándose, por favor asegúrese de que él `content` es de confianza, y **nunca** asigne a `content` contenido proporcionado por el usuario.

:::

:::demo

tooltip/html-content

:::

## Activación virtual

A veces queremos renderizar la descripción en algún otro elemento disparador, podemos separar el disparador y el contenido.

:::tip

El tooltip de activación virtual es un componente controlado, por lo que tendrá que controlar la visibilidad de la información por su cuenta, cuando esto suceda, **NO PODRÁ** cerrar el tooltip haciendo clic en otro lugar.

:::

:::demo

tooltip/virtual-trigger

:::

## Singleton

La descripción también puede ser singleton, lo que significa que puede tener múltiples disparadores con una sola instancia de tooltip, esta función está implementada con base en `Virtual triggering`

:::tip

Problema conocido: al usar singleton, la ventana emergente saldrá en lugares inesperados

:::

:::demo

tooltip/singleton

:::

## Control

La descripción puede ser controlada por el componente padre, usando `:visible` puede implementar la vinculación de dos vías.

:::demo

tooltip/controlled

:::

## Animaciones

Tooltip can be customized animated, you can set the desired animation use `transition`.

:::tip

Transition Classes, more information can be found at [Vue Transition](https://vuejs.org/guide/built-ins/transition.html#css-based-transitions).

:::

:::demo

tooltip/animations

:::

## Use the `append-to`

You must wait for the DOM to be mounted before using `targetElement`.

:::demo

tooltip/append-to

:::

## API

### Atributos

| Nombre                    | Descripción                                                                                                                                                                           | Tipo                                                                                                                                                                                   | Por defecto       |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| append-to                 | Which element the tooltip CONTENT appends to                                                                                                                                          | ^[CSSSelector] / ^[HTMLElement]                                                                                                                                                        | —                 |
| effect                    | Popover tiene dos temas: `dark` y `light`                                                                                                                                             | ^[enum]`'dark' \| 'light'`                                                                                                                                                            | dark              |
| content                   | Display content, can be overridden by `slot#content`                                                                                                                                  | ^[string]                                                                                                                                                                              | ''                |
| raw-content               | Whether `content` is treated as HTML string                                                                                                                                           | ^[boolean]                                                                                                                                                                             | false             |
| placement                 | Position of Tooltip                                                                                                                                                                   | ^[enum]`'top' \| 'top-start' \| 'top-end' \| 'bottom' \| 'bottom-start' \| 'bottom-end' \| 'left' \| 'left-start' \| 'left-end' \| 'right' \| 'right-start' \| 'right-end'` | bottom            |
| fallback-placements       | List of possible positions for Tooltip [popper.js](https://popper.js.org/docs/v2/modifiers/flip/#fallbackplacements)                                                                  | ^[array]`Placement[]`                                                                                                                                                                  | —                 |
| visible / v-model:visible | Visibility of Tooltip                                                                                                                                                                 | ^[boolean]                                                                                                                                                                             | —                 |
| disabled                  | Whether Tooltip is disabled                                                                                                                                                           | ^[boolean]                                                                                                                                                                             | —                 |
| offset                    | Offset of the Tooltip                                                                                                                                                                 | ^[number]                                                                                                                                                                              | 12                |
| transition                | Animation name                                                                                                                                                                        | ^[string]                                                                                                                                                                              | —                 |
| popper-options            | [parámetros popper.js](https://popper.js.org/docs/v2/)                                                                                                                                | ^[object]refer to [popper.js](https://popper.js.org/docs/v2/) doc                                                                                                                      | {}                |
| arrow-offset ^(2.9.10)    | Controls the offset (padding) of the tooltip’s arrow relative to the popper.                                                                                                          | ^[number]                                                                                                                                                                              | 5                 |
| show-after                | Delay of appearance, in millisecond, not valid in controlled mode                                                                                                                     | ^[number]                                                                                                                                                                              | 0                 |
| show-arrow                | Whether the tooltip content has an arrow                                                                                                                                              | ^[boolean]                                                                                                                                                                             | true              |
| hide-after                | Delay of disappear, in millisecond, not valid in controlled mode                                                                                                                      | ^[number]                                                                                                                                                                              | 200               |
| auto-close                | Timeout in milliseconds to hide tooltip, not valid in controlled mode                                                                                                                 | ^[number]                                                                                                                                                                              | 0                 |
| popper-class              | Custom class name for Tooltip's popper                                                                                                                                                | ^[string]                                                                                                                                                                              | —                 |
| popper-style              | Custom style for Tooltip's popper                                                                                                                                                     | ^[string] / ^[object]                                                                                                                                                                  | —                 |
| enterable                 | Whether the mouse can enter the tooltip                                                                                                                                               | ^[boolean]                                                                                                                                                                             | true              |
| teleported                | Whether tooltip content is teleported, if `true` it will be teleported to where `append-to` sets                                                                                      | ^[boolean]                                                                                                                                                                             | true              |
| trigger                   | How should the tooltip be triggered (to show), not valid in controlled mode                                                                                                           | ^[enum]`'hover' \| 'click' \| 'focus' \| 'contextmenu'` / ^[array]`Array<'click' \| 'focus' \| 'hover' \| 'contextmenu'>`                                                  | hover             |
| virtual-triggering        | Indica si la activación virtual está habilitada                                                                                                                                       | ^[boolean]                                                                                                                                                                             | —                 |
| virtual-ref               | Indica el elemento de referencia al que se adjunta el tooltip                                                                                                                         | ^[HTMLElement]                                                                                                                                                                         | —                 |
| trigger-keys              | When you click the mouse to focus on the trigger element, you can define a set of keyboard codes to control the display of tooltip through the keyboard, not valid in controlled mode | ^[Array]                                                                                                                                                                               | ['Enter','Space'] |
| persistent                | When tooltip inactive and `persistent` is `false` , tooltip will be destroyed                                                                                                         | ^[boolean]                                                                                                                                                                             | —                 |
| aria-label ^(a11y)        | Same as `aria-label`                                                                                                                                                                  | ^[string]                                                                                                                                                                              | —                 |
| focus-on-target ^(2.11.2) | When triggering tooltips through hover, whether to focus the trigger element, which improves accessibility                                                                            | ^[boolean]                                                                                                                                                                             | false             |

### Eventos

| Nombre      | Descripción                                                           | Tipo                                    |
| ----------- | --------------------------------------------------------------------- | --------------------------------------- |
| before-show | Triggers before tooltip is shown. Passes trigger reason as argument.  | ^[Function]`(event?: Event) => void` |
| show        | Triggers when tooltip is shown. Passes trigger reason as argument.    | ^[Function]`(event?: Event) => void` |
| before-hide | Triggers before tooltip is hidden. Passes trigger reason as argument. | ^[Function]`(event?: Event) => void` |
| hide        | Triggers when tooltip is hidden. Passes trigger reason as argument.   | ^[Function]`(event?: Event) => void` |

### Slots

| Nombre  | Descripción                                                                    |
| ------- | ------------------------------------------------------------------------------ |
| default | Tooltip triggering & reference element, only a single root element is accepted |
| content | Customize content                                                              |

### Expuesto

| Nombre               | Descrición                                                        | Tipo                                                       |
| -------------------- | ----------------------------------------------------------------- | ---------------------------------------------------------- |
| popperRef            | instancia del componente el-popper                                | ^[object]`Ref<PopperInstance \| undefined>`         |
| contentRef           | instancia del componente el-tooltip-content                       | ^[object]`Ref<TooltipContentInstance \| undefined>` |
| isFocusInsideContent | Validate current focus event is trigger inside el-tooltip-content | ^[Function]`() => boolean \| undefined`                |
| updatePopper         | Update el-popper component instance                               | ^[Function]`() => void`                                 |
| onOpen               | Expose onOpen function to manage el-tooltip open state            | ^[Function]`(event?: Event \| undefined) => void`      |
| onClose              | Expose onClose function to manage el-tooltip open state           | ^[Function]`(event?: Event \| undefined) => void`      |
| hide                 | Expose hide function                                              | ^[Function]`(event?: Event \| undefined) => void`      |

## FAQ

#### How to allow spaces in the input box when tooltip is nested?

Typical issue: [#20907](https://github.com/element-plus/element-plus/issues/20907)

```vue
<template>
  <el-tooltip content="tooltip content" placement="top" :trigger-keys="[]">
    <el-input v-model="value" placeholder="" />
  </el-tooltip>
</template>
```
