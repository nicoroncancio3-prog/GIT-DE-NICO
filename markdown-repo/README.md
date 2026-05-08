# 📝 Guía Completa de Markdown

> Un repositorio de referencia rápida con todos los elementos esenciales de Markdown, ejemplos prácticos y casos de uso reales.

---

## 📚 Tabla de Contenidos

- [¿Qué es Markdown?](#qué-es-markdown)
- [¿Por qué usar Markdown?](#por-qué-usar-markdown)
- [Estructura del Repositorio](#estructura-del-repositorio)
- [Inicio Rápido](#inicio-rápido)
- [Documentación por Tema](#documentación-por-tema)
- [Contribuir](#contribuir)

---

## ¿Qué es Markdown?

**Markdown** es un lenguaje de marcado ligero creado por *John Gruber* en 2004. Permite escribir texto con formato usando una sintaxis simple y legible en texto plano, que luego se convierte a HTML u otros formatos.

Es el estándar de facto para:
- 📄 Documentación de proyectos (GitHub, GitLab)
- 📓 Notas técnicas (Obsidian, Notion)
- 📰 Blogs estáticos (Jekyll, Hugo)
- 💬 Mensajes en foros (Reddit, Discord, Slack)

---

## ¿Por qué usar Markdown?

| Ventaja | Descripción |
|--------|-------------|
| ✅ **Simple** | Sintaxis fácil de aprender en minutos |
| 🔓 **Portable** | Archivos `.md` funcionan en cualquier editor |
| ⚡ **Rápido** | Escribir formato sin levantar las manos del teclado |
| 🌍 **Universal** | Soportado por GitHub, VS Code, Notion, y más |
| 🔄 **Convertible** | Se puede exportar a HTML, PDF, Word, etc. |

---

## Estructura del Repositorio

```
markdown-repo/
├── README.md                    ← Este archivo
├── docs/
│   ├── 01-sintaxis-basica.md    ← Encabezados, párrafos, énfasis
│   ├── 02-listas.md             ← Listas ordenadas, desordenadas, anidadas
│   ├── 03-enlaces-imagenes.md   ← Links, imágenes, badges
│   ├── 04-codigo.md             ← Código inline y bloques de código
│   ├── 05-tablas.md             ← Tablas y alineación
│   ├── 06-citas-separadores.md  ← Blockquotes y reglas horizontales
│   ├── 07-markdown-extendido.md ← GFM: tareas, alertas, emojis
│   └── 08-trucos-avanzados.md   ← Tips, HTML en Markdown, escapes
└── ejemplos/
    ├── readme-proyecto.md       ← Plantilla de README para proyectos
    ├── documentacion-api.md     ← Documentación de API REST
    ├── changelog.md             ← Registro de cambios (CHANGELOG)
    └── notas-reunion.md         ← Plantilla de actas/notas
```

---

## Inicio Rápido

Si solo tienes 5 minutos, esto es lo más importante:

```markdown
# Título grande
## Título mediano

Texto normal. **negrita** *cursiva* ~~tachado~~

- Elemento de lista
- Otro elemento
  - Sub-elemento

1. Lista numerada
2. Segundo item

[Texto del enlace](https://ejemplo.com)

`código inline`

> Esto es una cita
```

---

## Documentación por Tema

| Archivo | Contenido |
|---------|-----------|
| [📖 Sintaxis Básica](docs/01-sintaxis-basica.md) | Encabezados, párrafos, énfasis, texto |
| [📋 Listas](docs/02-listas.md) | Ordenadas, desordenadas, anidadas, de tareas |
| [🔗 Enlaces e Imágenes](docs/03-enlaces-imagenes.md) | Links, imágenes, badges, referencias |
| [💻 Código](docs/04-codigo.md) | Inline, bloques, resaltado de sintaxis |
| [📊 Tablas](docs/05-tablas.md) | Creación, alineación, trucos |
| [💬 Citas y Separadores](docs/06-citas-separadores.md) | Blockquotes, reglas horizontales |
| [🚀 Markdown Extendido](docs/07-markdown-extendido.md) | GitHub Flavored Markdown, alertas, emojis |
| [⚙️ Trucos Avanzados](docs/08-trucos-avanzados.md) | HTML, escapes, tips profesionales |

---

## Contribuir

Las contribuciones son bienvenidas. Si encuentras un error o quieres agregar ejemplos:

1. Haz un fork del repositorio
2. Crea una rama: `git checkout -b mejora/nuevo-ejemplo`
3. Realiza tus cambios
4. Abre un Pull Request

---

*Hecho con ❤️ para la comunidad de desarrolladores*
