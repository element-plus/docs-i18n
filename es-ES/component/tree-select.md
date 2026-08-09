---
title: TreeSelect
lang: es-ES
---

# TreeSelect

El selector de árbol del menú desplegable, combina las funciones de los componentes `el-tree` y `el-select`.

## Uso básico

Selector para estructuras de árbol.

:::demo

tree-select/basic

:::

## Seleccionar cualquier nivel

Al usar el atributo `check-strictly=true`, cualquier nodo puede ser marcado, de lo contrario solo se soportan los nodos de hoja.

:::tip

Cuando se utiliza `show-checkbox`, ya que `check-on-click-node` es false por defecto, solo se puede seleccionar marcando, se puede establecer este valor a true, y luego hacer clic en el nodo para seleccionar.

:::

:::demo

tree-select/check-strictly

:::

:::warning

When using show-checkbox, since `check-on-click-leaf` is true by default, last tree children's can be checked by clicking their nodes.

:::

## Selección múltiple

Selección múltiple usando clics o casillas de verificación.

:::demo

tree-select/multiple

:::

## Selección deshabilitada

Desactivar opciones usando el campo disabled.

:::demo

tree-select/disabled

:::

## Filtrable

Usar métodos de filtrado de palabras clave o de filtrado personalizado. `filterMethod` puede personalizar el método de filtrado para los datos, `filterNodeMethod` puede personalizar el método de filtrado para el nodo de datos.

:::demo

tree-select/filterable

:::

## Contenido personalizado

Contenido personalizado de nodos de árbol.

:::demo

tree-select/slots

:::

## Carga lenta

Carga perezosa de nodos de árbol, adecuada para listas de datos grandes.

:::demo

tree-select/lazy

:::

## Use node-key attribute

By default the `modelValue` is looking for the `value` key. For a different data structure `node-key` must be provided to work normally.

:::tip

1. `node-key` should be unique across the whole tree.
2. `value-key` have the same objective as `node-key`.
3. Contrary to the select component, the tree-select can't retrieve an object value.

:::

:::demo

tree-select/node-key

:::

## API

### Atributos

Puesto que este componente combina las funciones de los componentes `el-tree` y `el-select`, las propiedades originales no han sido cambiadas, por lo que no hay repetición aquí, por favor vaya al componente original para ver la documentación.

| Attributes                              | Expuesto                             | Eventos                             | Slots                              |
| --------------------------------------- | ------------------------------------ | ----------------------------------- | ---------------------------------- |
| [tree](./tree.md#attributes)            | [tree](./tree.md#exposes)            | [tree](./tree.md#events)            | [tree](./tree.md#slots)            |
| [select](./select.md#select-attributes) | [select](./select.md#select-exposes) | [select](./select.md#select-events) | [select](./select.md#select-slots) |

#### Atributos propios

| Nombre               | Descripción                                                                                                                                         | Tipo                    | Por defecto |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- | ----------- |
| cache-data ^(2.2.26) | Los datos almacenados en caché del nodo perezoso, la estructura es la misma que los datos, usados para obtener la etiqueta de los datos descargados | ^[array]`CacheOption[]` | []          |

### Expuesto

:::warning

Expose methods under tree and select component has been **deprecated**, and **will be** removed in ^(3.0.0), please use them under their component layer: `tree` and `select`.

:::

| Nombre del slot                      | Descripcíon                                                                                                                         | Tipo                                                                                                                                                                                                                                                                                                                         |
| ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| treeRef ^(2.11.3)                    | Tree component instance                                                                                                             | `TreeInstance`                                                                                                                                                                                                                                                                                                               |
| selectRef ^(2.11.3)                  | Select component instance                                                                                                           | `SelectInstance`                                                                                                                                                                                                                                                                                                             |
| filter ^(deprecated)                 | Esta función se ejecutará en cada nodo cuando se use el método filtrar, si devuelve `false` el nodo se oculta                       | Acepta un parámetro que será usado como primer parámetro para el método filter-node-method                                                                                                                                                                                                                                   |
| updateKeyChildren ^(deprecated)      | dos parámetros: objeto nodo que se corresponde al nodo actual y propiedad `node` del TreeNode                                       | (key, data)Acepta dos parámetros: 1. clave del nodo 2. nuevo dato                                                                                                                                                                                                                                                            |
| getCheckedNodes ^(deprecated)        | Si el nodo puede ser seleccionado (`show-checkbox` es `true`), devuelve el array de nodos actualmente seleccionado                  | (leafOnly, includeHalfChecked) Acepta dos parámetros de tipo booleano: 1. el valor por defecto es `false`. Si el parámetro es `true`, sólo devuelve el array de subnodos actualmente seleccionado. 2. el valor por defecto es `false`. Si el parámetro es `true`, el valor de retorno contiene nodos halfchecked.            |
| setCheckedNodes ^(deprecated)        | establece ciertos nodos para ser verificados, solo funciona cuando `node-key` es asignado                                           | un array de nodos a ser verificados                                                                                                                                                                                                                                                                                          |
| getCheckedKeys ^(deprecated)         | Si el nodo puede ser seleccionado (`show-checkbox` es `true`), devuelve el array de claves de nodo seleccionados                    | (leafOnly) Acepta un parámetro de tipo booleano cuyo valor por defecto es `false`. Si el parámetro es `true`, sólo devuelve el array de subnodos actualmente seleccionado.                                                                                                                                                   |
| setCheckedKeys ^(deprecated)         | establece ciertos nodos para ser verificados, solo funciona cuando `node-key` es asignado                                           | (keys, leafOnly) Acepta dos parametros: 1. un array de claves 2. un operador booleano. Si se establece a `true`, sólo se establecerá el estado comprobado de los nodos de hoja. El valor por defecto es `false`.                                                                                                             |
| setChecked ^(deprecated)             | establece nodo para ser comprobado o no, solo funciona cuando `node-key` es asignado                                                | (key/data, checked, deep) Acepta tres parámetros: 1. la clave o dato del nodo a ser seleccionado 2. un parámetro tipo booleano que indica chequeado o no. 3. a boolean typed parameter indicating whether to recursively check/uncheck child nodes (since ^(2.14.0), this works regardless of the `check-strictly` setting). |
| getHalfCheckedNodes ^(deprecated)    | Si el nodo puede ser seleccionado (`show-checkbox` es `true`), devuelve el array de nodos actualmente medio seleccionado            | —                                                                                                                                                                                                                                                                                                                            |
| getHalfCheckedKeys ^(deprecated)     | Si el nodo puede ser seleccionado (`show-checkbox` es `true`), devuelve el array de claves de nodos actualmente medio seleccionados | —                                                                                                                                                                                                                                                                                                                            |
| getCurrentKey ^(deprecated)          | devuelve el nodo por el dato o la clave                                                                                             | —                                                                                                                                                                                                                                                                                                                            |
| getCurrentNode ^(deprecated)         | (data) los datos del nodo o nodo a borrar                                                                                           | —                                                                                                                                                                                                                                                                                                                            |
| setCurrentKey ^(deprecated)          | establecer nodo resaltado por clave, solo funciona cuando `node-key` es asignado                                                    | (key, shouldAutoExpandParent=true) 1. la clave del nodo a ser resaltado. Si es `null`, cancela los nodos actualmente resaltados 2. si expandir automáticamente el nodo padre                                                                                                                                                 |
| setCurrentNode ^(deprecated)         | establecer nodo resaltado, solo funciona cuando `node-key` es asignado                                                              | (node, shouldAutoExpandParent=true) 1. nodo a ser resaltado 2. si expandir automáticamente el nodo padre                                                                                                                                                                                                                     |
| getNode ^(deprecated)                | (data) los datos o clave del nodo                                                                                                   | (data) los datos o clave del nodo                                                                                                                                                                                                                                                                                            |
| remove ^(deprecated)                 | elimina un nodo, solo funciona cuando se asigna node-key                                                                            | (data) los datos del nodo o el nodo a ser borrad                                                                                                                                                                                                                                                                             |
| append ^(deprecated)                 | añadir un nodo hijo a un nodo determinado del árbol                                                                                 | (data, parentNode) 1. los datos del nodo hijo que se añadirán 2. los datos del nodo padre, clave o nodo                                                                                                                                                                                                                      |
| insertBefore ^(deprecated)           | insertar un nodo antes de un nodo dado en el árbol                                                                                  | (data, refNode) 1. Datos del nodo que se insertarán 2. Datos del nodo de referencia, clave o nodo                                                                                                                                                                                                                            |
| insertAfter ^(deprecated)            | insertar un nodo después de un nodo dado en el árbol                                                                                | (data, refNode) 1. Datos del nodo que se insertarán 2. Datos del nodo de referencia, clave o nodo                                                                                                                                                                                                                            |
| focus ^(deprecated)                  | Foco en el componente input                                                                                                         | ^[Function]`() => void`                                                                                                                                                                                                                                                                                                   |
| blur ^(deprecated)                   | Quita el focus del componente y oculta el dropdown                                                                                  | ^[Function]`() => void`                                                                                                                                                                                                                                                                                                   |
| selectedLabel ^(2.8.5) ^(deprecated) | get the currently selected label                                                                                                    | ^[object]`ComputedRef<string \| string[]>`                                                                                                                                                                                                                                                                            |

## Declaraciones de tipo

<details>
  <summary>Mostrar declaraciones</summary>

```ts
type CacheOption = {
  value: string | number | boolean | object
  currentLabel: string | number
  isDisabled: boolean
}
```

</details>
