---
title: Steps
lang: es-ES
---

# Steps

Guía al usuario para completar tareas de acuerdo con el proceso. Sus pasos pueden configurarse de acuerdo con el escenario de aplicación real y el número de pasos no puede ser inferior a dos.

## Uso básico

Barra de pasos simple.

:::demo Defina el atributo `active` con un valor de tipo `Number`, que indica el índice de pasos y comienza desde 0. Puede definir el atributo `space` cuando es necesario fijar el ancho del paso que acepta el tipo `Number`. La unidad del atributo `space` es px. Si no está configurado, es responsive. La configuración del atributo `finish-status` puede cambiar el estado de los pasos completados.

steps/basic

:::

## Step bar con el estatus

Muestra el estado del step para cada paso.

:::demo Utilice el atributo `title` para establecer el nombre del paso, o sobrescriba el atributo usando un slot con nombre. Hemos enumerado todos los nombres de slots al final de esta página.

steps/with-status

:::

## Centrado

El título y la descripción pueden estar centrados.

:::demo

steps/centered

:::

## Step bar con descripción

Puede poner una descripción para cada paso.

:::demo

steps/with-description

:::

## Step bar con icono

En la barra de pasos se pueden utilizar diversos iconos personalizados.

:::demo El icono se define mediante la propiedad `icon`. Los tipos de iconos se pueden encontrar en la descripción del componente Icono. Además, puede personalizar el icono a través de un slot con nombre.

steps/with-icon

:::

## Step bar vertical

Step bar vertical.

:::demo Solo tiene que fijar el atributo `direction` a `vertical` en el elemento `el-steps`.

steps/vertical

:::

## Step bar simple

Step bar simple, donde se ignorará `align-center`, `description`, `direction` y `space`.

:::demo

steps/simple

:::

## API de Steps

### Steps Attributes

| Nombre         | Descripción                                                                 | Tipo                                                                 | Por defecto |
| -------------- | --------------------------------------------------------------------------- | -------------------------------------------------------------------- | ----------- |
| space          | el espaciado de cada paso, será responsivo si se omite. Soporta porcentaje. | ^[number] / ^[string]                                                | ''          |
| direction      | dirección de visualización                                                  | ^[enum]`'vertical' \| 'horizontal'`                                 | horizontal  |
| active         | actual paso de activación                                                   | ^[number]                                                            | 0           |
| process-status | estatus del paso actual                                                     | ^[enum]`'wait' \| 'process' \| 'finish' \| 'error' \| 'success'` | process     |
| finish-status  | estatus del paso final                                                      | ^[enum]`'wait' \| 'process' \| 'finish' \| 'error' \| 'success'` | finish      |
| align-center   | centrado de título y descripción                                            | ^[boolean]                                                           | —           |
| simple         | si aplicar un tema simple                                                   | ^[boolean]                                                           | —           |

### Steps Events

| Nombre | Descripción                           | Parámetro                                                |
| ------ | ------------------------------------- | -------------------------------------------------------- |
| change | triggers when the active step changes | ^[Function]`(newVal: number, oldVal: number) => void` |

### Steps Slots

| Nombre  | Descripción                          | Subtags |
| ------- | ------------------------------------ | ------- |
| default | personaliza el contenido por defecto | Step    |

## API de Steps

### Step Attributes

| Nombre      | Descripción                                                                          | Tipo                                                                        | Por defecto |
| ----------- | ------------------------------------------------------------------------------------ | --------------------------------------------------------------------------- | ----------- |
| title       | titulo del paso                                                                      | ^[string]                                                                   | ''          |
| description | descripción del paso                                                                 | ^[string]                                                                   | ''          |
| icon        | icono personalizado. Los iconos también se pueden pasar a través del slot con nombre | ^[string] / ^[Component]                                                    | —           |
| status      | estado actual. Se configurará automáticamente mediante Steps si no está configurado. | ^[enum]`'' \| 'wait' \| 'process' \| 'finish' \| 'error' \| 'success'` | ''          |

### Step Slots

| Nombre      | Descripción          |
| ----------- | -------------------- |
| icon        | icono personalizado  |
| title       | titulo del paso      |
| description | descripción del paso |
