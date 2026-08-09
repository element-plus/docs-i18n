---
title: Color
lang: es-ES
---

# Color

Element Plus utiliza un conjunto de paletas para especificar colores, y así, proporcionar una apariencia y sensación coherente para los productos que construye.

<style lang="scss">
.demo-color-box {
  position: relative;
  border-radius: 4px;
  padding: 20px;
  margin: 8px 0;
  height: 112px;
  box-sizing: border-box;
  color: var(--el-color-white);
  font-size: 14px;

  .bg-color-sub {
    width: 100%;
    height: 40px;
    left: 0;
    bottom: 0;
    position: absolute;

    .bg-blue-sub-item {
      height: 100%;
      display: inline-block;

      &:first-child {
        border-radius: 0 0 0 var(--el-border-radius-base);
      }
    }

    .bg-secondary-sub-item {
      height: 100%;
      display: inline-block;
      &:first-child {
        border-radius: 0 0 0 var(--el-border-radius-base);
      }
    }
  }

  .value {
    margin-top: 2px;
  }
}

.demo-color-box-lite {
  color: var(--el-text-color-primary);
}
</style>

## Color principal

El color principal de Element Plus es el azul brillante y amigable.

<!-- Do not touch -->
<ClientOnly>
  <MainColor />
</ClientOnly>

## Color secundario

Además del color principal, se necesitan utilizar distintos colores para diferentes escenarios (por ejemplo, el color en tono rojo indica una operación peligrosa)

<!-- Do not touch -->
<ClientOnly>
  <SecondaryColors />
</ClientOnly>

## Color neutro

Los colores neutros son para texto, fondos y bordes. Puede usar diferentes colores neutrales para representar una estructura jerárquica.

<!-- Do not touch -->
<ClientOnly>
  <NeutralColor />
</ClientOnly>
