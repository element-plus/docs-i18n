---
title: Icon
lang: es-ES
---

# Icon

Element Plus proporciona un conjunto de iconos propios.

## Uso de iconos

- Si quiere **usarlos directamente** como en el ejemplo, necesita [registrar globalmente](https://v3.vuejs.org/guide/component-registration.html#global-registration) los componentes antes de usarlos.

- Si desea ver todos los iconos SVG disponibles, compruebe [@element-plus/icons-vue@1.](https://unpkg.com/browse/@element-plus/icons-vue@1/dist/es/)[@element-plus/icons-vue@latest](https://unpkg.com/browse/@element-plus/icons-vue@latest/dist/types/components/) y la fuente [element-plus: iconos](https://github.com/element-plus/element-plus-icons) fuera o [Colección de iconos](#icon-collection)

## Instalación

### Usando gestor de paquetes

Choose a package manager you like.

::: code-group

```shell [npm]
$ npm install @element-plus/icons-vue
```

```shell [yarn]
$ yarn add @element-plus/icons-vue
```

```shell [pnpm]
$ pnpm install @element-plus/icons-vue
```

:::

### Registrar todos los iconos

Necesitas importar todos los iconos de `@element-plus/icons-vue` y registrarlos globalmente.

```ts
// main.ts

// if you're using CDN, please remove this line.
import * as ElementPlusIconsVue from '@element-plus/icons-vue'

const app = createApp(App)
for (const [key, component] of Object.entries(ElementPlusIconsVue)) {
  app.component(key, component)
}
```

También puede consultar [esta plantilla](https://codepen.io/sxzz/pen/xxpvdrg).

### Importar en el navegador

Puede importar iconos de Element Plus directamente a las etiquetas HTML del navegador y usar la variable global `ElementPlusIconsVue`.

Según los diferentes proveedores de CDN hay diferentes URLs de importación. Aquí se usa [unpkg](https://unpkg.com) y [jsDelivr](https://jsdelivr.com) como ejemplo. También puede utilizar otros proveedores CDN.

::: code-group

```html [unpkg]
<script src="//unpkg.com/@element-plus/icons-vue"></script>
```

```html [jsDelivr]
<script src="//cdn.jsdelivr.net/npm/@element-plus/icons-vue"></script>
```

:::

:::tip

Recomendamos usar CDN para importar Element Plus. Empleándolo podrá bloquear la versión en la dirección del enlace, y no verse afectado por actualizaciones incompatibles cuando Element Plus se actualice en el futuro. Por favor, consulte en [unpkg.com](https://unpkg.com) para el método para bloquear la versión.

:::

### Auto Importar

Use [unplugin-icons](https://github.com/antfu/unplugin-icons) y [unplugin-auto-import](https://github.com/antfu/unplugin-auto-import) para importar automáticamente cualquier colección de iconos de iconify. Puede consultar [esta plantilla](https://github.com/sxzz/element-plus-best-practices/blob/db2dfc983ccda5570033a0ac608a1bd9d9a7f658/vite.config.ts#L21-L58).

## Uso simple

:::warning

Debido a que el estándar HTML ya ha definido una etiqueta llamada [menu](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/menu), necesita usar un alias para renderizar el icono, si registra `Menu` directamente no funcionará.

:::

```vue
<!-- Use el-icon to provide attributes to SVG icon -->
<template>
  <div>
    <el-icon :size="size" :color="color">
      <Edit />
    </el-icon>
    <!-- Or use it independently without derive attributes from parent -->
    <Edit />
  </div>
</template>
```

<vp-script setup>
import { Edit, Share, Delete, Search, Loading } from '@element-plus/icons-vue'
</vp-script>

<ElRow>
  <div>
    <ElIcon :size="30">
      <Edit />
    </ElIcon>
    <Edit />
  </div>
</ElRow>

## Combinado con el-icon

`el-icon` proporciona atributos adicionales para el icono SVG crudo, para más detalles, por favor lea al final.

```vue
<template>
  <p>
    with extra class <b>is-loading</b>, your icon is able to rotate 360 deg in 2
    seconds, you can also override this
  </p>
  <el-icon :size="20">
    <Edit />
  </el-icon>
  <el-icon color="#409efc" class="no-inherit">
    <Share />
  </el-icon>
  <el-icon>
    <Delete />
  </el-icon>
  <el-icon class="is-loading">
    <Loading />
  </el-icon>
  <el-button type="primary">
    <el-icon style="vertical-align: middle">
      <Search />
    </el-icon>
    <span style="vertical-align: middle"> Search </span>
  </el-button>
</template>
```

<ElRow>
  <p>
    con la clase extra <b>is-loading</b>, su icono será capaz de rotar 360 grados en 2 segundos, también puede anular esto
  </p>
  <div style="display: flex; align-items: center; justify-content: space-between; width: 100%;">
    <ElIcon :size="20">
      <Edit />
    </ElIcon>
    <ElIcon color="#409efc" class="no-inherit">
      <Share />
    </ElIcon>
    <ElIcon>
      <Delete />
    </ElIcon>
    <ElIcon class="is-loading">
      <Loading />
    </ElIcon>
    <ElButton type="primary">
      <ElIcon style="vertical-align: middle; color: #fff;">
        <Search />
      </ElIcon>
      <span style="vertical-align: middle;"> Search </span>
    </ElButton>
  </div>
</ElRow>

## Usando el icono SVG directamente

```vue
<template>
  <div style="font-size: 20px">
    <!-- Since svg icons do not carry any attributes by default -->
    <!-- You need to provide attributes directly -->
    <Edit style="width: 1em; height: 1em; margin-right: 8px" />
    <Share style="width: 1em; height: 1em; margin-right: 8px" />
    <Delete style="width: 1em; height: 1em; margin-right: 8px" />
    <Search style="width: 1em; height: 1em; margin-right: 8px" />
  </div>
</template>
```

<ElRow>
  <div style="font-size: 20px;">
    <!-- Since svg icons do not carry any attributes by default -->
    <!-- You need to provide attributes directly -->
    <Edit style="width: 1em; height: 1em; margin-right: 8px;" />
    <Share style="width: 1em; height: 1em; margin-right: 8px;" />
    <Delete style="width: 1em; height: 1em; margin-right: 8px;" />
    <Search style="width: 1em; height: 1em; margin-right: 8px;" />
  </div>
</ElRow>

## Colección de iconos{#icon-collection}

:::tip

**Puede usar el icono SVG en cualquier versión** siempre y cuando lo instale

**Puede hacer clic en el icono para copiarlo**

:::

<IconList />

## API

### Atributos

| Nombre | Descripción                            | Tipo                  | Por defecto            |
| ------ | -------------------------------------- | --------------------- | ---------------------- |
| color  | Atributo de relleno de la etiqueta SVG | ^[string]             | inherit from color     |
| size   | Tamaño del icono SVG. tamaño x tamaño  | ^[number] / ^[string] | inherit from font size |

### Slots

| Nombre  | Descripción               |
| ------- | ------------------------- |
| default | Customize default content |
