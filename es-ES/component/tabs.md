---
title: Tabulación
lang: es-ES
---

# Tabulación

Divide colecciones de datos que están relacionados pero pertenecen a diferentes tipos.

## Uso básico

Tabulación básica y concisa

:::demo Tabulación provee funcionalidad de tarjeta selectiva. Por defecto, la primer pestaña es seleccionada como activa, y es posible activar cualquier pestaña estableciendo el atributo de `value`.

tabs/basic

:::

## Estilo de Tarjeta

Pestañas diseñadas como tarjetas.

:::demo Establecer `type` a `card` para obtener una pestaña diseñada como tarjeta.

tabs/card-style

:::

## Tarjeta con Bordes

Pestañas de tarjeta con bordes.

:::demo Establecer `type` a `border-card`.

tabs/border-card

:::

## Posición de tabulación

Es posible usar el atributo `tab-position` para establecer la posición de la tabulación.

:::demo Es posible escoger entre cuatro direcciones: `tabPosition="left|right|top|bottom"`

tabs/tab-position

:::

## Pestaña Personalizada

Es posible usar slots con nombre para personalizar el contenido de la etiqueta de la pestaña.

:::demo

tabs/custom-tab

:::

## Agregar y cerrar pestaña

Solo las pestañas de tipo tarjeta soportan adición y cierre.

:::demo

tabs/dynamic-tabs

:::

## Customized add button icon ^(2.4.0)

:::demo

tabs/customized-add-button-icon

:::

## Customized trigger button of new tab

:::demo

tabs/customized-trigger

:::

## Default value ^(2.11.9)

:::demo

tabs/default-value

:::

## Tabs API

### Tabs Attributes

| Nombre                  | Descripción                                                                                                                              | Tipo                                                                                                       | Default    |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------- |
| model-value / v-model   | binding value, name of the selected tab, the default value is the name of first tab                                                      | ^[string] / ^[number]                                                                                      | —          |
| default-value ^(2.11.9) | The value of the tab that should be active when initially rendered. (avoid initial transition)                                           | ^[string] / ^[number]                                                                                      | —          |
| type                    | tipo de Pestaña                                                                                                                          | ^[enum]`'' \| 'card' \| 'border-card'`                                                                   | ''         |
| closable                | si la Pestaña es cerrable                                                                                                                | ^[boolean]                                                                                                 | false      |
| addable                 | si la Pestaña es añadible                                                                                                                | ^[boolean]                                                                                                 | false      |
| editable                | si la Pestaña es añadible y cerrable                                                                                                     | ^[boolean]                                                                                                 | false      |
| tab-position            | posición de tabulación                                                                                                                   | ^[enum]`'top' \| 'right' \| 'bottom' \| 'left'`                                                         | top        |
| stretch                 | si el ancho del tab se ajusta automáticamente a su contenedor                                                                            | ^[boolean]                                                                                                 | false      |
| before-leave            | función `hook` antes de cambiar de pestaña. Si se devuelve `false` o se devuelve una `Promise` y luego se rechaza, se evitará el cambio. | ^[Function]`(activeName: TabPaneName, oldActiveName: TabPaneName) => Awaitable<void \| boolean>` | () => true |
| tabindex ^(2.11.7)      | tabs tabindex                                                                                                                            | ^[string] / ^[number]                                                                                      | 0          |

### Tabs Events

| Nombre     | Descripción                                                          | Parámetros                                                                                |
| ---------- | -------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| tab-click  | se lanza cuando se hace clic a una pestaña                           | ^[Function]`(pane: TabsPaneContext, ev: Event) => void`                                |
| tab-change | se dispara cuando `activeName` cambia                                | ^[Function]`(name: TabPaneName) => void`                                               |
| tab-remove | se lanza cuando se hace clic al botón tab-remove                     | ^[Function]`(name: TabPaneName) => void`                                               |
| tab-add    | se lanza cuando se hace clic al botón tab-add                        | ^[Function]`() => void`                                                                |
| edit       | se lanza cuando los botones de tab-add y/o tab-remove son clickeados | ^[Function]`(paneName: TabPaneName \| undefined, action: 'remove' \| 'add') => void` |

### Tabs Slots

| Nombre                         | Descripción                          | Subtags  |
| ------------------------------ | ------------------------------------ | -------- |
| default                        | personaliza el contenido por defecto | Tab-pane |
| add-icon ^(2.5.4)              | customize add button icon            | —        |
| addIcon ^(2.4.0) ^(deprecated) | customize add button icon            | —        |

### Tabs Exposes

| Nombre              | Descripción                | Tipo                                               |
| ------------------- | -------------------------- | -------------------------------------------------- |
| currentName         | current active pane name   | ^[object]`Ref<TabPaneName>`                  |
| tabNavRef ^(2.9.10) | tab-nav component instance | ^[object]`Ref<TabNavInstance \| undefined>` |

## Tab-nav API

### Tab-nav Exposes

| Nombre               | Descripción                       | Type                                               |
| -------------------- | --------------------------------- | -------------------------------------------------- |
| scrollToActiveTab    | scroll to the active tab          | ^[Function]`() => Promise<void>`          |
| removeFocus          | remove focus status               | ^[Function]`() => boolean`                      |
| tabListRef ^(2.9.10) | el_tabs\_\_nav html element | ^[object]`Ref<HTMLDivElement \| undefined>` |
| tabBarRef ^(2.9.10)  | el_tabs\_\_nav bar instance | ^[object]`Ref<TabBarInstance \| undefined>` |

## Tab-bar API

### Tab-bar Exposes

| Name             | Description                                                       | Type                                               |
| ---------------- | ----------------------------------------------------------------- | -------------------------------------------------- |
| ref ^(2.9.10)    | tab root html element                                             | ^[object]`Ref<HTMLDivElement \| undefined>` |
| update ^(2.9.10) | method to manually update tab bar style, return the updated style | ^[Function]`() => CSSProperties`                |

## Tab-pane API

### Tab-pane Attributes

| Name     | Description                                                                                                                                                                         | Tipo                  | Por defecto |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- | ----------- |
| label    | título de la pestaña                                                                                                                                                                | ^[string]             | ''          |
| disabled | si la Tabulación está deshabilitada                                                                                                                                                 | ^[boolean]            | false       |
| name     | identifier corresponding to the name of Tabs, representing the alias of the tab-pane, the default is ordinal number of the tab-pane in the sequence, e.g. the first tab-pane is '0' | ^[string] / ^[number] | —           |
| closable | si la Pestaña es cerrable                                                                                                                                                           | ^[boolean]            | false       |
| lazy     | si Tab es renderizado con `lazy-load`                                                                                                                                               | ^[boolean]            | false       |

### Tab-pane Slots

| Nombre  | Descripción                 |
| ------- | --------------------------- |
| default | Contenido de los Tab-pane's |
| label   | Etiqueta de los Tab-pane's  |

## FAQ

#### How to use sortable/draggable tabs ?

We exposed the necessary information to implement it yourself. You can use a native way to do it, [demo](https://tinyurl.com/2jkyw82j). Or using [SortableJs](https://github.com/SortableJS/Sortable), [demo](https://tinyurl.com/2r8js24y).
