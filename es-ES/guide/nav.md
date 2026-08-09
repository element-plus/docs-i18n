---
title: Navigation
lang: es-ES
---

<style>
:root {
  --categories-c-bg: #F9FAFC;
  --categories-c-page: #E5E9F2;
  --categories-c-overlay: white;
  --categories-c-text: #99A9BF;
  --categories-c-icon: #E5E9F2;
  --categories-c-line: #E5E9F2;
}

.dark {
  --categories-c-bg: #1D1E1F;
  --categories-c-page: #0A0A0A;
  --categories-c-overlay: #141414;
  --categories-c-text: #53637A;
  --categories-c-icon: #2F333D;
  --categories-c-line: #242529;
}
</style>

# Navigation

La navegación se centra en resolver los problemas de los usuarios sobre dónde ir y cómo llegar allí. Generalmente, se puede categorizar en 'navegación lateral' y 'navegación superior'.

## Elija la navegación correcta

Una navegación adecuada proporciona a los usuarios una experiencia suave, mientras que una inapropiada provoca confusión. Here are the differences between sidebar navigation and top navigation.

## Navegación lateral

Fija la navegación en el borde izquierdo, mejorando así su visibilidad, haciendo más fácil cambiar entre páginas. En este caso, el área superior de la página contiene herramientas comúnmente usadas, por ejemplo, la barra de búsqueda, el botón de ayuda, el botón de notificación, etc. Adecuado para la gestión de sitios de administración de datos o sitios web de utilidades.

### Categorías de nivel 1

Adecuado para sitios simplemente estructurados con un solo nivel de páginas. No es necesario breadcrumb.

<L1Categories />

### Categorías de nivel 2

La barra lateral muestra hasta dos niveles de navegación. Se recomienda breadcrumb en la combinación de navegación de segundo nivel, facilitando a los usuarios localizar y navegar.

<L2Categories />

### Categorías de nivel 3

Adecuado para sitios web complicados de utilidades. La barra lateral izquierda mantiene la navegación del primer nivel, y la columna central muestra la navegación del segundo nivel u otras opciones de utilidad.

<L3Categories />

## Navegación superior

Conforme al orden normal de navegación de arriba hacia abajo, lo que hace las cosas más naturales. La cantidad de navegación y la longitud del texto se limitan al ancho de la parte superior.

Adecuado para sitios con poca navegación y grandes trozos.

<TopNavigationExample />
