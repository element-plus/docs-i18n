---
title: Statistic
lang: es-ES
---

# Estadísticas

Mostrar estadísticas.

## Uso básico

:::demo To highlight a number or a group of numbers, such as statistical value, amount, and ranking, you can add elements such as icon and unit before and after the number and title. And use [vueuse](https://vueuse.org/core/useTransition/) to add animated transitions to value.

statistic/basic

:::

## Cuenta atrás

:::demo El componente de cuenta regresiva, permite la cuenta regresiva de otros componentes.

statistic/countdown
:::  
:::tip

En formato se sugiere estar en el rango de días

:::

## Uso del modo Card

:::demo Visualización en modo Card, se puede combinar libremente

statistic/card

:::

## Api de Estadísticas

### Statistic Attributes

| Atributos         | Descripción                            | Tipo                                                                  | Por defecto |
| ----------------- | -------------------------------------- | --------------------------------------------------------------------- | ----------- |
| value             | Contenido numérico                     | ^[number]                                                             | 0           |
| decimal-separator | Establecer el punto decimal            | ^[string]                                                             | .           |
| formatter         | Presentación numérica personalizada    | ^[Function]`(value: number) => string \| number`                  | —           |
| group-separator   | Establece el identificador de milésimo | ^[string]                                                             | ,           |
| precision         | precisión numérica                     | ^[number]                                                             | 0           |
| prefix            | Establece el prefijo de un número      | ^[string]                                                             | —           |
| suffix            | Establece el sufijo de un número       | ^[string]                                                             | —           |
| title             | Título de los valores numéricos        | ^[string]                                                             | —           |
| value-style       | Estilo de los valores numéricos        | ^[string] / ^[object]`CSSProperties \| CSSProperties[] \| string[]` | —           |

### Statistic Slots

| Nombre | Descripción                     |
| ------ | ------------------------------- |
| prefix | Prefijo del valor numérico      |
| suffix | Sufijo del valor numérico       |
| title  | Título de los valores numéricos |

### Statistic Exposes

| Nombre       | Descripción            | Tipo                                    |
| ------------ | ---------------------- | --------------------------------------- |
| displayValue | valor actual a mostrar | ^[object]`Ref<string \| number>` |

## Api de la cuenta regresiva

### Countdown Attributes

| Atributos   | Descripción                                  | Tipo                                                                  | Por defecto |
| ----------- | -------------------------------------------- | --------------------------------------------------------------------- | ----------- |
| value       | tiempo objetivo                              | ^[number] / ^[Dayjs]                                                  | —           |
| format      | Formato visual de la cuenta regresiva        | ^[string]                                                             | HH:mm:ss    |
| prefix      | Establece el prefijo de la cuenta regresiva  | ^[string]                                                             | —           |
| suffix      | Establece el sufijo de la cuenta regresiva   | ^[string]                                                             | —           |
| title       | título de la cuenta regresiva                | ^[string]                                                             | —           |
| value-style | Estilo de los valores de la cuenta regresiva | ^[string] / ^[object]`CSSProperties \| CSSProperties[] \| string[]` | —           |

### Countdown Events

| Nombre | Descripción                                   | Tipo                                    |
| ------ | --------------------------------------------- | --------------------------------------- |
| change | Evento de cambio de los valores de tiempo     | ^[Function]`(value: number) => void` |
| finish | evento de finalización de la cuenta regresiva | ^[Function]`() => void`              |

### Countdown Slots

| Nombre | Descripción                              |
| ------ | ---------------------------------------- |
| prefix | prefijo del valor de la cuenta regresiva |
| suffix | sufijo del valor de la cuenta regresiva  |
| title  | título de la cuenta regresiva            |

### Countdown Exposes

| Nombre       | Descripción  | Tipo                         |
| ------------ | ------------ | ---------------------------- |
| displayValue | valor actual | ^[object]`Ref<string>` |
