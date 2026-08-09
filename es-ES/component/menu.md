---
title: Menu
lang: es-ES
---

# Menu

Menú que proporciona navegación para su sitio web.

::: tip

If you want to override the default height of el-menu, you can use the following CSS:

```css
.el-menu--horizontal {
  --el-menu-horizontal-height: 100px;
}
```

:::

## Barra superior

Menú de barra superior, se puede utilizar en una variedad de escenarios.

:::demo Por defecto Menú es vertical, pero puedes cambiarlo a horizontal ajustando el modo prop a 'horizontal'. Además, puede utilizar el componente de submenú para crear un menú de segundo nivel. El menú proporciona `background-color`, `text-color` y `active-text-color` para personalizar los colores.

menu/basic

:::

## Izquierda y derecha

:::demo Puede hacer que los elementos del menú estén a la izquierda o a la derecha.

menu/left-and-right

:::

## Barra lateral

Menú vertical con submenús.

:::demo Puede usar el componente el-menu-item-group para crear un grupo de menús, y el nombre del grupo está determinado por la propiedad title o un slot con nombre.

menu/vertical

:::

## Collapse

El menú vertical puede ser colapsado.

:::demo

menu/collapse

:::

## Popper Offset ^(2.4.4)

Submenu with popperOffset will override Menu's `popper-offset`.

:::demo

menu/popper-offset

:::

## Menu API

### Menu Attributes

| Nombre                          | Descripción                                                                                                                                                                                             | Tipo                                    | Default  |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------- | -------- |
| mode                            | modo de visualización del menú                                                                                                                                                                          | ^[enum]`'horizontal' \| 'vertical'`    | vertical |
| collapse                        | si el menú está colapsado (solo en modo vertical)                                                                                                                                                       | ^[boolean]                              | false    |
| ellipsis                        | si el menú es elipsis (disponible sólo en modo horizontal)                                                                                                                                              | ^[boolean]                              | true     |
| ellipsis-icon ^(2.4.4)          | custom ellipsis icon (available only in horizontal mode and ellipsis is true)                                                                                                                           | ^[string] / ^[Component]                | —        |
| popper-offset ^(2.4.4)          | offset of the popper (effective for all submenus)                                                                                                                                                       | ^[number]                               | 6        |
| default-active                  | índice del menú activo al cargar la página                                                                                                                                                              | ^[string]                               | ''       |
| default-openeds                 | array que contiene los índices de los sub-menús activos actualmente                                                                                                                                     | ^[array]`string[]`                      | []       |
| unique-opened                   | si sólo un submenú puede estar activo                                                                                                                                                                   | ^[boolean]                              | false    |
| menu-trigger                    | cómo se activan los submenús, solo funciona cuando `mode` es 'horizontal'                                                                                                                               | ^[enum]`'hover' \| 'click'`            | hover    |
| router                          | si el modo `vue-router` está activado. Si es verdadero, el índice se utilizará como 'ruta' para activar la acción de la ruta. Utilice con `default-active` para establecer el elemento activo en carga. | ^[boolean]                              | false    |
| collapse-transition             | si habilitar transition en el colapso                                                                                                                                                                   | ^[boolean]                              | true     |
| popper-effect ^(2.2.26)         | Tema Tooltip, tema integrado: `dark` / `light` cuando el menú está colapsado                                                                                                                            | ^[enum]`'dark' \| 'light'` / ^[string] | dark     |
| close-on-click-outside ^(2.4.4) | optional, whether menu is collapsed when clicking outside                                                                                                                                               | ^[boolean]                              | false    |
| popper-class ^(2.5.0)           | custom class name for all popup menus and titles' tooltips                                                                                                                                              | ^[string]                               | —        |
| popper-style ^(2.11.5)          | custom style for all popup menus and titles' tooltips                                                                                                                                                   | ^[string] / ^[object]                   | —        |
| show-timeout ^(2.5.0)           | control timeout for all menus before showing                                                                                                                                                            | ^[number]                               | 300      |
| hide-timeout ^(2.5.0)           | control timeout for all menus before hiding                                                                                                                                                             | ^[number]                               | 300      |
| background-color ^(deprecated)  | background color of Menu (hex format) (use `--el-menu-bg-color` in a style class instead)                                                                                                               | ^[string]                               | #ffffff  |
| text-color ^(deprecated)        | text color of Menu (hex format) ( use `--el-menu-text-color` in a style class instead)                                                                                                                  | ^[string]                               | #303133  |
| active-text-color ^(deprecated) | text color of currently active menu item (hex format) ( use `--el-menu-active-color` in a style class instead)                                                                                          | ^[string]                               | #409eff  |
| persistent ^(2.9.5)             | when menu inactive and `persistent` is `false` , dropdown menu will be destroyed                                                                                                                        | ^[boolean]                              | true     |

### Menu Events

| Nombre | Descripción                                   | Tipo                         |
| ------ | --------------------------------------------- | ---------------------------- |
| select | callback ejecutado cuando el menú es activado | ^[Function]`MenuSelectEvent` |
| open   | función callback cuando el submenú se expande | ^[Function]`MenuOpenEvent`   |
| close  | función callback cuando el submenú colapsa    | ^[Function]`MenuCloseEvent`  |

### Menu Slots

| Nombre  | Descripción                          | Subtags                               |
| ------- | ------------------------------------ | ------------------------------------- |
| default | personaliza el contenido por defecto | SubMenu / Menu-Item / Menu-Item-Group |

### Menu Exposes

| Nombre                     | Descripción                                                            | Tipo                                    |
| -------------------------- | ---------------------------------------------------------------------- | --------------------------------------- |
| open                       | open a specific sub-menu, the param is index of the sub-menu to open   | ^[Function]`(index: string) => void` |
| close                      | close a specific sub-menu, the param is index of the sub-menu to close | ^[Function]`(index: string) => void` |
| handleResize               | manually trigger menu width recalculation                              | ^[Function]`() => void`              |
| updateActiveIndex ^(2.9.8) | set index of active menu                                               | ^[Function]`(index: string) => void` |

## SubMenu API

### SubMenu Attributes

| Nombre                 | Descripción                                                                                                                                      | Tipo                     | Por defecto |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------ | ----------- |
| index ^(required)      | identificador único                                                                                                                              | ^[string]                | —           |
| popper-class           | nombre personalizado de la clase del menú popup                                                                                                  | ^[string]                | —           |
| popper-style ^(2.11.5) | custom style for the popup menu                                                                                                                  | ^[string] / ^[object]    | —           |
| show-timeout           | timeout before showing a sub-menu(inherit `show-timeout` of the menu by default.)                                                                | ^[number]                | —           |
| hide-timeout           | timeout before hiding a sub-menu(inherit `hide-timeout` of the menu by default.)                                                                 | ^[number]                | —           |
| disabled               | si el submenú está deshabilitado                                                                                                                 | ^[boolean]               | false       |
| teleported             | whether popup menu is teleported to the body, the default is true for the level one SubMenu, false for other SubMenus                            | ^[boolean]               | undefined   |
| popper-offset          | offset of the popper (overrides the `popper` of menu)                                                                                            | ^[number]                | —           |
| expand-close-icon      | El icono cuando el menú se expanda y el submenú se cierran, `expand-close-icon` y `expand-open-icon` deben pasarse juntos para que surtan efecto | ^[string] / ^[Component] | —           |
| expand-open-icon       | El icono cuando el menú se expanda y el submenú se abre, `expand-close-icon` y `expand-open-icon` deben pasarse juntos para que surtan efecto    | ^[string] / ^[Component] | —           |
| collapse-close-icon    | El icono cuando el menú se expanda y el submenú se cierra, `expand-close-icon` y `expand-open-icon` deben pasarse juntos para que surtan efecto  | ^[string] / ^[Component] | —           |
| collapse-open-icon     | El icono cuando el menú se expanda y el submenú se abra, `expand-close-icon` y `expand-open-icon` deben pasarse juntos para que surtan efecto    | ^[string] / ^[Component] | —           |

### SubMenu Slots

| Nombre  | Descripción                          | Subtags                               |
| ------- | ------------------------------------ | ------------------------------------- |
| default | personaliza el contenido por defecto | SubMenu / Menu-Item / Menu-Item-Group |
| title   | personalizar contenido del título    | —                                     |

## Menu-Item API

### Menu-Item Attributes

| Nombre            | Descripción                          | Type                  | Por defecto |
| ----------------- | ------------------------------------ | --------------------- | ----------- |
| index ^(required) | identificador único                  | ^[string]             | —           |
| route             | Vue Router Route Location Parameters | ^[string] / ^[object] | —           |
| disabled          | si está desactivado                  | ^[boolean]            | false       |

### Menu-Item Events

| Nombre | Descripción                                                                  | Type                                               |
| ------ | ---------------------------------------------------------------------------- | -------------------------------------------------- |
| click  | callback function when menu-item is clicked, the param is menu-item instance | ^[Function]`(item: MenuItemRegistered) => void` |

### Menu-Item Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |
| title   | personalizar contenido del título    |

## Menu-Item-Group API

### Menu-Item-Group Attributes

| Nombre | Descripción      | Type      | Por defecto |
| ------ | ---------------- | --------- | ----------- |
| title  | título del grupo | ^[string] | —           |

### Menu-Item-Group Slots

| Name    | Descripción                          | Subtags   |
| ------- | ------------------------------------ | --------- |
| default | personaliza el contenido por defecto | Menu-Item |
| title   | personalizar título del grupo        | —         |

## Type Declarations

<details>
  <summary>Show declarations</summary>

```ts
/**
 * @param index index of activated menu
 * @param indexPath index path of activated menu
 * @param item the selected menu item
 * @param routerResult result returned by `vue-router` if `router` is enabled
 */
type MenuSelectEvent = (
  index: string,
  indexPath: string[],
  item: MenuItemClicked,
  routerResult?: Promise<void | NavigationFailure>
) => void

/**
 * @param index index of expanded sub-menu
 * @param indexPath index path of expanded sub-menu
 */
type MenuOpenEvent = (index: string, indexPath: string[]) => void

/**
 * @param index index of collapsed sub-menu
 * @param indexPath index path of collapsed sub-menu
 */
type MenuCloseEvent = (index: string, indexPath: string[]) => void

interface MenuItemRegistered {
  index: string
  indexPath: string[]
  active: boolean
}

interface MenuItemClicked {
  index: string
  indexPath: string[]
  route?: RouteLocationRaw
}
```

</details>
