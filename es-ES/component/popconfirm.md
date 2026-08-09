---
title: Popconfirm
lang: es-ES
---

# Popconfirm

Un cuadro de diálogo de confirmación simple de una acción.

## Placement

popconfirm has 9 placements.

:::demo Use attribute `title` to set the display content when click the reference element. The attribute `placement` determines the position of the popconfirm. Its value is `[orientation]-[alignment]` with four orientations `top`, `left`, `right`, `bottom` and three alignments `start`, `end`, `null`, and the default alignment is null. Take `placement="left-end"` for example, popconfirm will display on the left of the element which you are hovering and the bottom of the popconfirm aligns with the bottom of the element.

popconfirm/placement

:::

## Uso básico

Popconfirm es similar a Popover. Así que para algunos atributos duplicados, por favor consulte la documentación de Popover.

:::demo Solo el atributo `title` está disponible en Popconfirm, `content` será ignorado.

popconfirm/basic-usage

:::

## Personalizar

Puede personalizar Popconfirm así:

:::demo

popconfirm/customize

:::

## Evento disparador

Haga clic en el botón para activar el evento

:::demo

popconfirm/trigger-event

:::

## API

### Atributos

| Nombre                             | Descripción                                                                                         | Tipo                                                                              | Por defecto    |
| ---------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | -------------- |
| title                              | Título                                                                                              | ^[string]                                                                         | —              |
| effect ^(2.11.2)                   | Popover tiene dos temas: `dark` y `light`                                                           | ^[enum]`'dark' \| 'light'` / ^[string]                                           | light          |
| confirm-button-text                | Texto del botón de confirmar                                                                        | ^[string]                                                                         | —              |
| cancel-button-text                 | Texto del botón de cancelar                                                                         | ^[string]                                                                         | —              |
| confirm-button-type                | Tipo de botón para confirmar                                                                        | ^[enum]`'primary' \| 'success' \| 'warning' \| 'danger' \| 'info' \| 'text'` | primary        |
| cancel-button-type                 | Tipo de botón para cancelar                                                                         | ^[enum]`'primary' \| 'success' \| 'warning' \| 'danger' \| 'info' \| 'text'` | text           |
| icon                               | Componente de icono                                                                                 | ^[string] / ^[Component]                                                          | QuestionFilled |
| icon-color                         | Color del icono                                                                                     | ^[string]                                                                         | #f90           |
| hide-icon                          | si se oculta el icono                                                                               | ^[boolean]                                                                        | false          |
| hide-after                         | retraso de la desaparición, en milisegundos                                                         | ^[number]                                                                         | 200            |
| teleported                         | si el popconfirm se teletransporta al body                                                          | ^[boolean]                                                                        | true           |
| persistent                         | cuando el popconfirm este inactivo y `persistent` es `false`, el popconfirm será destruido          | ^[boolean]                                                                        | false          |
| width                              | popconfirm ancho, ancho mínimo 150px                                                                | ^[string] / ^[number]                                                             | 150            |
| [tooltip](./tooltip.md#attributes) | Inherits all attributes from Tooltip, except: `popper-class`, `popper-style`, `fallback-placements` | —                                                                                 | —              |

### Eventos

| Nombre  | Descripción                                          | Tipo                                    |
| ------- | ---------------------------------------------------- | --------------------------------------- |
| confirm | se dispara cuando se hace clic en el botón confirmar | ^[Function]`(e: MouseEvent) => void` |
| cancel  | activa cuando se hace clic en el botón cancelar      | ^[Function]`(e: MouseEvent) => void` |

### Slots

| Nombre           | Descripción                         | Type                                                                                   |
| ---------------- | ----------------------------------- | -------------------------------------------------------------------------------------- |
| reference        | Elemento HTML que activa Popconfirm | —                                                                                      |
| actions ^(2.8.1) | content of the Popconfirm footer    | ^[object]`{ confirm: (e: MouseEvent) => void, cancel: (e: MouseEvent) => void }` |

### Expuesto

| Nombre              | Descrición                         | Tipo                                               |
| ------------------- | ---------------------------------- | -------------------------------------------------- |
| popperRef ^(2.10.7) | instancia del componente el-popper | ^[object]`Ref<PopperInstance \| undefined>` |
| hide ^(2.10.7)      | hide popconfirm                    | ^[Function]`() => void`                         |
