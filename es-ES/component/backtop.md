---
title: Backtop
lang: es-ES
---

# Backtop

Un botón para volver a la parte superior.

## Uso básico

Desplácese hacia abajo para ver el botón en el lado inferior derecho.

:::demo

backtop/basic

:::

## Personalizaciones

Área de visualización de 40px \* 40px.

:::demo

backtop/custom

:::

## API

### Atributos

| Nombre            | Descripción                                                                        | Tipo      | Por defecto |
| ----------------- | ---------------------------------------------------------------------------------- | --------- | ----------- |
| target            | el objetivo para activar el desplazamiento.                                        | ^[string] | —           |
| visibility-height | el botón no se mostrará hasta que la altura del desplazamiento alcance este valor. | ^[number] | 200         |
| right             | separación desde la derecha.                                                       | ^[number] | 40          |
| bottom            | separación desde abajo.                                                            | ^[number] | 40          |

### Eventos

| Nombre | Descripción                | Parámetros                                |
| ------ | -------------------------- | ----------------------------------------- |
| click  | se dispara al hacer click. | ^[Function]`(evt: MouseEvent) => void` |

### Slots

| Nombre  | Descripción                           |
| ------- | ------------------------------------- |
| default | personaliza el contenido por defecto. |
