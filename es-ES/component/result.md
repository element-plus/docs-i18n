---
title: Result
lang: es-ES
---

# Resultado

Utilizado para dar comentarios sobre el resultado de la operación del usuario o excepción de acceso.

## Uso básico

:::demo `primary` has been added in ^(2.9.11).

result/basic-usage

:::

## Contenido personalizado

:::demo

result/customized-content

:::

## API

### Atributos

| Nombre    | Descripción                 | Tipo                                                                           | Por defecto |
| --------- | --------------------------- | ------------------------------------------------------------------------------ | ----------- |
| title     | título del resultado        | ^[string]                                                                      | ''          |
| sub-title | subtítulo del resultado     | ^[string]                                                                      | ''          |
| icon      | tipo de icono del resultado | ^[enum]`'primary' (2.9.11) \| 'success' \| 'warning' \| 'info' \| 'error'` | info        |

### Slots

| Nombre    | Descripción                         |
| --------- | ----------------------------------- |
| icon      | contenido de icono de result        |
| title     | contenido del título de result      |
| sub-title | contenido del subtítulo de result   |
| extra     | contenido del área extra del result |
