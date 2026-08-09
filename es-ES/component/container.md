---
title: Container
lang: es-ES
---

# Container

Componentes contenedores para iniciar una estructura básica de una página:

`<el-container>`: contenedor envoltorio. Cuando se anidan con un `<el-header>` o `<el-footer>`, todos sus elementos hijos estarán dispuestos verticalmente. De lo contrario horizontalmente.

`<el-header>`: contenedor para encabezados.

`<el-aside>`: Contenedor para secciones laterales (generalmente, una barra lateral).

`<el-main>`: contenedor para secciones principales.

`<el-footer>`: contenedor para pie de página.

:::tip

Estos componentes usan flex para el diseño, así que por favor asegúrese de que su navegador lo soporta. Además, los elementos secundarios directos de `<el-container>`tienen que ser uno o más de los últimos cuatro componentes. Y el elemento padre de estos últimos cuatro componentes debe ser un `<el-container>`.

:::

## Diseños comunes

<style lang="scss">
@use '../../examples/container/common-layout.scss';
</style>

:::demo

container/layout-hm

:::

:::demo

container/layout-hmf

:::

:::demo

container/layout-am

:::

:::demo

container/layout-ham

:::

:::demo

container/layout-hamf

:::

:::demo

container/layout-ahm

:::

:::demo

container/layout-ahmf

:::

## Ejemplo

:::demo

container/example

:::

## API del Contenedor

### Container Attributes

| Nombre    | Descripción                                    | Tipo                                 | Por defecto                                                                |
| --------- | ---------------------------------------------- | ------------------------------------ | -------------------------------------------------------------------------- |
| direction | dirección de diseño para elementos secundarios | ^[enum]`'horizontal' \| 'vertical'` | vertical when nested with `el-header` or `el-footer`; horizontal otherwise |

### Container Slots

| Nombre  | Descripción                          | Subtags                                    |
| ------- | ------------------------------------ | ------------------------------------------ |
| default | personaliza el contenido por defecto | Container / Header / Aside / Main / Footer |

## API de cabecera

### Header Attributes

| Nombre | Descripción           | Tipo      | Por defecto |
| ------ | --------------------- | --------- | ----------- |
| height | altura del encabezado | ^[string] | 60px        |

### Header Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |

## Aside API

### Aside Attributes

| Nombre | Descripción                 | Tipo      | Por defecto |
| ------ | --------------------------- | --------- | ----------- |
| width  | ancho de la sección lateral | ^[string] | 300px       |

### Aside Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |

## Main API

### Main Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |

## API de Footer

### Footer Attributes

| Nombre | Descripción              | Tipo      | Por defecto |
| ------ | ------------------------ | --------- | ----------- |
| height | altura del pie de página | ^[string] | 60px        |

### Footer Slots

| Nombre  | Descripción                          |
| ------- | ------------------------------------ |
| default | personaliza el contenido por defecto |
