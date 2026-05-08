# 03 — Enlaces e Imágenes

## Enlaces Básicos

```markdown
[Texto del enlace](https://www.ejemplo.com)
[Google](https://www.google.com)
[GitHub](https://github.com)
```

**Resultado:**

[Google](https://www.google.com)  
[GitHub](https://github.com)

---

## Enlace con Título (tooltip)

```markdown
[Visita Google](https://www.google.com "El motor de búsqueda más usado")
```

Al pasar el cursor sobre el enlace aparece el texto "El motor de búsqueda más usado".

---

## URLs y Emails Directos

```markdown
<https://www.ejemplo.com>
<correo@ejemplo.com>
```

**Resultado:**

<https://www.ejemplo.com>  
<correo@ejemplo.com>

---

## Enlaces Relativos (dentro del repositorio)

```markdown
[Ir al inicio](../README.md)
[Ver sintaxis básica](01-sintaxis-basica.md)
[Ir a la sección de tablas](05-tablas.md#alineación-de-columnas)
```

---

## Enlace a una Sección del Mismo Archivo

Los encabezados generan automáticamente anclas (IDs). El ID se forma convirtiendo el texto a minúsculas y reemplazando espacios con `-`:

```markdown
[Ir a la sección de imágenes](#imágenes-básicas)
[Volver arriba](#enlaces-básicos)
```

---

## Enlaces de Referencia

Para no repetir URLs largas, puedes usar referencias:

```markdown
Consulta la [documentación oficial][docs] o visita el [repositorio][repo].

[docs]: https://docs.ejemplo.com "Documentación"
[repo]: https://github.com/usuario/repo
```

También puedes usar el texto del enlace como referencia implícita:

```markdown
Visita [Google] para buscar.

[Google]: https://www.google.com
```

---

## Imágenes Básicas

```markdown
![Texto alternativo](ruta/imagen.png)
![Logo de GitHub](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png)
```

La sintaxis es igual a un enlace pero con `!` al inicio. El texto entre `[]` es el texto alternativo (importante para accesibilidad).

---

## Imagen con Título

```markdown
![Descripción de la imagen](ruta/imagen.png "Título opcional")
```

---

## Imagen con Enlace

Para que una imagen sea clickeable:

```markdown
[![Texto alternativo](ruta/imagen.png)](https://enlace.com)
```

Ejemplo real:

```markdown
[![GitHub](https://img.shields.io/badge/GitHub-100000?logo=github)](https://github.com)
```

---

## Badges (Insignias)

Los badges son imágenes pequeñas muy usadas en READMEs:

### Usando Shields.io

```markdown
![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Build](https://img.shields.io/badge/build-passing-brightgreen)
![Coverage](https://img.shields.io/badge/coverage-95%25-yellow)
```

### Badges de estado comunes

```markdown
[![npm version](https://img.shields.io/npm/v/nombre-paquete)](https://www.npmjs.com/package/nombre-paquete)
[![GitHub stars](https://img.shields.io/github/stars/usuario/repo)](https://github.com/usuario/repo/stargazers)
[![GitHub issues](https://img.shields.io/github/issues/usuario/repo)](https://github.com/usuario/repo/issues)
[![GitHub forks](https://img.shields.io/github/forks/usuario/repo)](https://github.com/usuario/repo/network)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
```

---

## Imágenes de Referencia

```markdown
![Logo][logo]

[logo]: imagenes/logo.png "Logo del proyecto"
```

---

## Controlar el Tamaño de Imágenes (con HTML)

Markdown puro no permite controlar el tamaño, pero puedes usar HTML:

```html
<img src="imagen.png" alt="descripción" width="300">
<img src="imagen.png" alt="descripción" width="50%">
```

---

## Centrar Imágenes (con HTML)

```html
<div align="center">
  <img src="imagen.png" alt="descripción" width="400">
</div>
```

---

## GIF Animados

Funcionan igual que las imágenes normales:

```markdown
![Demo de la app](docs/demo.gif)
```

---

## Ejemplos de Sección de Banner para READMEs

```markdown
<div align="center">

  <img src="logo.png" alt="Logo" width="200">

  <h1>Mi Proyecto Increíble</h1>

  <p>Una descripción breve y clara del proyecto.</p>

  [![Version](https://img.shields.io/badge/version-2.0.0-blue)](#)
  [![License](https://img.shields.io/badge/license-MIT-green)](#)
  [![Build](https://img.shields.io/badge/build-passing-brightgreen)](#)

</div>
```

---

[← Volver al README](../README.md) | [← Anterior](02-listas.md) | [Siguiente: Código →](04-codigo.md)
