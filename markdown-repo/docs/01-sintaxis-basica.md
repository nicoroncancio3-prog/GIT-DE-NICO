# 01 — Sintaxis Básica

## Encabezados

Los encabezados se crean con el símbolo `#`. Puedes usar de 1 a 6 niveles:

```markdown
# Encabezado H1 — Título principal
## Encabezado H2 — Sección
### Encabezado H3 — Subsección
#### Encabezado H4
##### Encabezado H5
###### Encabezado H6
```

**Resultado:**

# Encabezado H1
## Encabezado H2
### Encabezado H3
#### Encabezado H4
##### Encabezado H5
###### Encabezado H6

> 💡 **Tip:** Siempre deja un espacio entre el `#` y el texto. Algunos parsers no lo reconocen sin el espacio.

**Alternativa con subrayado** (solo para H1 y H2):

```markdown
Título H1
=========

Título H2
---------
```

---

## Párrafos y Saltos de Línea

```markdown
Este es un párrafo normal. Puede tener varias oraciones.
Esta línea está en el mismo párrafo porque no hay línea en blanco.

Esto es un nuevo párrafo porque hay una línea en blanco arriba.

Para un salto de línea  
sin nuevo párrafo, termina con dos espacios  
al final de la línea anterior.
```

**Resultado:**

Este es un párrafo normal. Puede tener varias oraciones.
Esta línea está en el mismo párrafo porque no hay línea en blanco.

Esto es un nuevo párrafo porque hay una línea en blanco arriba.

Para un salto de línea  
sin nuevo párrafo, termina con dos espacios  
al final de la línea anterior.

---

## Énfasis y Formato de Texto

```markdown
**negrita** o __negrita__
*cursiva* o _cursiva_
***negrita y cursiva*** o ___negrita y cursiva___
~~tachado~~
`código inline`
==resaltado== (en algunos parsers)
```

| Sintaxis | Resultado |
|----------|-----------|
| `**negrita**` | **negrita** |
| `*cursiva*` | *cursiva* |
| `***negrita cursiva***` | ***negrita cursiva*** |
| `~~tachado~~` | ~~tachado~~ |
| `` `código` `` | `código` |

> ⚠️ **Nota:** El resaltado `==texto==` solo funciona en algunos editores como Obsidian, no en GitHub.

---

## Caracteres Especiales y Escapes

Para mostrar un carácter especial literalmente, usa `\` antes de él:

```markdown
\# Esto no es un encabezado
\*Esto no es cursiva\*
\**Esto no es negrita\**
\`Esto no es código\`
\[Esto no es un enlace\]
```

**Caracteres que necesitan escape:**

```
\ ` * _ { } [ ] ( ) # + - . !
```

---

## Texto sin Formato

Para mostrar texto exactamente como está escrito, puedes indentarlo con 4 espacios:

```markdown
    Este texto aparece en fuente monoespaciada
    y preserva los espacios exactamente
    como los escribiste.
```

---

## Separadores Horizontales

Se crean con tres o más guiones, asteriscos o guiones bajos:

```markdown
---
***
___
```

Los tres producen una línea horizontal como esta:

---

← Eso fue un separador

---

[← Volver al README](../README.md) | [Siguiente: Listas →](02-listas.md)
