---
title: Transfer
lang: es-ES
---

# Transfer

## Uso básico

:::demo Los datos son pasados a la transferencia a través del atributo `data`. Los datos deben ser un array de objetos, y cada objeto debe tener estos atributos: `key` siendo la identificación del elemento de datos, `label` siendo el texto mostrado y `disabled` indicando si el elemento de datos está desactivado. Los elementos dentro de la lista de destino están sincronizados con la variable que se enlaza al `v-model`, y el valor de esa variable es un array de keys de los elementos destino. Por lo tanto, si no quiere que la lista de destino esté vacía inicialmente, puede inicializar el `v-model` con un array.

transfer/basic

:::

## Filtrable

Puede buscar y filtrar elementos de datos.

:::demo Establezca el atributo `filterable` a `true` para habilitar el modo filtro. Por defecto, si el elemento de datos `label` contiene la palabra clave de búsqueda, se incluirá en el resultado de la búsqueda. Además, puede implementar su propio método de filtro con el atributo `filter-method`. Toma un método y pasa la palabra clave de búsqueda y cada elemento de los datos cada vez que la palabra clave cambia. Para un determinado elemento de datos, si el método devuelve true, se incluirá en la lista de resultados.

transfer/filterable

:::

## Personalizable

Puede personalizar los títulos de la lista, los textos de los botones, la función de renderizado para los elementos de datos, la comprobación del estado de los textos en el pie de la lista y el contenido del pie.

:::demo Use `titles`, `button-texts`, `render-content` y `format` respectivamente para personalizar los títulos de las listas, el texto de los botones, la función de renderizado para los items y el texto de la cabecera que muestra el estado de los items. Además, también puede utilizar los slots para personalizar los elementos de los datos. Para el pie de la lista hay dos slots: `left-footer` y `right-footer`. Además, si quiere algunos items marcados inicialmente puede usar `left-default-checked` y `right-default-checked`. Finalmente este ejemplo muestra el evento `change`. Tenga en cuenta que esta demostración no puede ejecutarse en JSFiddle porque no soporta la sintaxis JSX. En un proyecto real `render-content` funcionará si las dependencias relevantes están configuradas correctamente.

transfer/customizable

:::

## Custom empty content ^(2.9.0)

You can customize the content when the list is empty or when no filtering results are found.

:::demo Use `left-empty` and `right-empty` slots to customize the empty content for each panel.

transfer/empty-content

:::

## Alias de las props

Por defecto, Transfer busca `key`, `label` y `disabled` en cada elemento. Si sus datos tienen diferentes nombres de clave, puede usar el atributo `props` para definir distintos alias.

:::demo En este ejemplo los elementos no tienen `key` y `label`, en vez de eso tienen `value` y `desc`. Así que tiene que añadir alias para `key` y `label`.

transfer/prop-alias

:::

## Virtual Scroll ^(2.14.3)

When dealing with large amounts of data, you can enable virtual scrolling to improve performance.

:::demo Set `virtual-scroll` to `true` to enable virtual scrolling. You can also customize the item height with `item-size`. Default item size is 30px.

transfer/virtual-scroll

:::

## Transfer API

### Transfer Attributes

| Nombre                      | Descripción                                                                                                                                                                                                                                                                                                                                     | Tipo                                                                        | Default  |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- | -------- |
| model-value / v-model       | valor vinculado                                                                                                                                                                                                                                                                                                                                 | ^[array]`Array<string \| number>`                                    | []       |
| data                        | Origen de datos                                                                                                                                                                                                                                                                                                                                 | ^[array]`Record<string, any>[]`                                       | []       |
| filterable                  | Si se puede filtrar                                                                                                                                                                                                                                                                                                                             | ^[boolean]                                                                  | false    |
| filter-placeholder          | Placeholder para el input del filtro                                                                                                                                                                                                                                                                                                            | ^[string]                                                                   | —        |
| filter-method               | Método de filtrado                                                                                                                                                                                                                                                                                                                              | ^[Function]`(query: string, item: Record<string, any>) => boolean` | —        |
| target-order                | estrategia de órdenes para elementos de la lista destino. Si está configurado en `original`, los elementos mantendrán el mismo orden que la fuente de datos. Si está configurado para `push`, los nuevos elementos añadidos se insertaran al final. Si se ajusta a `unshift`, los nuevos elementos añadidos se insertarán en la parte superior. | ^[enum]`'original' \| 'push' \| 'unshift'`                                | original |
| titles                      | Títulos de las listas                                                                                                                                                                                                                                                                                                                           | ^[array]`[string, string]`                                                  | []       |
| button-texts                | Texto de los botones                                                                                                                                                                                                                                                                                                                            | ^[array]`[string, string]`                                                  | []       |
| render-content              | Función de renderizado                                                                                                                                                                                                                                                                                                                          | ^[object]`renderContent`                                                    | —        |
| format                      | Texto para el status en el header                                                                                                                                                                                                                                                                                                               | ^[object]`TransferFormat`                                                   | {}       |
| [props](#type-declarations) | prop alias para el origen de datos                                                                                                                                                                                                                                                                                                              | ^[object]`TransferPropsAlias`                                               | —        |
| left-default-checked        | Array de claves de los elementos marcados inicialmente en la lista de la izquierda                                                                                                                                                                                                                                                              | ^[array]`Array<string \| number>`                                    | []       |
| right-default-checked       | Array de claves de los elementos marcados inicialmente en la lista de la derecha                                                                                                                                                                                                                                                                | ^[array]`Array<string \| number>`                                    | []       |
| validate-event              | si se debe activar la validación del formulario                                                                                                                                                                                                                                                                                                 | ^[boolean]                                                                  | true     |
| virtual-scroll ^(2.14.3)    | whether to enable virtual scrolling                                                                                                                                                                                                                                                                                                             | ^[boolean]                                                                  | false    |
| item-size ^(2.14.3)         | item height for virtual scrolling                                                                                                                                                                                                                                                                                                               | ^[number]                                                                   | 30       |

### Transfer Events

| Nombre             | Descripción                                                                         | Type                                                                                                   |
| ------------------ | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| change             | triggers when data items change in the right list                                   | ^[Function]`(value: TransferKey[], direction: TransferDirection, movedKeys: TransferKey[]) => void` |
| left-check-change  | triggers when end user changes the checked state of any data item in the left list  | ^[Function]`(value: TransferKey[], movedKeys?: TransferKey[]) => void`                              |
| right-check-change | triggers when end user changes the checked state of any data item in the right list | ^[Function]`(value: TransferKey[], movedKeys?: TransferKey[]) => void`                              |

### Transfer Slots

| Name                 | Descripción                                                          | Type                                    |
| -------------------- | -------------------------------------------------------------------- | --------------------------------------- |
| default              | Custom content for data items.                                       | ^[object]`{ option: TransferDataItem }` |
| left-footer          | content of left list footer                                          | —                                       |
| right-footer         | content of right list footer                                         | —                                       |
| left-empty ^(2.9.0)  | content when left panel is empty or when no data matches the filter  | —                                       |
| right-empty ^(2.9.0) | content when right panel is empty or when no data matches the filter | —                                       |

### Transfer Exposes

| Name       | Descripción                                 | Type                                               |
| ---------- | ------------------------------------------- | -------------------------------------------------- |
| clearQuery | clear the filter keyword of a certain panel | ^[Function]`(which: TransferDirection) => void` |
| leftPanel  | left panel ref                              | ^[object]`Ref<TransferPanelInstance>`        |
| rightPanel | right panel ref                             | ^[object]`Ref<TransferPanelInstance>`        |

## Transfer Panel API

### Transfer Panel Exposes

| Name  | Description    | Parámetros |
| ----- | -------------- | ---------- |
| query | filter keyword | ^[string]  |

## Type Declarations

<details>
  <summary>Show declarations</summary>

```ts
import type { h as H, VNode } from 'vue'

type TransferKey = string | number

type TransferDirection = 'left' | 'right'

type TransferDataItem = Record<string, any>

type renderContent<T extends TransferDataItem = TransferDataItem> = (
  h: typeof H,
  option: T
) => VNode | VNode[]

interface TransferFormat {
  noChecked?: string
  hasChecked?: string
}

interface TransferPropsAlias {
  label?: string
  key?: string
  disabled?: string
}
```

</details>
