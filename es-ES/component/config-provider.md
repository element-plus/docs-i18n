---
title: Config Provider
lang: es-ES
---

# Proveedor de configuración

Config Provider se utiliza para proporcionar configuraciones globales, lo que permite a toda la aplicación acceder a estas configuraciones en todas partes.

## Configuraciones i18n

Configure las propiedades relacionadas con i18n a través del proveedor de configuración, para obtener la función de cambiar de idioma.

:::demo Use dos atributos para proporcionar configuración relacionada con i18n

config-provider/usage

:::

## Configuración de botones

:::demo

config-provider/button

:::

## Link Configurations ^(2.9.11)

:::demo

config-provider/link

:::

## Card Configurations ^(2.10.5)

:::demo

config-provider/card

:::

## Dialog Configurations ^(2.10.7)

:::demo

config-provider/dialog

:::

## Configuración de mensajes

:::demo

config-provider/message

:::

## Empty Values Configurations ^(2.7.0)

<details>
  <summary>Supported components list</summary>

- Cascader
- ColorPicker ^(2.10.3)
- DatePicker
- Select
- SelectV2
- TimePicker
- TimeSelect
- TreeSelect

</details>

Set `empty-values` to support empty values of components. The fallback value is `['', null, undefined]`. If you think the empty string is meaningful, write `[undefined, null]`.

Set `value-on-clear` to set the return value when cleared. The fallback value is `undefined`. In the date component is `null`. If you want to set `undefined`, use `() => undefined`.

:::demo

config-provider/empty-values

:::

## Table Configurations ^(2.13.3)

:::demo

config-provider/table

:::

## Características experimentales

En esta sección, puede aprender cómo usar el Proveedor de Configuración para proporcionar características experimentales. Por ahora, no hemos añadido ninguna característica experimental, pero en el mapa de características añadiremos algunas. Puede usar esta configuración para administrar las características que desea o no.

 <!-- TODO -->

## API

### Atributos del proveedor de configuración

| Nombre                  | Descripción                                                                                                                                                                | Tipo                                                                                                                                                                                                                                                           | Por defecto                                                                            |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| locale                  | Objeto Locale                                                                                                                                                              | ^[object]`{name: string, el: TranslatePair}`[](https://github.com/element-plus/element-plus/blob/a98ff9b40c0c3d2b9959f99919bd8363e3e3c25a/packages/locale/index.ts#L5) [languages](https://github.com/element-plus/element-plus/tree/dev/packages/locale/lang) | [en](https://github.com/element-plus/element-plus/blob/dev/packages/locale/lang/en.ts) |
| size                    | tamaño global del componente                                                                                                                                               | ^[enum]`'large' \| 'default' \| 'small'`                                                                                                                                                                                                                     | default                                                                                |
| zIndex                  | zIndex inicial global                                                                                                                                                      | ^[number]                                                                                                                                                                                                                                                      | —                                                                                      |
| namespace               | prefijo global className del componente (cooperado con [$namespace](https://github.com/element-plus/element-plus/blob/dev/packages/theme-chalk/src/mixins/config.scss#L1)) | ^[string]                                                                                                                                                                                                                                                      | el                                                                                     |
| button                  | configuración relacionada con el botón, [vea la siguiente tabla](#button-attribute)                                                                                        | ^[object]`{autoInsertSpace?: boolean, type?: string, plain?: boolean, text?: boolean, round?: boolean, dashed?: boolean}`                                                                                                                                      | see the following table                                                                |
| link                    | link related configuration, [see the following table](#link-attribute)                                                                                                     | ^[object]`{type?: string, underline?: boolean \| string}`                                                                                                                                                                                                     | see the following table                                                                |
| dialog ^(2.10.7)        | dialog related configuration, [see the following table](#dialog-attribute)                                                                                                 | ^[object]`{alignCenter?: boolean, draggable?: boolean, overflow?: boolean, transition?: DialogTransition}`                                                                                                                                                     | see the following table                                                                |
| message                 | configuración relacionada con mensajes, [vea la siguiente tabla](#message-attribute)                                                                                       | ^[object]`{max?: number}`                                                                                                                                                                                                                                      | see the following table                                                                |
| experimental-features   | características en la etapa experimental a ser añadidas, todas las características son definidas como falsas                                                               | ^[object]                                                                                                                                                                                                                                                      | —                                                                                      |
| empty-values ^(2.7.0)   | global empty values of components                                                                                                                                          | ^[array]                                                                                                                                                                                                                                                       | —                                                                                      |
| value-on-clear ^(2.7.0) | global clear return value                                                                                                                                                  | ^[string] / ^[number] / ^[boolean] / ^[Function]                                                                                                                                                                                                               | —                                                                                      |
| table ^(2.13.3)         | table related configuration, [see the following table](#table-attribute)                                                                                                   | ^[object]`{showOverflowTooltip?: boolean \| object, tooltipEffect?: string, tooltipOptions?: object, tooltipFormatter?: Function}`                                                                                                                            | see the following table                                                                |

### Atributo del botón

| Atributo         | Descripción                                                                                                                                          | Tipo                                                                                           | Por defecto |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ----------- |
| type ^(2.9.11)   | button type, when setting `color`, the latter prevails                                                                                               | ^[enum]`'primary' \| 'success' \| 'warning' \| 'danger' \| 'info' \| 'text' (deprecated)` | —           |
| autoInsertSpace  | automatically insert a space between two chinese characters(this will only take effect when the text length is 2 and all characters are in Chinese.) | ^[boolean]                                                                                     | false       |
| plain ^(2.9.11)  | determine whether it's a plain button                                                                                                                | ^[boolean]                                                                                     | false       |
| text ^(2.11.0)   | determinar si es un botón de texto                                                                                                                   | ^[boolean]                                                                                     | false       |
| round ^(2.9.11)  | determine whether it's a round button                                                                                                                | ^[boolean]                                                                                     | false       |
| dashed ^(2.13.3) | determine whether it's a dashed button                                                                                                               | ^[boolean]                                                                                     | false       |

### Link Attribute

| Atributo            | Descripción                   | Tipo                                                                                 | Por defecto |
| ------------------- | ----------------------------- | ------------------------------------------------------------------------------------ | ----------- |
| type ^(2.9.11)      | type                          | ^[enum]`'primary' \| 'success' \| 'warning' \| 'danger' \| 'info' \| 'default'` | default     |
| underline ^(2.9.11) | when underlines should appear | ^[enum]`'always' \| 'hover' \| 'never' \| boolean`                                | hover       |

### Card Attribute

| Attribute        | Descripción               | Type                                | Default |
| ---------------- | ------------------------- | ----------------------------------- | ------- |
| shadow ^(2.10.5) | when to show card shadows | ^[enum]`always \| never \| hover` | —       |

### Dialog Attribute

| Attribute              | Description                                                                                                                    | Type                                   | Default |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------- | ------- |
| align-center ^(2.10.7) | si se alinea el diálogo tanto horizontal como verticalmente                                                                    | ^[boolean]                             | false   |
| draggable ^(2.10.7)    | activar característica de arrastre para el diálogo                                                                             | ^[boolean]                             | false   |
| overflow ^(2.10.7)     | draggable Dialog can overflow the viewport long                                                                                | ^[boolean]                             | false   |
| transition ^(2.10.7)   | custom transition configuration for dialog animation. Can be a string (transition name) or an object with Vue transition props | ^[string] / ^[object]`TransitionProps` | —       |

### Atributo del mensaje

| Atributo            | Description                                                                    | Tipo                                                                                            | Por defecto |
| ------------------- | ------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------- | ----------- |
| max                 | el número máximo de mensajes que se pueden mostrar al mismo tiempo             | ^[number]                                                                                       | —           |
| grouping ^(2.8.2)   | merge messages with the same content, type of VNode message is not supported   | ^[boolean]                                                                                      | —           |
| duration ^(2.8.2)   | display duration, millisecond. If set to 0, it will not turn off automatically | ^[number]                                                                                       | —           |
| showClose ^(2.8.2)  | whether to show a close button                                                 | ^[boolean]                                                                                      | —           |
| offset ^(2.8.2)     | set the distance to the top of viewport                                        | ^[number]                                                                                       | —           |
| plain ^(2.9.11)     | whether message is plain                                                       | ^[boolean]                                                                                      | —           |
| placement ^(2.11.0) | message placement position                                                     | ^[enum]`'top' \| 'top-left' \| 'top-right' \| 'bottom' \| 'bottom-left' \| 'bottom-right'` | —           |

### Table Attribute ^(2.13.3)

| Atributo              | Descripción                                                                                                                                             | Tipo                                                                                                                                                                               | Por defecto                                                                                                             |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| show-overflow-tooltip | whether to hide extra content and show them in a tooltip when hovering on the cell.It will affect all the table columns, refer to table tooltip-options | ^[boolean] / [`object`]                                                                                                                                                            | —                                                                                                                       |
| tooltip-effect        | el `effect` del tooltip por desbordamiento                                                                                                              | ^[enum]`'dark' \| 'light'`                                                                                                                                                        | dark                                                                                                                    |
| tooltip-options       | las opciones para el tooltip de desbordamiento, [vea el componente de tooltip](tooltip.html#attributes)                                                 | ^[object]`Pick<ElTooltipProps, 'effect' \| 'enterable' \| 'hideAfter' \| 'offset' \| 'placement' \| 'popperClass' \| 'popperOptions' \| 'showAfter' \| 'showArrow'>` | ^[object]`{ enterable: true, placement: 'top', showArrow: true, hideAfter: 200, popperOptions: { strategy: 'fixed' } }` |
| tooltip-formatter     | customize tooltip content when using `show-overflow-tooltip`                                                                                            | ^[Function]`(data: { row: any, column: TableColumnCtx<T>, cellValue: any }) => VNode \| string`                                                                          | —                                                                                                                       |

### Config Provider Slots

| Nombre  | Descripción                          | Tipo                                                               |
| ------- | ------------------------------------ | ------------------------------------------------------------------ |
| default | personaliza el contenido por defecto | config: configuración global proporcionada (heredada desde arriba) |
