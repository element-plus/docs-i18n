---
title: Tree
lang: es-ES
---

# Tree

Muestra un conjunto de datos jerárquicos.

## Uso básico

Estructura básica de árbol.

:::demo

tree/basic

:::

## Seleccionable

Usado para la selección de nodos.

:::demo Este ejemplo también muestra como cargar los datos de forma asíncrona.

tree/selectable

:::

:::warning

When using show-checkbox, since `check-on-click-leaf` is true by default, last tree children's can be checked by clicking their nodes.

:::

## Nodos hoja en modo perezoso (lazy load)

:::demo Los datos de un nodo no son cargados hasta que no es pinchado, así que el árbol no puede predecir si es una hoja. Por eso a cada nodo se le añade el botón de desplegar, y si el nodo es una hoja el botón desaparecerá al pinchar en él. También puede decirle al árbol que el nodo es una hoja de antemano, y así evita que muestre el botón de desplegar.

tree/custom-leaf

:::

## Lazy loading multiple times ^(2.6.3)

:::demo When lazily loading node data remotely, lazy loading may sometimes fail. In this case, you can call reject to keep the node status as is and allow remote loading to continue.

tree/multiple-times-load

:::

## Checkbox desactivados

El checkbox de un nodo se puede poner como desactivado.

:::demo En el ejemplo, la propiedad `disabled` se declara en `defaultProps`, y algunos nodos se ponen como `disabled:true`. Los checkboxes correspondientes son desactivados y no se pueden pinchar.

tree/disabled

:::

## Desplegado o seleccionado por defecto

Los nodos pueden estar desplegados o seleccionados por defecto.

:::demo Utilice `default-expanded-keys` y `default-checked-keys` para establecer los nodos desplegados y seleccionados respectivamente. Tenga en cuenta que para que funcione es necesario que tengan `node-key`. Su valor es el nombre de una clave en el objeto data, y el valor de la clave debe ser único en todo el árbol.

tree/default-state

:::

## Seleccionando nodos

:::demo Este ejemplo muestra como establecer y leer nodos seleccionados. Esto se puede hacer por nodos o por claves. Si lo hace por claves el atributo `node-key` es necesario.

tree/checking-tree

:::

## Contenido personalizado en los nodos

El contenido de los nodos puede ser personalizado, así que puede añadir iconos y botones a su gusto.

:::demo Hay dos maneras de personalizar la plantilla para los nodos de árbol: `render-content` y scoped slot. Utilice `render-content` para asignar una función de renderizado que devuelve el contenido del árbol de nodos. Mire la documentación de node para una introducción detallada a las funciones de renderizado. Si prefiere scoped slot, tendrá acceso a los `nodos` y `datos` en el ámbito de aplicación, representando el objeto TreeNode y los datos del nodo actual respectivamente. Ten en cuenta que la demo de `render-content` no puede ejecutarse en JSFiddle porque no soporta la sintaxis JSX. En un proyecto real `render-content` funcionará si las dependencias son configuradas correctamente.

tree/customized-node

:::

## Clase de nodo personalizado

La clase de nodos de árbol puede ser personalizada

:::demo. Usa `props.class` para construir un nombre de clase de nodos.

tree/custom-node-class

:::

## Filtrado de nodos

Los nodos del árbol se pueden filtrar.

:::demo Invoque el método `filter` de la instancia de Tree para filtrar los nodos. Su parámetro es la palabra de filtrado. Tenga en cuenta que para que funcione es necesario `filter-node-method`, y su valor el método de filtrado.

tree/filtering

:::

## Acordeón

Solo puede ser expandido un nodo del mismo nivel a la vez.

:::demo

tree/accordion

:::

## Arrastrable

Puede arrastrar y soltar nodos de Tree añadiendo un atributo `draggable` .

:::demo

tree/draggable

:::

## Tree API

### Atributos

| Nombre                       | Descripción                                                                                                                                                                                                                                                                                                                                                                  | Tipo                                                      | Por defecto |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- | ----------- |
| data                         | Datos del árbol                                                                                                                                                                                                                                                                                                                                                              | ^[array]`Array<{[key: string]: any}>`               | —           |
| empty-text                   | Texto a mostrar cuando data es void                                                                                                                                                                                                                                                                                                                                          | ^[string]                                                 | —           |
| node-key                     | Identificador único en todo el árbol para los nodos                                                                                                                                                                                                                                                                                                                          | ^[string]                                                 | —           |
| [props](#props)              | Opciones de configuración                                                                                                                                                                                                                                                                                                                                                    | ^[object]                                                 | —           |
| render-after-expand          | si se mostrarán los nodos hijo sólo después de que se desglose por primera vez un nodo padre                                                                                                                                                                                                                                                                                 | ^[boolean]                                                | true        |
| load                         | Método para cargar los datos de subárboles                                                                                                                                                                                                                                                                                                                                   | ^[Function]`(node, resolve, reject) => void`           | —           |
| render-content               | Función de renderizado para los nodos                                                                                                                                                                                                                                                                                                                                        | ^[Function]`(h, { node, data, store }) => void`        | —           |
| highlight-current            | Si el nodo actual está resaltado                                                                                                                                                                                                                                                                                                                                             | ^[boolean]                                                | false       |
| default-expand-all           | Expandir todos los nodos por defecto                                                                                                                                                                                                                                                                                                                                         | ^[boolean]                                                | false       |
| expand-on-click-node         | Si expandir o contraer un nodo al pincharlo, si es false solo se hará al pinchar en la flecha                                                                                                                                                                                                                                                                                | ^[boolean]                                                | true        |
| check-on-click-node          | Si es `false`, el nodo sólo se puede marcar o desmarcar haciendo clic en la casilla de verificación.                                                                                                                                                                                                                                                                         | ^[boolean]                                                | false       |
| check-on-click-leaf ^(2.9.6) | whether to check or uncheck node when clicking on leaf node (last children).                                                                                                                                                                                                                                                                                                 | ^[boolean]                                                | true        |
| auto-expand-parent           | Expandir un nodo padre si el hijo está seleccionado                                                                                                                                                                                                                                                                                                                          | ^[boolean]                                                | true        |
| default-expanded-keys        | Array de claves de los nodos expandidos inicialmente                                                                                                                                                                                                                                                                                                                         | ^[array]`Array<string \| number>`                  | —           |
| show-checkbox                | Si un nodo es seleccionable                                                                                                                                                                                                                                                                                                                                                  | ^[boolean]                                                | false       |
| check-strictly               | El estado de selección de un nodo no afecta a sus padres o hijos, cuando `show-checkbox` es `true`                                                                                                                                                                                                                                                                           | ^[boolean]                                                | false       |
| default-checked-keys         | Array con claves de los nodos seleccionados inicialmente                                                                                                                                                                                                                                                                                                                     | ^[array]`Array<string \| number>`                  | —           |
| current-node-key             | la clave del nodo inicialmente seleccionado                                                                                                                                                                                                                                                                                                                                  | ^[string] / ^[number]                                     | —           |
| filter-node-method           | esta función se ejecutará antes de arrastrar un nodo. si devuelve `false`, el nodo no puede ser arrastrado.                                                                                                                                                                                                                                                                  | ^[Function]`(value, data, node) => boolean`            | —           |
| accordion                    | Si solo un nodo de cada nivel puede expandirse a la vez                                                                                                                                                                                                                                                                                                                      | ^[boolean]                                                | false       |
| indent                       | Indentación horizontal de los nodos en niveles adyacentes, en pixeles                                                                                                                                                                                                                                                                                                        | ^[number]                                                 | 18          |
| icon                         | componente de icono de nodo de árbol personalizado                                                                                                                                                                                                                                                                                                                           | ^[string] / ^[Component]                                  | —           |
| lazy                         | si se trata de un nodo de hoja lazy load, utilizado con el atributo `load`                                                                                                                                                                                                                                                                                                   | ^[boolean]                                                | false       |
| draggable                    | si se habilita la función de drag & drop en los nodos                                                                                                                                                                                                                                                                                                                        | ^[boolean]                                                | false       |
| allow-drag                   | esta función se ejecutará antes de arrastrar un nodo. Si se devuelve `false`, el nodo no puede ser arrastrado                                                                                                                                                                                                                                                                | ^[Function]`(node) => boolean`                         | —           |
| allow-drop                   | esta función se ejecutará al arrastrar y soltar un nodo. si devuelve false, el nodo arrastrando no se puede soltar en el nodo destino. `type` tiene tres valores posibles: 'prev' (insertar el nodo de arrastre antes del nodo de destino), 'inner' (insertar el nodo de arrastre en el nodo de destino) y 'next' (insertar el nodo de arrastre después del nodo de destino) | ^[Function]`(draggingNode, dropNode, type) => boolean` | —           |

### props

| Atributos | Descripción                                                                     | Tipo                                                | Por defecto |
| --------- | ------------------------------------------------------------------------------- | --------------------------------------------------- | ----------- |
| label     | Especifica que clave del objecto nodo se utilizará como label                   | ^[string] / ^[Function]`(data, node) => string`  | —           |
| children  | Especifica que objeto del nodo se utiliza como subárbol                         | ^[string]                                           | —           |
| disabled  | Especifica si el nodo es una hoja, sólo funciona cuando lazy load está activado | ^[string] / ^[Function]`(data, node) => boolean` | —           |
| isLeaf    | elimina un nodo, solo funciona si `node-key` está asignado                      | ^[string] / ^[Function]`(data, node) => boolean` | —           |
| class     | nombre de clase de nodo personalizado                                           | ^[string] / ^[Function]`(data, node) => string`  | —           |

### Expuesto

`Tree` has the following method, which returns the currently selected array of nodes.

| Method              | Descripción                                                                                                          | Parámetros                                                                                                                                                                                                                                                                                                        |
| ------------------- | -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| filter              | filter all tree nodes, filtered nodes will be hidden                                                                 | Accept a parameter which will be used as first parameter for filter-node-method                                                                                                                                                                                                                                   |
| updateKeyChildren   | set new data to node, only works when `node-key` is assigned                                                         | (key, data) Accept two parameters: 1. key of node 2. new data                                                                                                                                                                                                                                                     |
| getCheckedNodes     | If the node can be selected (`show-checkbox` is `true`), it returns the currently selected array of nodes            | (leafOnly, includeHalfChecked) Accept two boolean type parameters: 1. default value is `false`. If the parameter is `true`, it only returns the currently selected array of sub-nodes. 2. default value is `false`. If the parameter is `true`, the return value contains halfchecked nodes                       |
| setCheckedNodes     | set certain nodes to be checked, only works when `node-key` is assigned                                              | (nodes, leafOnly) Accept two parameters: 1. an array of node objects to be checked 2. a boolean parameter. If set to `true`, only the checked status of leaf nodes will be set. The default value is `false`.                                                                                                     |
| getCheckedKeys      | If the node can be selected (`show-checkbox` is `true`), it returns the currently selected array of node's keys      | (leafOnly) Accept a boolean type parameter whose default value is `false`. If the parameter is `true`, it only returns the currently selected array of sub-nodes.                                                                                                                                                 |
| setCheckedKeys      | set certain nodes to be checked, only works when `node-key` is assigned                                              | (keys, leafOnly) Accept two parameters: 1. an array of node's keys to be checked 2. un operador booleano. Si se establece a `true`, sólo se establecerá el estado comprobado de los nodos de hoja. El valor por defecto es `false`.                                                                               |
| setChecked          | set node to be checked or not, only works when `node-key` is assigned                                                | (key/data, checked, deep) Accept three parameters: 1. node's key or data to be checked 2. a boolean typed parameter indicating checked or not. 3. a boolean typed parameter indicating whether to recursively check/uncheck child nodes (since ^(2.14.0), this works regardless of the `check-strictly` setting). |
| getHalfCheckedNodes | If the node can be selected (`show-checkbox` is `true`), it returns the currently half selected array of nodes       | —                                                                                                                                                                                                                                                                                                                 |
| getHalfCheckedKeys  | If the node can be selected (`show-checkbox` is `true`), it returns the currently half selected array of node's keys | —                                                                                                                                                                                                                                                                                                                 |
| getCurrentKey       | return the highlight node's key (null if no node is highlighted)                                                     | —                                                                                                                                                                                                                                                                                                                 |
| getCurrentNode      | return the highlight node's data (null if no node is highlighted)                                                    | —                                                                                                                                                                                                                                                                                                                 |
| setCurrentKey       | set highlighted node by key, only works when `node-key` is assigned                                                  | (key, shouldAutoExpandParent=true) 1. the node's key to be highlighted. If `null`, cancel the currently highlighted node 2. whether to automatically expand parent node                                                                                                                                           |
| setCurrentNode      | set highlighted node, only works when `node-key` is assigned                                                         | (node, shouldAutoExpandParent=true) 1. the node to be highlighted 2. whether to automatically expand parent node                                                                                                                                                                                                  |
| getNode             | get node by data or key                                                                                              | (data) the node's data or key                                                                                                                                                                                                                                                                                     |
| remove              | remove a node, only works when node-key is assigned                                                                  | (data) the node's data or node to be deleted                                                                                                                                                                                                                                                                      |
| append              | append a child node to a given node in the tree                                                                      | (data, parentNode) 1. child node's data to be appended 2. parent node's data, key or node                                                                                                                                                                                                                         |
| insertBefore        | insert a node before a given node in the tree                                                                        | (data, refNode) 1. node's data to be inserted 2. reference node's data, key or node                                                                                                                                                                                                                               |
| insertAfter         | insert a node after a given node in the tree                                                                         | (data, refNode) 1. node's data to be inserted 2. reference node's data, key or node                                                                                                                                                                                                                               |

### Eventos

| Nombre           | Descripción                                               | Parameters                                                                                                                                                                                       |
| ---------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| node-click       | triggers when a node is clicked                           | four parameters: node object corresponding to the node clicked, `node` property of TreeNode, TreeNode itself, event object                                                                       |
| node-contextmenu | triggers when a node is clicked by right button           | four parameters: event, node object corresponding to the node clicked, `node` property of TreeNode, TreeNode itself                                                                              |
| check-change     | triggers when the selected state of the node changes      | three parameters: node object corresponding to the node whose selected state is changed, whether the node is selected, whether node's subtree has selected nodes                                 |
| check            | triggers after clicking the checkbox of a node            | two parameters: node object corresponding to the node that is checked / unchecked, tree checked status object which has four props: checkedNodes, checkedKeys, halfCheckedNodes, halfCheckedKeys |
| current-change   | triggers when current node changes                        | two parameters: node object corresponding to the current node, `node` property of TreeNode                                                                                                       |
| node-expand      | triggers when current node open                           | three parameters: node object corresponding to the node opened, `node` property of TreeNode, TreeNode itself                                                                                     |
| node-collapse    | triggers when current node close                          | three parameters: node object corresponding to the node closed, `node` property of TreeNode, TreeNode itself                                                                                     |
| node-drag-start  | triggers when dragging starts                             | two parameters: node object corresponding to the dragging node, event.                                                                                                                           |
| node-drag-enter  | triggers when the dragging node enters another node       | three parameters: node object corresponding to the dragging node, node object corresponding to the entering node, event.                                                                         |
| node-drag-leave  | triggers when the dragging node leaves a node             | three parameters: node object corresponding to the dragging node, node object corresponding to the leaving node, event.                                                                          |
| node-drag-over   | triggers when dragging over a node (like mouseover event) | three parameters: node object corresponding to the dragging node, node object corresponding to the dragging over node, event.                                                                    |
| node-drag-end    | triggers when dragging ends                               | four parameters: node object corresponding to the dragging node, node object corresponding to the dragging end node (may be `undefined`), node drop type (before / after / inner), event.        |
| node-drop        | triggers after the dragging node is dropped               | four parameters: node object corresponding to the dragging node, node object corresponding to the dropped node, node drop type (before / after / inner), event.                                  |

### Slots

| Name           | Description                       | Parámetros                                                                                 |
| -------------- | --------------------------------- | ------------------------------------------------------------------------------------------ |
| default        | custom content for tree nodes     | ^[object]`{ node: UnwrapRef<RootTreeType['root']>, data: Tree \| TreeOptionProps }` |
| empty ^(2.3.4) | custom content when data is empty | —                                                                                          |

## Declaraciones de tipo

<details>
  <summary>Mostrar declaraciones</summary>

```ts
interface RootTreeType {
  root: Ref<Node>
  // ...
}

// UnwrapRef<RootTreeType['root']> => Node
type Node = {
  canFocus: boolean
  checked: boolean
  childNodes: Node[]
  data: TreeNodeData
  expanded: boolean
  id: number
  indeterminate: boolean
  isCurrent: boolean
  isEffectivelyChecked: boolean
  isLeaf?: boolean
  isLeafByUser?: boolean
  level: number
  loaded: boolean
  loading: boolean
  parent: Node | null
  store: TreeStore
  text: string | null
  visible: boolean
}

// TreeNodeData => Tree / TreeOptionProps
// Tree type is your prop type.
// TreeOptionProps is default prop type
interface TreeOptionProps {
  children?: string
  label?: string | ((data: TreeNodeData, node: Node) => string)
  disabled?: string | ((data: TreeNodeData, node: Node) => boolean)
  isLeaf?: string | ((data: TreeNodeData, node: Node) => boolean)
  class?: (
    data: TreeNodeData,
    node: Node
  ) => string | { [key: string]: boolean }
}
```

</details>
