---
title: Virtualized Tree
lang: es-ES
---

# <ElBadge value="beta">Árbol virtualizado V2</ElBadge>

Vista del árbol con un rendimiento de desplazamiento rápido para cualquier cantidad de datos

## Uso básico

Estructura básica de árbol.

:::demo

tree-v2/basic

:::

## Seleccionable

Usado para la selección de nodos.

:::demo

tree-v2/selectable

:::

:::warning

When using show-checkbox, since `check-on-click-leaf` is true by default, last tree children's can be checked by clicking their nodes.

:::

## Checkbox desactivados

El checkbox de un nodo se puede poner como desactivado.

:::demo En el ejemplo, la propiedad`disabled` es declarada en defaultProps, y algunos nodos se establecen como `disabled: true`. Los checkboxes correspondientes son desactivados y no se pueden pinchar.

tree-v2/disabled

:::

## Desplegado o seleccionado por defecto

Los nodos pueden estar desplegados o seleccionados por defecto.

:::demo Utilice `default-expanded-keys` y `default-checked-keys` para establecer los nodos desplegados y seleccionados respectivamente.

tree-v2/default-state

:::

## Contenido personalizado en los nodos

El contenido de los nodos puede ser personalizado, así que puede añadir iconos y botones a su gusto.

:::demo

tree-v2/custom-node

:::

## Custom node class ^(2.9.0)

The class of tree nodes can be customized

:::demo

tree-v2/custom-node-class

:::

## Custom node icon ^(2.10.3)

You can customize icons for different node states. Tree nodes expose the `expanded` property and `isLeaf` property, allowing you to dynamically render different icons based on the node's state: leaf nodes, expanded nodes, or collapsed nodes.

:::demo

tree-v2/custom-icon

:::

## Tree node filtering ^(2.9.1)

The `filter-method` method can only accept the third parameter after version `2.9.1`. Tree nodes can be filtered

:::demo Invoque el método `filter` de la instancia de Tree para filtrar los nodos. Su parámetro es la palabra de filtrado. Note that for it to work, `filter-method` is required, and its value is the filtering method.

tree-v2/filter

:::

## TreeV2 API

### TreeV2 Attributes

| Nombre                        | Descripción                                                                                                 | Tipo                                                                           | Por defecto |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | ----------- |
| data                          | Datos del árbol                                                                                             | ^[array]`Array<{[key: string]: any}>`                                    | —           |
| empty-text                    | Texto a mostrar cuando data es void                                                                         | ^[string]                                                                      | —           |
| [props](#props)               | Opciones de configuración                                                                                   | ^[object]                                                                      | —           |
| highlight-current             | Si el nodo actual está resaltado                                                                            | ^[boolean]                                                                     | false       |
| expand-on-click-node          | Si expandir o contraer un nodo al pincharlo, si es false solo se hará al pinchar en la flecha               | ^[boolean]                                                                     | true        |
| check-on-click-node           | Si es `false`, el nodo sólo se puede marcar o desmarcar haciendo clic en la casilla de verificación.        | ^[boolean]                                                                     | false       |
| check-on-click-leaf ^(2.9.6)  | whether to check or uncheck node when clicking on leaf node (last children).                                | ^[boolean]                                                                     | true        |
| default-expanded-keys         | Array de claves de los nodos expandidos inicialmente                                                        | ^[array]`Array<string \| number>`                                       | —           |
| show-checkbox                 | Si un nodo es seleccionable                                                                                 | ^[boolean]                                                                     | false       |
| check-strictly                | El estado de selección de un nodo no afecta a sus padres o hijos, cuando `show-checkbox` es `true`          | ^[boolean]                                                                     | false       |
| default-checked-keys          | Array con claves de los nodos seleccionados inicialmente                                                    | ^[array]`Array<string \| number>`                                       | —           |
| current-node-key              | la clave del nodo inicialmente seleccionado                                                                 | ^[string] / ^[number]                                                          | —           |
| filter-method                 | esta función se ejecutará antes de arrastrar un nodo. si devuelve `false`, el nodo no puede ser arrastrado. | ^[Function]`(query: string, data: TreeNodeData, node: TreeNode) => boolean` | —           |
| indent                        | Indentación horizontal de los nodos en niveles adyacentes, en pixeles                                       | ^[number]                                                                      | 16          |
| icon                          | custom tree node icon component                                                                             | ^[string] / ^[Component]                                                       | —           |
| item-size ^(2.2.33)           | altura del nodo de árbol personalizado                                                                      | ^[number]                                                                      | 26          |
| scrollbar-always-on ^(2.10.4) | always show scrollbar                                                                                       | ^[boolean]                                                                     | false       |
| height                        | height of the tree                                                                                          | ^[number]                                                                      | 200         |

### props

| Atributos      | Descripción                                                                     | Tipo                                                                                                    | Por defecto |
| -------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | ----------- |
| value          | Identificador único en todo el árbol para los nodos                             | ^[string]                                                                                               | id          |
| label          | especifica qué clave del objeto del nodo se utiliza como label                  | ^[string]                                                                                               | label       |
| children       | Especifica que objeto del nodo se utiliza como subárbol                         | ^[string]                                                                                               | children    |
| disabled       | Especifica si el nodo es una hoja, sólo funciona cuando lazy load está activado | ^[string]                                                                                               | disabled    |
| class ^(2.9.0) | custom node class name                                                          | ^[string] / ^[Function]`(data: TreeNodeData, node: TreeNode) => string \| {[key: string]: boolean}` | —           |

### TreeV2 Exposes

`Tree` has the following method, which returns the currently selected array of nodes.

| Method                | Descripción                                                                                                                       | Parámetros                                                               |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| filter                | filter all tree nodes, filtered nodes will be hidden                                                                              | `(query: string)`                                                        |
| getCheckedNodes       | If the node can be selected (`show-checkbox` is `true`), it returns the currently selected array of nodes                         | `(leafOnly: boolean)`                                                    |
| getCheckedKeys        | If the node can be selected (`show-checkbox` is `true`), it returns the currently selected array of node's keys                   | `(leafOnly: boolean)`                                                    |
| setCheckedKeys        | set certain nodes to be checked                                                                                                   | `(keys: TreeKey[])`                                                      |
| setChecked            | set node to be checked or not, `deep` (added in ^(2.14.0)) indicates whether child nodes should be recursively checked/unchecked. | `(key: TreeKey, checked: boolean, deep?: boolean)`                       |
| setExpandedKeys       | set certain nodes to be expanded                                                                                                  | `(keys: TreeKey[])`                                                      |
| getHalfCheckedNodes   | If the node can be selected (`show-checkbox` is `true`), it returns the currently half selected array of nodes                    | —                                                                        |
| getHalfCheckedKeys    | If the node can be selected (`show-checkbox` is `true`), it returns the currently half selected array of node's keys              | —                                                                        |
| getCurrentKey         | return the highlight node's key (undefined if no node is highlighted)                                                             | —                                                                        |
| getCurrentNode        | return the highlight node's data (undefined if no node is highlighted)                                                            | —                                                                        |
| setCurrentKey         | set highlighted node by key                                                                                                       | `(key: TreeKey)`                                                         |
| getNode               | get node by key or data                                                                                                           | `(data: TreeKey \| TreeNodeData)`                                       |
| expandNode            | expand specified node                                                                                                             | `(node: TreeNode)`                                                       |
| collapseNode          | collapse specified node                                                                                                           | `(node: TreeNode)`                                                       |
| setData               | When the data is very large, using reactive data will cause the poor performance, so we provide a way to avoid this situation     | `(data: TreeData)`                                                       |
| scrollTo ^(2.8.0)     | scroll to a given position                                                                                                        | `(offset: number)`                                                       |
| scrollToNode ^(2.8.0) | scroll to a given tree key with specified scroll strategy                                                                         | `(key: TreeKey, strategy?: auto \| smart \| center \| start \| end)` |

### TreeV2 Events

| Nombre             | Descripción                                          | Parameters                                                                                                                              |
| ------------------ | ---------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| node-click         | triggers when a node is clicked                      | `(data: TreeNodeData, node: TreeNode, e: MouseEvent)`                                                                                   |
| node-drop ^(2.8.3) | triggers when drag something and drop on a node      | `(data: TreeNodeData, node: TreeNode, e: DragEvent)`                                                                                    |
| node-contextmenu   | triggers when a node is clicked by right button      | `(e: Event, data: TreeNodeData, node: TreeNode)`                                                                                        |
| check-change       | triggers when the selected state of the node changes | `(data: TreeNodeData, checked: boolean)`                                                                                                |
| check              | triggers after clicking the checkbox of a node       | `(data: TreeNodeData, info: { checkedKeys: TreeKey[],checkedNodes: TreeData, halfCheckedKeys: TreeKey[], halfCheckedNodes: TreeData,})` |
| current-change     | triggers when current node changes                   | `(data: TreeNodeData, node: TreeNode)`                                                                                                  |
| node-expand        | triggers when current node open                      | `(data: TreeNodeData, node: TreeNode)`                                                                                                  |
| node-collapse      | triggers when current node close                     | `(data: TreeNodeData, node: TreeNode)`                                                                                                  |

### TreeV2 Slots

| Name           | Description                       | Parámetros                                        |
| -------------- | --------------------------------- | ------------------------------------------------- |
| default        | custom content for tree nodes     | ^[object]`{ node: TreeNode, data: TreeNodeData }` |
| empty ^(2.9.0) | custom content when data is empty | —                                                 |

## Declaraciones de tipo

<details>
  <summary>Mostrar declaraciones</summary>

```ts
type TreeNodeData = Record<string, any>
type TreeKey = string | number
type TreeData = TreeNodeData[]

interface TreeNode {
  key: TreeKey
  level: number
  parent?: TreeNode
  children?: TreeNode[]
  data: TreeNodeData
  disabled?: boolean
  label?: string
  isLeaf?: boolean
  expanded?: boolean
  isEffectivelyChecked?: boolean
}
```

</details>
