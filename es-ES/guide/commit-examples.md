---
title: Commit Examples
lang: es-ES
---

# Ejemplos de Commit

## Por qué existe este capítulo

Consulte [Compromisos Convencionales](https://www.conventionalcommits.org/) para obtener más información.

Un buen mensaje de confirmación nos sirve para:

1. Para entender lo que el colaborador está intentando hacer
2. Genera automáticamente el registro de cambios

### Regla para escribir mensaje de confirmación

```md
# (Si se aplica, este commit hará...) <subject> (Max 72 caracteres)

# |<---- Usando un máximo de 72 caracteres---->|

# Explicar por qué se está haciendo este cambio

# |<---- Intentar limitar cada línea a un máximo de 72 caracteres ---->|

# Proporcionar enlaces o claves a cualquier ticket relevante, artículos u otros recursos

# Utilice issues y las URL completas de las solicitudes de fusión en lugar de referencias cortas,

# ya que se muestran como texto plano fuera de GitLab

# --- COMMIT END ---

# --------------------

# Recuerde

# Capitalizar la línea del asunto

# Usar el modo imperativo en la línea del asunto

# No termine la línea del asunto con un punto

# El asunto debe contener al menos 3 palabras

# Separar el tema del cuerpo con una línea en blanco

# Commits que cambian 30 o más líneas en al menos 3 archivos deben

# describir estos cambios en el cuerpo del commit

# No use Emojis

# Utilice el cuerpo para explicar qué y por qué en vez de cómo

# Puede usar múltiples líneas con "-" para incluir puntos en el cuerpo

# Para más información: https://chris.beams.io/posts/git-commit/

# --------------------
```

### Plantilla para mensajes de confirmación

A continuación se muestra un mensaje de confirmación de plantilla para su referencia.

```md
feat(components): [button] Hice algo con botón

Se espera un espacio en blanco entre el asunto y el cuerpo.(se espera un punto)
Describe tu cambio en una o varias líneas.
Capitaliza tu primera letra al iniciar una nueva línea
Por favor, no exceda 72 caracteres por línea, porque sería más difícil de entender.

- También puedes añadir el símbolo de lista para una mejor disposición
```

Para el encabezado del tema, el formato es:

```
[type](scope): [messages]
```

Puede revisar los valores permitidos para **type** y **scope** en [commitlint.config.js](https://github.com/element-plus/element-plus/blob/c2ee36a7fc72b17742d43ecdff4e2912c416141d/commitlint.config.js#L57),

### Enlaces útiles

[Manteniendo limpio el historial de git commit](https://about.gitlab.com/blog/2018/06/07/keeping-git-commit-history-clean/)
