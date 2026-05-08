# 08 — Trucos Avanzados

## HTML dentro de Markdown

La mayoría de parsers permiten HTML inline. Úsalo cuando Markdown no sea suficiente:

### Alineación de texto

```html
<div align="center">Texto centrado</div>
<div align="right">Texto a la derecha</div>
```

### Colores (con HTML)

```html
El semáforo tiene <span style="color:red">rojo</span>, 
<span style="color:orange">naranja</span> y 
<span style="color:green">verde</span>.
```

> ⚠️ Los estilos inline no funcionan en GitHub por razones de seguridad, pero sí en muchos otros renderers.

### Salto de línea forzado

```html
Primera línea<br>Segunda línea<br>Tercera línea
```

### Espacios no-rompibles

```html
Texto&nbsp;&nbsp;&nbsp;con espacios extras
```

---

## Comentarios en Markdown

Markdown no tiene comentarios nativos, pero puedes usar comentarios HTML:

```markdown
<!-- Este comentario no se mostrará en el output renderizado -->

<!-- 
  Esto es un comentario
  de múltiples líneas
-->

Texto visible <!-- comentario inline --> más texto visible
```

Útil para:
- Dejar notas para otros editores del archivo
- Desactivar temporalmente secciones
- Añadir metadatos no visibles

---

## Escape de Caracteres

Para mostrar literalmente un carácter especial, precédelo con `\`:

```markdown
\# No es un encabezado
\*No es cursiva\*
\**No es negrita\**
\`No es código\`
\[No es un enlace\](http://ejemplo.com)
\- No es una lista
\> No es una cita
\| No es una tabla
```

**Caracteres que necesitan escape:**

```
\ ` * _ { } [ ] ( ) # . ! + - >
```

---

## Anclas y Navegación Interna

Los encabezados generan IDs automáticamente. Reglas para el ID:
1. Se convierte a minúsculas
2. Los espacios se reemplazan por `-`
3. Se eliminan los caracteres especiales (excepto `-`)
4. Los emojis se eliminan

```markdown
## Mi Sección con Espacios
## ¿Cómo funciona?
## Título con (paréntesis)
## Título con Emojis 🚀
```

Los IDs generados serían:
- `#mi-sección-con-espacios`
- `#cómo-funciona`
- `#título-con-paréntesis`
- `#título-con-emojis-`

### Navegar a secciones

```markdown
[Ir a configuración](#configuración)
[Ver la tabla de contenidos](#tabla-de-contenidos)
```

### Enlace a encabezado en otro archivo

```markdown
[Ver sintaxis avanzada](08-trucos-avanzados.md#html-dentro-de-markdown)
```

---

## Tabla de Contenidos Automática

Muchos editores generan TOCs automáticamente, pero también puedes hacerla manual:

```markdown
## Tabla de Contenidos

- [Instalación](#instalación)
- [Configuración](#configuración)
  - [Variables de entorno](#variables-de-entorno)
  - [Base de datos](#base-de-datos)
- [Uso](#uso)
- [API](#api)
- [Contribuir](#contribuir)
```

---

## Badges Útiles para READMEs

```markdown
<!-- Estado del repositorio -->
![Mantenido](https://img.shields.io/badge/Mantenido%3F-sí-green.svg)
![No mantenido](https://img.shields.io/badge/Mantenido%3F-no-red.svg)

<!-- Licencias -->
![MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)
![GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)

<!-- Tecnologías -->
![Node.js](https://img.shields.io/badge/Node.js-43853D?logo=node.js&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?logo=typescript&logoColor=white)

<!-- Plataformas -->
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?logo=github-actions&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
```

---

## Texto Colapsable con HTML

```html
<details>
<summary><strong>📋 Instrucciones de instalación (clic para expandir)</strong></summary>

### Paso 1: Clonar el repositorio

```bash
git clone https://github.com/usuario/repo.git
cd repo
```

### Paso 2: Instalar dependencias

```bash
npm install
```

### Paso 3: Configurar el entorno

Copia el archivo `.env.example` a `.env` y configura las variables.

</details>
```

---

## Imágenes Side by Side (con HTML)

```html
<p float="left">
  <img src="imagen1.png" width="48%" />
  <img src="imagen2.png" width="48%" />
</p>
```

---

## Resumen de Atajos Útiles en Editores

### VS Code
| Atajo | Acción |
|-------|--------|
| `Ctrl+Shift+V` | Vista previa de Markdown |
| `Ctrl+K V` | Vista previa al lado |
| `Ctrl+B` | Negrita |
| `Ctrl+I` | Cursiva |

### Obsidian
| Atajo | Acción |
|-------|--------|
| `Ctrl+E` | Alternar modo edición/vista |
| `Ctrl+B` | Negrita |
| `Ctrl+I` | Cursiva |
| `Ctrl+K` | Enlace |

---

## Buenas Prácticas

1. **Usa un solo `#` por archivo** — Solo debe haber un H1 por documento.
2. **No saltes niveles de encabezado** — H1 → H2 → H3, no H1 → H3.
3. **Línea en blanco antes y después de bloques** — Mejora la compatibilidad entre parsers.
4. **Consistencia en listas** — Usa siempre el mismo carácter (`-`, `*`, o `+`).
5. **Texto alternativo en imágenes** — Siempre describe lo que muestra la imagen.
6. **Links descriptivos** — Evita "haz clic aquí", usa texto que describa el destino.
7. **Máximo 80 caracteres por línea** (opcional) — Facilita las revisiones en git.
8. **Archivo `.editorconfig`** — Define indentación y fin de línea para consistencia.

---

## Herramientas Recomendadas

| Herramienta | Tipo | Descripción |
|-------------|------|-------------|
| [VS Code](https://code.visualstudio.com/) | Editor | El mejor editor con preview integrado |
| [Obsidian](https://obsidian.md/) | Notas | Ideal para knowledge base personal |
| [Typora](https://typora.io/) | Editor WYSIWYG | Edita y ve el resultado al mismo tiempo |
| [StackEdit](https://stackedit.io/) | Online | Editor en el navegador con sync |
| [Dillinger](https://dillinger.io/) | Online | Editor simple online |
| [Pandoc](https://pandoc.org/) | CLI | Convierte Markdown a cualquier formato |
| [markdownlint](https://github.com/DavidAnson/markdownlint) | Linter | Verifica la calidad del Markdown |

---

[← Volver al README](../README.md) | [← Anterior](07-markdown-extendido.md)
