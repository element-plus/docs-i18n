---
title: Migration
lang: es-ES
---

# Migration

[Esta guía](https://github.com/element-plus/element-plus/discussions/5658) le ayudará a pasar del Element 2.x al Element Plus.

## Versión de migración de Vue 3

Puede encontrar algunos problemas al usar Element Plus con la compilación de migración Vue 3. Algunos de los componentes dependen de las API internas de Vue 3. It's worth trying to adjust compatConfig mode to 3, either globally or [per component in your project](https://v3-migration.vuejs.org/migration-build.html).

## Herramienta de Migración :hammer_and_wrench:

Hemos creado una herramienta de migración para que pueda migrar su proyecto desde la interfaz de [Element UI](https://element.eleme.io) a Element Plus. Puedes encontrar la <a ref="https://github.com/thx/gogocode/tree/main/packages/gogocode-plugin-element">herramienta de migración de código gogo</a> aquí.

Hemos probado esto en [Vue Element Admin](https://github.com/PanJiaChen/vue-element-admin) (Vue2 + Element UI). Puedes encontrar el código transpilado [aquí](https://github. com/gogocodeio/vue-element-admin).

<style scoped>
  details {
    margin-top: 8px;
  }
</style>
