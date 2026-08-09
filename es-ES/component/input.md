---
title: Input
lang: es-ES
---

# Input

Ingresa datos usando el ratón o teclado.

## Uso básico

:::demo

input/basic

:::

## Deshabilitar

:::demo Deshabilite el Input con el atributo `disabled`.

input/disabled

:::

## Limpiable

:::demo Marque que el input puede ser limpiable con el atributo `clearable`. After version ^(2.13.4), the clearable feature is also available for textarea type of Input.

input/clearable

:::

## Custom Clear Icon ^(2.11.0)

:::demo You can customize the clear icon by setting the `clear-icon` attribute.

input/clear-icon

:::

## Formato

Muestre el valor, según la situación, con `formatter`, y normalmente se usa `parser` al mismo tiempo.

:::demo

input/formatter

:::

## Contraseña

:::demo Puede hacer un input de contraseña conmutable con el atributo `show-password`. Since ^(2.13.6), the `password-icon` slot is supported to override the default icon.

input/password

:::

## Input con icono

Añada un icono para indicar el tipo de Input.

:::demo Para añadir iconos en el Input, puede utilizar los atributos `prefix-icon` y `suffix-icon`. Además, los slots con nombre `prefix` y `suffix` también funcionan.

input/with-icon

:::

## Textarea

Redimensionable para introducir múltiples líneas de información de texto. Agregue el atributo `type="textarea"` para cambiar el `input` al tipo nativo `textarea`.

:::demo Controle la altura ajustando la propiedad `rows`.

input/textarea

:::

## Textarea de tamaño automático

El ajuste de la propiedad `autosize` en el tipo de Input textarea hace que la altura se ajuste automáticamente en función del contenido. Se pueden proporcionar opciones en un objeto para `autosize` y especificar el número mínimo y máximo de líneas que el textarea puede ajustar automáticamente.

:::demo

input/auto-sizing-textarea

:::

## Mezclando elementos con input

Añada un elemento antes o después del input, generalmente será una etiqueta o un botón.

:::demo Utilice el `slot` para seleccionar si el elemento se colocara antes (prepend) o después (append) del Input.

input/mixed-input

:::

## Tamaños

:::demo Añada el atributo `size` para cambiar el tamaño del Input. Además del tamaño predeterminado, hay otras dos opciones: `large`, `small`.

input/various-size

:::

## Limitar el tamaño

:::demo `maxlength` and `minlength` attributes of input, they declare a limit on the number of characters a user can input. The "number of characters" is measured using JavaScript string length.Setting the `maxlength` prop for a text or textarea type of Input can limit the length of input value, allows you to show word count by setting `show-word-limit` to `true` at the same time. In ^(2.11.5), You can set `word-limit-position` to `outside` to display the word count outside the input.

input/length-limiting

:::

## Count graphemes ^(2.13.7)

:::demo Set `count-graphemes` to calculate text length. If it's set, native `maxlength` and `minlength` won't be used.

input/count-graphemes

:::

:::tip

**Browser Support & Fallback Strategy**

When using the `count-graphemes` prop, the component employs the following approach:

- **Primary**: Uses `Intl.Segmenter` API (Chrome 87+, Firefox 125+, Safari 14.1+) for proper grapheme cluster handling. This correctly handles complex emoji, combining marks, and Zero Width Joiner sequences.

- **Fallback**: Older browsers fall back to `Array.from()` for code-point based iteration. Note that this may split multi-codepoint grapheme sequences (e.g., emoji with skin tone modifiers).

When implementing your own `count-graphemes` function, consider using `Intl.Segmenter` if you need robust support for complex unicode characters.

:::

## API

### Atributos

| Nombre                        | Descripción                                                                                                                                                                                                                                                                         | Tipo                                                                                                       | Por defecto |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ----------- |
| type                          | type of input, see more in [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Form_%3Cinput%3E_types)                                                                                                                                                            | ^[string]`'text' \| 'textarea' \| 'number' \| 'password' \| 'email' \| 'search' \| 'tel' \|  'url'` | text        |
| model-value / v-model         | valor enlazado                                                                                                                                                                                                                                                                      | ^[string] / ^[number]                                                                                      | —           |
| model-modifiers ^(2.11.5)     | v-model modifiers, reference [Vue modifiers](https://vuejs.org/guide/essentials/forms.html#modifiers)                                                                                                                                                                               | ^[object]`{ lazy?: true, number?: true, trim?: true }`                                                     | —           |
| maxlength                     | same as `maxlength` in native input                                                                                                                                                                                                                                                 | ^[string] / ^[number]                                                                                      | —           |
| minlength                     | igual que `minlength` en el input nativo                                                                                                                                                                                                                                            | ^[string] / ^[number]                                                                                      | —           |
| show-word-limit               | si se muestra el contador de palabras, solamente funciona cuando `type` es 'text' o 'textarea'                                                                                                                                                                                      | ^[boolean]                                                                                                 | false       |
| word-limit-position ^(2.11.5) | word count position, valid when `show-word-limit` is true                                                                                                                                                                                                                           | ^[enum]`'inside' \| 'outside'`                                                                            | "inside"    |
| placeholder                   | placeholder del Input                                                                                                                                                                                                                                                               | ^[string]                                                                                                  | —           |
| clearable                     | si mostrar el botón limpiar, solo funciona cuando `type` no es 'textarea'                                                                                                                                                                                                           | ^[boolean]                                                                                                 | false       |
| clear-icon ^(2.11.0)          | personaliza el componente de icono de limpieza                                                                                                                                                                                                                                      | ^[string] / ^[object]`Component`                                                                           | CircleClose |
| formatter                     | especifica el formato del valor presentado en el input.(solo funciona cuando `type` es 'text')                                                                                                                                                                                      | ^[Function]`(value: string \| number) => string`                                                       | —           |
| parser                        | especifica el valor extraído del input formateado.(solo funciona cuando `type` es 'text')                                                                                                                                                                                           | ^[Function]`(value: string) => string`                                                                  | —           |
| show-password                 | si debe mostrar la posibilidad de conmutación en el input de tipo password                                                                                                                                                                                                          | ^[boolean]                                                                                                 | false       |
| disabled                      | si esta deshabilitado                                                                                                                                                                                                                                                               | ^[boolean]                                                                                                 | false       |
| size                          | tamaño del input, esto funciona cuando `type` no es 'textarea'                                                                                                                                                                                                                      | ^[enum]`'large' \| 'default' \| 'small'`                                                                 | —           |
| prefix-icon                   | componente de icono prefijo                                                                                                                                                                                                                                                         | ^[string] / ^[Component]                                                                                   | —           |
| suffix-icon                   | componente de icono sufijo                                                                                                                                                                                                                                                          | ^[string] / ^[Component]                                                                                   | —           |
| rows                          | número de filas, solo funciona cuando `type` es 'textarea'                                                                                                                                                                                                                          | ^[number]                                                                                                  | 2           |
| autosize                      | si textarea tiene una altura adaptativa, solo funciona cuando `type` es 'textarea'. Puede aceptar un objeto, por ejemplo, `{ minRows: 2, maxRows: 6 }`                                                                                                                              | ^[boolean] / ^[object]`{ minRows?: number, maxRows?: number }`                                             | false       |
| autocomplete                  | igual que `autocomplete` en el input nativo                                                                                                                                                                                                                                         | ^[string]                                                                                                  | off         |
| name                          | como `name` en el input nativo                                                                                                                                                                                                                                                      | ^[string]                                                                                                  | —           |
| readonly                      | igual que `readonly` en el input nativo                                                                                                                                                                                                                                             | ^[boolean]                                                                                                 | false       |
| max                           | igual que `max` en el input nativo                                                                                                                                                                                                                                                  | —                                                                                                          | —           |
| min                           | igual que `min` en el input nativo                                                                                                                                                                                                                                                  | —                                                                                                          | —           |
| step                          | igual que `step` en el input nativo                                                                                                                                                                                                                                                 | —                                                                                                          | —           |
| resize                        | controlar la resizabilidad                                                                                                                                                                                                                                                          | ^[enum]`'none' \| 'both' \| 'horizontal' \| 'vertical'`                                                 | —           |
| autofocus                     | igual que `autofocus` en el input nativo                                                                                                                                                                                                                                            | ^[boolean]                                                                                                 | false       |
| form                          | igual que `form` en el input nativo                                                                                                                                                                                                                                                 | `string`                                                                                                   | —           |
| aria-label ^(a11y) ^(2.7.2)   | igual que `aria-label` en el input nativo                                                                                                                                                                                                                                           | ^[string]                                                                                                  | —           |
| tabindex                      | orden de tabulación para el Input                                                                                                                                                                                                                                                   | ^[string] / ^[number]                                                                                      | —           |
| validate-event                | si se debe lanzar la validación de formulario                                                                                                                                                                                                                                       | ^[boolean]                                                                                                 | true        |
| input-style                   | el estilo del elemento input o elemento textarea                                                                                                                                                                                                                                    | ^[string] / ^[object]`CSSProperties \| CSSProperties[] \| string[]`                                      | {}          |
| label ^(a11y) ^(deprecated)   | same as `aria-label` in native input                                                                                                                                                                                                                                                | ^[string]                                                                                                  | —           |
| inputmode ^(2.10.3)           | same as `inputmode` in native input                                                                                                                                                                                                                                                 | ^[string]                                                                                                  | —           |
| count-graphemes ^(2.13.7)     | custom function to count graphemes; when set, native `maxlength`/`minlength` constraints are bypassed. Component uses `Intl.Segmenter` (Chrome 87+, Firefox 125+, Safari 14.1+) for proper grapheme clustering; older browsers fall back to `Array.from()` for code-point iteration | ^[Function]`(value: string) => number`                                                                  | —           |

### Eventos

| Nombre            | Descripción                                                                                              | Tipo                                                                                                 |
| ----------------- | -------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| blur              | se dispara cuando el input pierde el foco                                                                | ^[Function]`(event: FocusEvent) => void`                                                          |
| focus             | se lanza cuando el input se enfoca                                                                       | ^[Function]`(event: FocusEvent) => void`                                                          |
| change            | se dispara cuando el input pierde el foco o el usuario presiona Enter, solo si el modelValue ha cambiado | ^[Function]`(value: string \| number, evt?: Event) => void`                                      |
| input             | se dispara cuando el valor del input cambia                                                              | ^[Function]`(value: string \| number) => void`                                                   |
| clear             | se dispara cuando el input se borra haciendo clic en el botón de borrar                                  | ^[Function]`(evt?: MouseEvent) => void (After version 2.13.4, the evt parameter can be received)` |
| keydown           | triggers when a key is pressed down                                                                      | ^[Function]`(event: KeyboardEvent \| Event) => void`                                             |
| mouseleave        | triggers when the mouse leaves the Input element                                                         | ^[Function]`(event: MouseEvent) => void`                                                          |
| mouseenter        | triggers when the mouse enters the Input element                                                         | ^[Function]`(event: MouseEvent) => void`                                                          |
| compositionstart  | triggers when the composition starts                                                                     | ^[Function]`(event: CompositionEvent) => void`                                                    |
| compositionupdate | triggers when the composition is updated                                                                 | ^[Function]`(event: CompositionEvent) => void`                                                    |
| compositionend    | triggers when the composition ends                                                                       | ^[Function]`(event: CompositionEvent) => void`                                                    |

### Slots

| Nombre                  | Descripción                                                                                                           |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------- |
| prefix                  | contenido como prefijo del input, solo funciona cuando `type` no es 'textarea'                                        |
| suffix                  | contenido como sufijo del input, solo funciona cuando `type` no es 'textarea'                                         |
| prepend                 | contenido a añadir antes del input, solo funciona cuando `type` no es 'textarea'                                      |
| append                  | contenido para añadir después del input solo funciona cuando `type` no es 'textarea'                                  |
| password-icon ^(2.13.6) | content as Input password icon, only works when `show-password` is true. The scope variable is `{ visible: boolean }` |

### Expuesto

| Nombre                    | Descrición                      | Tipo                                                           |
| ------------------------- | ------------------------------- | -------------------------------------------------------------- |
| blur                      | quita el foco en el input       | ^[Function]`() => void`                                     |
| clear                     | borra contenido del input       | ^[Function]`() => void`                                     |
| focus                     | coloca el foco en el input      | ^[Function]`() => void`                                     |
| input                     | Elemento HTML input             | ^[object]`Ref<HTMLInputElement>`                         |
| ref                       | Elemento HTML, input o textarea | ^[object]`Ref<HTMLInputElement \| HTMLTextAreaElement>` |
| resizeTextarea            | redimensiona textarea           | ^[Function]`() => void`                                     |
| select                    | selecciona el texto del input   | ^[Function]`() => void`                                     |
| textarea                  | Elemento HTML textarea          | ^[object]`Ref<HTMLTextAreaElement>`                      |
| textareaStyle             | estilo de textarea              | ^[object]`Ref<StyleValue>`                               |
| isComposing ^(2.8.0)      | is input composing              | ^[object]`Ref<boolean>`                                  |
| passwordVisible ^(2.13.7) | whether the password is visible | ^[object]`Ref<boolean>`                                  |

## FAQ

#### Why is the width of the ElInput component expanded by clearable?

Typical issue: [#7287](https://github.com/element-plus/element-plus/issues/7287)

PS: Since the ElInput component does not have a default width, when the clearable icon is displayed, the width of the component will be expanded, which can be solved by setting width.

```vue
<el-input v-model="input" clearable style="width: 200px" />
```
