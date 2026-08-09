---
title: Rate
lang: es-ES
---

# Rate

Usado para la calificación

## Uso básico

:::demo Rate divide las puntuaciones en varios niveles y estos niveles pueden distinguirse usando diferentes colores de fondo. Por defecto, los colores de fondo son iguales, pero puedes asignarlos para reflejar los tres niveles usando el atributo `colors` y sus dos umbrales pueden ser definidos con `low-treshold` y `high-treshold`. O puede asignarlos con un objeto cuya clave es el umbral entre dos niveles y cuyo valor es el color correspondiente.

rate/basic-usage

:::

## Tamaños

:::demo

rate/sizes

:::

## Media elección permitida

:::demo Añadir la propiedad `allow-half` para permitir la selección de las mitades de estrellas

rate/allow-half

:::

## Con texto

Use texto para indicar la puntuación

:::demo Agregue el atributo `show-text` para mostrar texto a la derecha del componente. Puede asignar textos para las distintas puntuaciones usando `texts`. `texts` es un arreglo cuya longitud debe ser igual a la máxima puntuación `max`.

rate/text

:::

## Limpiable

:::demo Puede restablecer el valor a `0` cuando haga clic en el mismo valor otra vez.

rate/clearable

:::

## Más iconos

Puede utilizar diferentes iconos para distinguir diferentes componentes de velocidad.

:::demo Puede personalizar los iconos pasando a `icons` un arreglo con tres elementos o un objeto que es el umbral entre dos niveles y el valor es el icono correspondiente. En este ejemplo, también usamos `void-icon` para establecer si el icono está seleccionado.

rate/more-icons

:::

## Sólo lectura

La tasa de sólo lectura es para mostrar la puntuación de calificación. La estrella media está soportada.

:::demo Use el atributo `disabled` para hacer que el componente sea de solo lectura. Añada `show-score` para mostrar la puntuación en el lado derecho. Además, puede utilizar el atributo `score-template` para proporcionar una plantilla de puntuación. Debe contener `{value}` y `{value}` será reemplazado con la puntuación de calificación.

rate/readonly

:::

## Estilos personalizados

Ahora puede establecer un estilo personalizado para el componente. Use los lenguajes `css/scss` para cambiar el color global o local. Establecemos algunas variables de color globales: `--el-rate-void-color`, `--el-rate-fill-color`, `--el-rate-disabled-void-color`, `--el-rate-text-color`. Puede usar como: `:root { --el-rate-void-color: red; --el-rate-fill-color: blue; }`.

### Variables por defecto

| Variable                      | Color por defecto             |
| ----------------------------- | ----------------------------- |
| --el-rate-void-color          | var(--el-border-color-darker) |
| --el-rate-fill-color          | #f7ba2a                       |
| --el-rate-disabled-void-color | var(--el-fill-color)          |
| --el-rate-text-color          | var(--el-text-color-primary)  |

## API

### Atributos

| Nombre                      | Descripción                                                                                                                                                                                                                                                          | Tipo                                                                                       | Por defecto                                                        |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------ |
| model-value / v-model       | valor vinculado                                                                                                                                                                                                                                                      | ^[number]                                                                                  | 0                                                                  |
| max                         | puntuación máxima                                                                                                                                                                                                                                                    | ^[number]                                                                                  | 5                                                                  |
| size                        | tamaño de rate                                                                                                                                                                                                                                                       | ^[enum]`'large' \| 'default' \| 'small'`                                                 | —                                                                  |
| disabled                    | si es solo de lectura                                                                                                                                                                                                                                                | ^[boolean]                                                                                 | false                                                              |
| allow-half                  | si escoger media estrella está permitido                                                                                                                                                                                                                             | ^[boolean]                                                                                 | false                                                              |
| low-threshold               | valor del umbral entre nivel bajo y medio. El valor en sí mismo será incluido en el nivel bajo                                                                                                                                                                       | ^[number]                                                                                  | 2                                                                  |
| high-threshold              | valor del umbral entre nivel medio y alto. El valor en sí mismo se incluirá en un nivel alto                                                                                                                                                                         | ^[number]                                                                                  | 4                                                                  |
| colors                      | colores para los iconos. Si se trata de una matriz, debe tener 3 elementos, cada uno de los cuales corresponde a un nivel de puntuación, si se trata de un objeto, la clave debe ser el valor umbral entre dos niveles, y el valor debe ser el color correspondiente | ^[array]`string[]` / ^[object]`Record<number, string>`                               | ['#f7ba2a', '#f7ba2a', '#f7ba2a']                                  |
| void-color                  | color de los iconos no seleccionados                                                                                                                                                                                                                                 | ^[string]                                                                                  | #c6d1de                                                            |
| disabled-void-color         | color para los iconos no seleccionados de solo lectura                                                                                                                                                                                                               | ^[string]                                                                                  | #eff2f7                                                            |
| icons                       | componentes de icono. Si es un array, debe tener 3 elementos, cada uno de los cuales corresponde con un nivel de puntuación, si es un objeto, la clave debe ser el valor de umbral entre dos niveles, y el valor debe ser el componente de icono correspondiente     | ^[array]`string[] \| Component[]` / ^[object]`Record<number, string \| Component>` | [StarFilled, StarFilled, StarFilled]                               |
| void-icon                   | componente de iconos no seleccionados                                                                                                                                                                                                                                | ^[string] / ^[Component]                                                                   | Star                                                               |
| disabled-void-icon          | componente de iconos de solo lectura no seleccionados                                                                                                                                                                                                                | ^[string] / ^[Component]                                                                   | StarFilled                                                         |
| show-text                   | si se muestra texto                                                                                                                                                                                                                                                  | ^[boolean]                                                                                 | false                                                              |
| show-score                  | si quiere mostrar la puntuación actual. show-score y show-text no pueden ser verdaderos al mismo tiempo                                                                                                                                                              | ^[boolean]                                                                                 | false                                                              |
| text-color                  | color de los textos                                                                                                                                                                                                                                                  | ^[string]                                                                                  | ''                                                                 |
| texts                       | array de textos                                                                                                                                                                                                                                                      | ^[array]`string[]`                                                                         | ['Extremely bad', 'Disappointed', 'Fair', 'Satisfied', 'Surprise'] |
| score-template              | plantilla de puntuación                                                                                                                                                                                                                                              | ^[string]                                                                                  | {value}                                                            |
| clearable ^(2.2.18)         | si el valor puede reiniciarse a `0`                                                                                                                                                                                                                                  | ^[boolean]                                                                                 | false                                                              |
| id                          | atributo nativo `id`                                                                                                                                                                                                                                                 | ^[string]                                                                                  | —                                                                  |
| aria-label ^(a11y) ^(2.7.2) | igual que `aria-label` en nativo                                                                                                                                                                                                                                     | ^[string]                                                                                  | —                                                                  |
| label ^(a11y) ^(deprecated) | same as `aria-label` in Rate                                                                                                                                                                                                                                         | ^[string]                                                                                  | —                                                                  |

### Eventos

| Nombre | Descripción                               | Tipo                                    |
| ------ | ----------------------------------------- | --------------------------------------- |
| change | Dispara cuando se cambia el valor de rate | ^[Function]`(value: number) => void` |

### Expuesto

| Nombre            | Descripción              | Tipo                                    |
| ----------------- | ------------------------ | --------------------------------------- |
| setCurrentValue   | fijar valor actual       | ^[Function]`(value: number) => void` |
| resetCurrentValue | restablecer valor actual | ^[Function]`() => void`              |
