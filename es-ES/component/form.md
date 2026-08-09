---
title: Form
lang: es-ES
---

# Formulario

El formulario consiste en `input`, `radio`, `select`, `checkbox` y así sucesivamente. Con el formulario, usted puede recoger, verificar y enviar datos.

:::tip

El componente ha sido actualizado con un diseño flex para reemplazar el antiguo diseño flotante.

:::

## Formulario básico

Incluye todo tipo de entradas, tales como `input`, `select`, `radio` y `checkbox`.

:::demo En cada componente `form`, necesita un campo `form-item` que es el contenedor del ítem.

form/basic-form

:::

:::tip

[W3C](https://www.w3.org/MarkUp/html-spec/html-spec_8.html#SEC8.2) reglamenta esto

> <i><i>Cuando solo hay un campo de entrada de texto de una sola línea en un formulario, el agente de usuario debe aceptar Enter en ese campo como una solicitud de envío del formulario.</i>.
</i>
Para evitar este comportamiento, puede añadir `@submit.prevent` en `<el-form>`.

:::

## Formulario inline

Cuando el espacio vertical es limitado y el formulario es relativamente simple, puede ponerlo en una única línea.

:::demo Set the `inline` attribute to `true` and the form will be inline.

form/inline-form

:::

## Alineación

Depending on your design, there are several different ways to align your label element.

You can set `label-position` of `el-form-item` separately ^(2.7.7). If the value is empty, the `label-position` of `el-form` is used.

:::demo The `label-position` attribute decides how labels align, it can be `top` or `left`. When set to `top`, labels will be placed at the top of the form field.

form/alignment

:::

## Validación

Form component allows you to verify your data, helping you find and correct errors.

:::demo Just add the `rules` attribute for `Form` component, pass validation rules, and set `prop` attribute for `FormItem` as a specific key that needs to be validated. See more information at [async-validator](https://github.com/yiminghe/async-validator).

form/validation

:::

## Reglas personalizadas de validación

This example shows how to customize your own validation rules to finish a two-factor password verification.

:::demo Here we use `status-icon` to reflect validation result as an icon.

form/custom-validation

:::

:::tip

Custom validate callback function must be called. See more advanced usage at [async-validator](https://github.com/yiminghe/async-validator).

:::

## Añadir/Eliminar validaciones del elemento del formulario

:::demo In addition to passing all validation rules at once on the form component, you can also pass the validation rules or delete rules on a single form field dynamically.

form/form-items

:::

## Validación numérica

:::demo Number Validate need a `.number` modifier added on the input `v-model` binding，it's used to transform the string value to the number which is provided by Vue.

form/number-validate

:::

:::tip

When an `el-form-item` is nested in another `el-form-item`, its label width will be `0`. You can set `label-width` on that `el-form-item` if needed.

:::

## Control de tamaño

All components in a Form inherit their `size` attribute from that Form. Similarly, FormItem also has a `size` attribute.

:::demo Still you can fine tune each component's `size` if you don't want that component to inherit its size from From or FormItem.

form/size-control

:::

## Accesibilidad

When only a single input (or related control such as select or checkbox) is inside of a `el-form-item`, the form item's label will automatically be attached to that input. However, if multiple inputs are inside of the `el-form-item`, the form item will be assigned the [WAI-ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) role of [group](https://www.w3.org/TR/wai-aria/#group) instead. In this case, it is your responsibility to assign assistive labels to the individual inputs.

:::demo

form/accessibility

:::

## API del Formulario

### Form Attributes

| Nombre                            | Descripción                                                                                                                                                                                                                                  | Tipo                                              | Por defecto |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------- | ----------- |
| model                             | Datos del componente de formulario.                                                                                                                                                                                                          | ^[object]`Record<string, any>`              | —           |
| rules                             | Reglas de validación.                                                                                                                                                                                                                        | ^[object]`FormRules`                              | —           |
| inline                            | Si el formulario es inline.                                                                                                                                                                                                                  | ^[boolean]                                        | false       |
| label-position                    | Posición de la etiqueta. Si se establece en `'left'` o `'right'`, se necesita definir la prop`label-width`.                                                                                                                                  | ^[enum]`'left' \| 'right' \| 'top'`             | right       |
| label-width                       | Ancho de la etiqueta, ej.: `'50px'`. Todos los componentes del formulario que sean hijos directos heredaran este valor. se puede usar `auto`.                                                                                                | ^[string] / ^[number]                             | ''          |
| label-suffix                      | Sufijo de la etiqueta.                                                                                                                                                                                                                       | ^[string]                                         | ''          |
| hide-required-asterisk            | Si los campos obligatorios deben tener un asterisco rojo (estrella) al lado de sus etiquetas.                                                                                                                                                | ^[boolean]                                        | false       |
| require-asterisk-position         | Posición del asterisco.                                                                                                                                                                                                                      | ^[enum]`'left' \| 'right'`                       | left        |
| show-message                      | Si mostrar o no el mensaje de error.                                                                                                                                                                                                         | ^[boolean]                                        | true        |
| inline-message                    | Si mostrar el mensaje de error en línea con el elemento del formulario.                                                                                                                                                                      | ^[boolean]                                        | false       |
| status-icon                       | Si se muestra un icono que indique el resultado de la validación.                                                                                                                                                                            | ^[boolean]                                        | false       |
| validate-on-rule-change           | Si se desencadena la validación cuando la prop `rules` cambia.                                                                                                                                                                               | ^[boolean]                                        | true        |
| size                              | Controla el tamaño de los componentes en este formulario.                                                                                                                                                                                    | ^[enum]`'' \| 'large' \| 'default' \| 'small'` | —           |
| disabled                          | Deshabilitar o no todos los componentes en este formulario. Before ^(2.12.0), if set to `true`, it will override the `disabled` prop of the inner component. After ^(2.12.0), the configuration of the internal components takes precedence. | ^[boolean]                                        | false       |
| scroll-to-error                   | Cuando la validación falla, desplácese a la primera entrada del formulario de error.                                                                                                                                                         | ^[boolean]                                        | false       |
| scroll-into-view-options ^(2.3.2) | Cuando la validación falla, se desplaza al primer elemento de error basado en la opción scrollIntoView. [scrollIntoView](https://developer.mozilla.org/es/docs/Web/API/Element/scrollIntoView).                                              | ^[object]`ScrollIntoViewOptions` / ^[boolean]     | true        |

### Form Events

| Name     | Descripción                             | Tipo                                                                            |
| -------- | --------------------------------------- | ------------------------------------------------------------------------------- |
| validate | triggers after a form item is validated | ^[Function]`(prop: FormItemProp, isValid: boolean, message: string) => void` |

### Form Slots

| Nombre  | Descripción               | Subtags  |
| ------- | ------------------------- | -------- |
| default | customize default content | FormItem |

### Form Exposes

| Nombre                     | Descripción                                                                                          | Tipo                                                                                                                                         |
| -------------------------- | ---------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| validate                   | Validar todo el formulario. Recibe un callback o devuelve `Promise`.                                 | ^[Function]`(callback?: FormValidateCallback) => Promise<void>`                                                                     |
| validateField              | Validar campos específicos.                                                                          | ^[Function]`(props?: Arrayable<FormItemProp> \| undefined, callback?: FormValidateCallback \| undefined) => FormValidationResult` |
| resetFields                | Restablece los campos especificados y elimina el resultado de la validación.                         | ^[Function]`(props?: Arrayable<FormItemProp> \| undefined) => void`                                                                |
| scrollToField              | Desplazarse hasta los campos especificados.                                                          | ^[Function]`(prop: FormItemProp) => void`                                                                                                 |
| clearValidate              | Clear validation messages for all or specified fields.                                               | ^[Function]`(props?: Arrayable<FormItemProp> \| undefined) => void`                                                                |
| fields ^(2.7.3)            | Get all fields context.                                                                              | ^[array]`FormItemContext[]`                                                                                                                  |
| getField ^(2.10.2)         | Get a field context.                                                                                 | ^[Function]`(prop: FormItemProp) => FormItemContext \| undefined`                                                                        |
| setInitialValues ^(2.13.1) | Set initial values for form fields. When `resetFields` is called, fields will reset to these values. | ^[Function]`(initModel: Record<string, any>) => void`                                                                               |

## FormItem API

### FormItem Attributes

| Nombre                  | Descripción                                                                                                                                                            | Type                                                   | Default |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ | ------- |
| prop                    | A key of `model`. It could be a path of the property (e.g `a.b.0` or `['a', 'b', '0']`). In the use of `validate` and `resetFields` method, the attribute is required. | ^[string] / ^[string&#91;&#93;]                        | —       |
| label                   | Label text.                                                                                                                                                            | ^[string]                                              | —       |
| label-position ^(2.7.7) | Position of item label. If set to `'left'` or `'right'`, `label-width` prop is also required. Default extend `label-position` of `form`.                               | ^[enum]`'left' \| 'right' \| 'top'`                  | ''      |
| label-width             | Width of label, e.g. `'50px'`. `'auto'` is supported.                                                                                                                  | ^[string] / ^[number]                                  | —       |
| required                | Whether the field is required or not, will be determined by validation rules if omitted.                                                                               | ^[boolean]                                             | —       |
| rules                   | Validation rules of form, see the [following table](#formitemrule), more advanced usage at [async-validator](https://github.com/yiminghe/async-validator).             | ^[object]`Arrayable<FormItemRule>`               | —       |
| error                   | Field error message, set its value and the field will validate error and show this message immediately.                                                                | ^[string]                                              | —       |
| show-message            | Whether to show the error message.                                                                                                                                     | ^[boolean]                                             | true    |
| inline-message          | Inline style validate message.                                                                                                                                         | ^[boolean]                                             | false   |
| size                    | Control the size of components in this form-item.                                                                                                                      | ^[enum]`'' \| 'large' \| 'default' \| 'small'`      | —       |
| for                     | Same as for in native label.                                                                                                                                           | ^[string]                                              | —       |
| validate-status         | Validation state of formItem.                                                                                                                                          | ^[enum]`'' \| 'error' \| 'validating' \| 'success'` | —       |

#### Reglas de los componentes del formulario

| Nombre  | Descripción                     | Tipo                         | Por defecto |
| ------- | ------------------------------- | ---------------------------- | ----------- |
| trigger | How the validator is triggered. | ^[enum]`'blur' \| 'change'` | —           |

:::tip

If you don't want to trigger the validator based on input events, set the `validate-event` attribute as `false` on the corresponding input type components (`<el-input>`, `<el-radio>`, `<el-select>`, ...).

:::

### FormItem Slots

| Nombre  | Descripción                                   | Tipo                         |
| ------- | --------------------------------------------- | ---------------------------- |
| default | Content of Form Item.                         | —                            |
| label   | Custom content to display on label.           | ^[object]`{ label: string }` |
| error   | Custom content to display validation message. | ^[object]`{ error: string }` |

### FormItem Exposes

| Nombre                    | Descripción                                                                                        | Tipo                                                                                                     |
| ------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| size                      | Form item size.                                                                                    | ^[object]`ComputedRef<'' \| 'large' \| 'default' \| 'small'>`                                   |
| validateMessage           | Validation message.                                                                                | ^[object]`Ref<string>`                                                                             |
| validateState             | Validation state.                                                                                  | ^[object]`Ref<'' \| 'error' \| 'validating' \| 'success'>`                                      |
| validate                  | Validate form item.                                                                                | ^[Function]`(trigger: string, callback?: FormValidateCallback \| undefined) => FormValidationResult` |
| resetField                | Reset current field and remove validation result.                                                  | ^[Function]`() => void`                                                                               |
| clearValidate             | Remove validation status of the field.                                                             | ^[Function]`() => void`                                                                               |
| setInitialValue ^(2.13.1) | Set initial value for this field. When `resetField` is called, the field will reset to this value. | ^[Function]`(value: any) => void`                                                                     |

## Type Declarations

<details>
  <summary>Show declarations</summary>

```ts
type Arrayable<T> = T | T[]

type FormValidationResult = Promise<boolean>

// ValidateFieldsError: see [async-validator](https://github.com/yiminghe/async-validator/blob/master/src/interface.ts)
type FormValidateCallback = (
  isValid: boolean,
  invalidFields?: ValidateFieldsError
) => Promise<void> | void

// RuleItem: see [async-validator](https://github.com/yiminghe/async-validator/blob/master/src/interface.ts)
interface FormItemRule extends RuleItem {
  trigger?: Arrayable<string>
}

type Primitive = null | undefined | string | number | boolean | symbol | bigint
type BrowserNativeObject = Date | FileList | File | Blob | RegExp
type IsTuple<T extends ReadonlyArray<any>> = number extends T['length']
  ? false
  : true
type ArrayMethodKey = keyof any[]
type TupleKey<T extends ReadonlyArray<any>> = Exclude<keyof T, ArrayMethodKey>
type ArrayKey = number
type PathImpl<K extends string | number, V> = V extends
  Primitive | BrowserNativeObject
  ? `${K}`
  : `${K}` | `${K}.${Path<V>}`
type Path<T> =
  T extends ReadonlyArray<infer V>
    ? IsTuple<T> extends true
      ? {
          [K in TupleKey<T>]-?: PathImpl<Exclude<K, symbol>, T[K]>
        }[TupleKey<T>]
      : PathImpl<ArrayKey, V>
    : {
        [K in keyof T]-?: PathImpl<Exclude<K, symbol>, T[K]>
      }[keyof T]
type FieldPath<T> = T extends object ? Path<T> : never
// MaybeRef: see [@vueuse/core](https://github.com/vueuse/vueuse/blob/main/packages/shared/utils/types.ts)
// UnwrapRef: see [vue](https://github.com/vuejs/core/blob/main/packages/reactivity/src/ref.ts)
type FormRules<T extends MaybeRef<Record<string, any> | string> = string> =
  Partial<
    Record<
      UnwrapRef<T> extends string ? UnwrapRef<T> : FieldPath<UnwrapRef<T>>,
      Arrayable<FormItemRule>
    >
  >

type FormItemValidateState = (typeof formItemValidateStates)[number]
type FormItemProps = ExtractPropTypes<typeof formItemProps>

type FormItemContext = FormItemProps & {
  $el: HTMLDivElement | undefined
  size: ComponentSize
  validateMessage: string
  validateState: FormItemValidateState
  isGroup: boolean
  labelId: string
  inputIds: string[]
  hasLabel: boolean
  fieldValue: any
  propString: string
  addInputId: (id: string) => void
  removeInputId: (id: string) => void
  validate: (
    trigger: string,
    callback?: FormValidateCallback
  ) => FormValidationResult
  resetField(): void
  clearValidate(): void
  setInitialValue: (value: any) => void
}
```

</details>
