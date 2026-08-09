---
title: Dropdown
lang: es-ES
---

# Dropdown

Menú conmutable para visualizar listas de enlaces y acciones.

## Uso básico

Pase el ratón por el menú para desplegarlo y obtener más acciones.

:::demo El elemento activado se renderiza por el `slot` predeterminado, y la parte desplegable se renderiza por el `slot` con nombre `dropdown`. Por defecto, la lista desplegable se muestra cuando se pasa el ratón por encima del elemento desencadenante sin necesidad de hacer clic en él.

dropdown/basic-usage

:::

## Placement

Support 6 placements.

:::demo Set `placement` property to make dropdown appear in different locations.

dropdown/placements

:::

## Elemento de activación

Utilizando un botón para activar la lista desplegable.

:::demo Utilice `split-button` para dividir el elemento detonante en un grupo de botones, siendo el botón izquierdo un botón normal y el botón derecho el objetivo real de la detonación. If you wanna insert a separator line between item three and item four, just add the `divided` attribute to item four.

dropdown/triggering-element

:::

## Cómo detonar el evento

Haga clic en el elemento de activación o pase el cursor sobre él.

:::demo Use el atributo `trigger`. Por defecto, es `hover`.

dropdown/how-to-trigger

:::

## Comportamiento de ocultación de menú

Use `hide-on-click` para definir si el menú se cierra al hacer clic.

:::demo El menú predeterminado se cerrará cuando haga clic en los elementos del menú, y se puede desactivar configurando `hide-on-click` como false.

dropdown/menu-hiding-behavior

:::

## Evento de comando

Al hacer clic en cada elemento desplegable se detona un evento cuyo parámetro es asignado por cada ítem.

:::demo

dropdown/command-event

:::

## Métodos desplegables

Puede abrir o cerrar el menú desplegable usando manualmente `handleOpen` o `handleClose`

:::demo

dropdown/dropdown-methods

:::

## Tamaños

Además del tamaño predeterminado, el componente Dropdown proporciona tres tamaños adicionales para que pueda elegir entre diferentes escenarios.

:::demo Use attribute `size` to set additional sizes with `large`, `default` or `small`.

dropdown/sizes

:::

## Virtual triggering ^(2.11.3)

Sometimes we want to render the dropdown on some other trigger element, we can separate the trigger and the content.

:::demo

dropdown/virtual-trigger

:::

## Dropdown API

### Dropdown Attributes

| Nombre                       | Descripción                                                                                                   | Tipo                                                                                                                | Default                                                                    |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| type                         | tipo de botón de menú, consulte el componente `Button`, solo funciona cuando `split-button` es true           | ^[enum]`'' \| 'default' \| 'primary' \| 'success' \| 'warning' \| 'info' \| 'danger' \| 'text' (deprecated)` | ''                                                                         |
| size                         | tamaño del menú, también funciona en split button                                                             | ^[enum]`'' \| 'large' \| 'default' \| 'small'`                                                                   | ''                                                                         |
| button-props                 | props for the button component, refer to [Button Attributes](./button.html#button-attributes)                 | ^[object]                                                                                                           | —                                                                          |
| max-height                   | la altura máxima del menú                                                                                     | ^[string] / ^[number]                                                                                               | ''                                                                         |
| split-button                 | si se visualiza un grupo de botones                                                                           | ^[boolean]                                                                                                          | false                                                                      |
| disabled                     | whether to disable                                                                                            | ^[boolean]                                                                                                          | false                                                                      |
| placement                    | posición del menú                                                                                             | ^[enum]`'top' \| 'top-start' \| 'top-end' \| 'bottom' \| 'bottom-start' \| 'bottom-end'`                       | bottom                                                                     |
| effect                       | Popover tiene dos temas: `dark` y `light`                                                                     | ^[enum]`'dark' \| 'light'` / ^[string]                                                                             | light                                                                      |
| trigger                      | cómo activar                                                                                                  | ^[enum]`'click' \| 'hover' \| 'contextmenu'` / ^[array]`Array<'click' \| 'hover' \| 'contextmenu'>`       | hover                                                                      |
| trigger-keys ^(2.9.1)        | specify which keys on the keyboard can trigger when pressed                                                   | ^[array]`string[]`                                                                                                  | `['Enter', 'Space', 'ArrowDown', 'NumpadEnter']`                           |
| virtual-triggering ^(2.11.3) | indicates whether virtual triggering is enabled                                                               | ^[boolean]                                                                                                          | —                                                                          |
| virtual-ref ^(2.11.3)        | indicates the reference element to which the dropdown is attached                                             | ^[HTMLElement]                                                                                                      | —                                                                          |
| hide-on-click                | si se oculta el menú después de hacer clic en el elemento                                                     | ^[boolean]                                                                                                          | true                                                                       |
| show-arrow ^(2.11.3)         | si el contenido de la descripción tiene una flecha                                                            | ^[boolean]                                                                                                          | true                                                                       |
| show-timeout                 | delay time before show a dropdown (only works when trigger is `hover`)                                        | ^[number]                                                                                                           | 150                                                                        |
| hide-timeout                 | delay time before hide a dropdown (only works when trigger is `hover`)                                        | ^[number]                                                                                                           | 150                                                                        |
| role                         | the ARIA role attribute for the dropdown menu. Dependiendo del caso de uso, puede cambiar esto a 'navigation' | ^[enum]`'dialog' \| 'grid' \| 'group' \| 'listbox' \| 'menu' \| 'navigation' \| 'tooltip' \| 'tree'`         | menu                                                                       |
| tabindex                     | [tabindex](https://developer.mozilla.org/es/docs/Web/HTML/Global_attributes/tabindex) de Dropdown             | ^[number] / ^[string]                                                                                               | 0                                                                          |
| popper-class                 | nombre de clase personalizado para la lista desplegable de Dropdown                                           | ^[string] / ^[object]                                                                                               | ''                                                                         |
| popper-style ^(2.11.5)       | custom style for Dropdown's dropdown                                                                          | ^[string] / ^[object]                                                                                               | —                                                                          |
| popper-options               | parámetros de [popper.js](https://popper.js.org/docs/v2/)                                                     | ^[object]                                                                                                           | `{modifiers: [{name: 'computeStyles',options: {gpuAcceleration: false}}]}` |
| teleported ^(2.2.20)         | si la ventana emergente se teletransporta al cuerpo                                                           | ^[boolean]                                                                                                          | true                                                                       |
| append-to ^(2.13.0)          | which element the dropdown CONTENT appends to                                                                 | ^[CSSSelector] / ^[HTMLElement]                                                                                     | —                                                                          |
| persistent ^(2.9.5)          | when dropdown inactive and `persistent` is `false` , dropdown menu will be destroyed                          | ^[boolean]                                                                                                          | true                                                                       |

### Dropdown Slots

| Nombre   | Descripción                                                                                                                                                       | Subtags       |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- |
| default  | contenido del Dropdown. Aviso: Debe ser un elemento Html Dom válido (ej. `<span>, <button> etc.`) o `el-component`, para adjuntar al listener trigger | —             |
| dropdown | contenido del menu Dropdown, normalmente es un elemento `<el-dropdown-menu>`                                                                                | Dropdown-Menu |

### Dropdown Events

| Nombre         | Descripción                                                                                               | Tipo                                     |
| -------------- | --------------------------------------------------------------------------------------------------------- | ---------------------------------------- |
| click          | si `split-button` es `true`, se activa al hacer clic con el botón izquierdo                               | ^[Function]`(e: MouseEvent) => void`  |
| command        | triggers when a dropdown item is clicked, the parameters is the command dispatched from the dropdown item | ^[Function]`(...args: any[]) => void` |
| visible-change | triggers when the dropdown appears/disappears, the param is true when it appears, and false otherwise     | ^[Function]`(val: boolean) => void`   |

### Dropdown Exposes

| Método      | Descripción                | Type                       |
| ----------- | -------------------------- | -------------------------- |
| handleOpen  | abre el menú desplegable   | ^[Function]`() => void` |
| handleClose | cierra el menú desplegable | ^[Function]`() => void` |

## Dropdown-Menu API

### Dropdown-Menu Slots

| Nombre  | Descripción                    | Subtags       |
| ------- | ------------------------------ | ------------- |
| default | contenido del Menú desplegable | Dropdown-Item |

## Dropdown-Item API

### Dropdown-Item Attributes

| Nombre   | Descripción                                                                    | Type                              | Por defecto |
| -------- | ------------------------------------------------------------------------------ | --------------------------------- | ----------- |
| command  | un comando para ser enviado a la función de callback `command` de los Dropdown | ^[string] / ^[number] / ^[object] | —           |
| disabled | si el elemento está desactivado                                                | ^[boolean]                        | false       |
| divided  | si se visualiza un divisor                                                     | ^[boolean]                        | false       |
| icon     | icono personalizado                                                            | ^[string] / ^[Component]          | —           |

### Dropdown-Item Slots

| Nombre         | Descripción                                    |
| -------------- | ---------------------------------------------- |
| default        | personaliza el contenido del ítem del Dropdown |
| icon ^(2.13.1) | custom icon, it will override the icon prop    |
