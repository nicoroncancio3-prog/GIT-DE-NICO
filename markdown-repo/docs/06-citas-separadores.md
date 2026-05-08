# 06 — Citas y Separadores

## Blockquotes (Citas)

Se crean con `>` al inicio de la línea:

```markdown
> Esto es una cita básica.
```

**Resultado:**

> Esto es una cita básica.

---

## Citas de Múltiples Líneas

```markdown
> Esta es una cita
> que ocupa varias
> líneas de texto.
```

**Resultado:**

> Esta es una cita
> que ocupa varias
> líneas de texto.

También puedes poner `>` solo en la primera línea (en algunos parsers):

```markdown
> Esta cita larga es un solo párrafo.
Markdown juntará esta línea con la anterior.

Esta ya es una nueva línea fuera de la cita.
```

---

## Citas Anidadas

```markdown
> Primer nivel de cita.
>
> > Segundo nivel (cita dentro de cita).
> >
> > > Tercer nivel.
```

**Resultado:**

> Primer nivel de cita.
>
> > Segundo nivel (cita dentro de cita).
> >
> > > Tercer nivel.

---

## Citas con Otros Elementos

Las citas pueden contener casi cualquier elemento Markdown:

```markdown
> ### Título dentro de una cita
>
> - Elemento de lista
> - Otro elemento
>
> Un párrafo con **negrita** y *cursiva*.
>
> ```python
> print("Código dentro de una cita")
> ```
```

**Resultado:**

> ### Título dentro de una cita
>
> - Elemento de lista
> - Otro elemento
>
> Un párrafo con **negrita** y *cursiva*.

---

## Usos Comunes de las Citas

### Citar a alguien

```markdown
Como dijo Steve Jobs:

> La innovación distingue a un líder de un seguidor.
```

### Notas y advertencias (estilo manual)

```markdown
> 📝 **Nota:** Recuerda guardar los cambios antes de cerrar.

> ⚠️ **Advertencia:** Esta acción no se puede deshacer.

> 💡 **Tip:** Puedes usar el atajo `Ctrl+S` para guardar rápidamente.

> ❌ **Error común:** No olvides escapar los caracteres especiales.
```

**Resultado:**

> 📝 **Nota:** Recuerda guardar los cambios antes de cerrar.

> ⚠️ **Advertencia:** Esta acción no se puede deshacer.

> 💡 **Tip:** Puedes usar el atajo `Ctrl+S` para guardar rápidamente.

> ❌ **Error común:** No olvides escapar los caracteres especiales.

---

## Alertas de GitHub (GitHub Flavored Markdown)

GitHub tiene una extensión especial para alertas con formato visual diferenciado:

```markdown
> [!NOTE]
> Información útil que los usuarios deben saber.

> [!TIP]
> Consejo opcional para hacer las cosas mejor o más fácilmente.

> [!IMPORTANT]
> Información crucial necesaria para el éxito del usuario.

> [!WARNING]
> Contenido urgente que exige atención inmediata del usuario.

> [!CAUTION]
> Consecuencias negativas de ciertas acciones.
```

> [!NOTE]
> Información útil que los usuarios deben saber.

> [!TIP]
> Consejo opcional para hacer las cosas mejor o más fácilmente.

> [!WARNING]
> Contenido urgente que exige atención inmediata del usuario.

---

## Separadores Horizontales

Se crean con 3 o más de cualquiera de estos caracteres (con o sin espacios):

```markdown
---
- - -
***
* * *
___
_ _ _
```

Todos producen el mismo resultado — una línea horizontal:

---

### Cuándo usar separadores

Los separadores son útiles para:
- Dividir secciones temáticas
- Separar el contenido del pie de página
- Crear divisiones visuales en documentación larga

```markdown
## Sección 1

Contenido de la sección 1.

---

## Sección 2

Contenido de la sección 2.

---

*Pie de página*
```

---

## Combinando Citas con Atribución

```markdown
> "Cualquier tonto puede escribir código que una computadora pueda entender.
> Los buenos programadores escriben código que los humanos pueden entender."
>
> — *Martin Fowler*
```

**Resultado:**

> "Cualquier tonto puede escribir código que una computadora pueda entender.
> Los buenos programadores escriben código que los humanos pueden entender."
>
> — *Martin Fowler*

---

[← Volver al README](../README.md) | [← Anterior](05-tablas.md) | [Siguiente: Markdown Extendido →](07-markdown-extendido.md)
