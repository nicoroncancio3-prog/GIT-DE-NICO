# 05 — Tablas

## Tabla Básica

```markdown
| Columna 1 | Columna 2 | Columna 3 |
|-----------|-----------|-----------|
| Celda 1   | Celda 2   | Celda 3   |
| Celda 4   | Celda 5   | Celda 6   |
```

**Resultado:**

| Columna 1 | Columna 2 | Columna 3 |
|-----------|-----------|-----------|
| Celda 1   | Celda 2   | Celda 3   |
| Celda 4   | Celda 5   | Celda 6   |

> 💡 Los `|` al inicio y al final son opcionales, pero mejoran la legibilidad.

---

## Alineación de Columnas

Usa `:` en la fila separadora para controlar la alineación:

```markdown
| Izquierda | Centro | Derecha |
|:----------|:------:|--------:|
| texto     | texto  |   texto |
| abc       |  abc   |     abc |
| 1         |   1    |       1 |
```

**Resultado:**

| Izquierda | Centro | Derecha |
|:----------|:------:|--------:|
| texto     | texto  |   texto |
| abc       |  abc   |     abc |
| 1         |   1    |       1 |

| Sintaxis | Alineación |
|----------|------------|
| `:---` | Izquierda (predeterminado) |
| `:---:` | Centro |
| `---:` | Derecha |

---

## Formato dentro de Tablas

Puedes usar **negrita**, *cursiva*, `` `código` `` y [enlaces](#) dentro de las celdas:

```markdown
| Característica | Descripción | Estado |
|----------------|-------------|--------|
| **Autenticación** | Sistema de login con JWT | ✅ Listo |
| *Rate limiting* | Límite de peticiones | 🚧 En progreso |
| `API REST` | Endpoints principales | ✅ Listo |
| [Documentación](../README.md) | Guías de uso | ❌ Pendiente |
```

**Resultado:**

| Característica | Descripción | Estado |
|----------------|-------------|--------|
| **Autenticación** | Sistema de login con JWT | ✅ Listo |
| *Rate limiting* | Límite de peticiones | 🚧 En progreso |
| `API REST` | Endpoints principales | ✅ Listo |
| [Documentación](../README.md) | Guías de uso | ❌ Pendiente |

---

## Tablas Prácticas

### Comparación de tecnologías

```markdown
| Característica | React | Vue | Angular |
|:--------------|:-----:|:---:|:-------:|
| Curva de aprendizaje | Media | Baja | Alta |
| Rendimiento | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ |
| Ecosistema | 🌟 Enorme | Grande | Grande |
| TypeScript | Opcional | Opcional | Nativo |
| Tamaño del bundle | Medio | Pequeño | Grande |
```

| Característica | React | Vue | Angular |
|:--------------|:-----:|:---:|:-------:|
| Curva de aprendizaje | Media | Baja | Alta |
| Rendimiento | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ |
| Ecosistema | 🌟 Enorme | Grande | Grande |
| TypeScript | Opcional | Opcional | Nativo |
| Tamaño del bundle | Medio | Pequeño | Grande |

### Tabla de atajos de teclado

```markdown
| Atajo | Sistema | Acción |
|-------|---------|--------|
| `Ctrl + C` | Windows/Linux | Copiar |
| `Cmd + C` | macOS | Copiar |
| `Ctrl + Z` | Windows/Linux | Deshacer |
| `Cmd + Z` | macOS | Deshacer |
| `Ctrl + Shift + P` | VS Code | Paleta de comandos |
```

### Tabla de versiones / changelog

```markdown
| Versión | Fecha | Cambios |
|---------|-------|---------|
| v2.1.0 | 2024-03-15 | Añadido soporte para OAuth2 |
| v2.0.0 | 2024-02-01 | **Ruptura**: nueva API |
| v1.5.0 | 2024-01-10 | Mejoras de rendimiento |
| v1.0.0 | 2023-12-01 | Lanzamiento inicial |
```

---

## Trucos y Limitaciones

### Las pipes en el contenido

Para incluir un `|` dentro de una celda, usa `\|`:

```markdown
| Expresión | Significado |
|-----------|-------------|
| `A \| B` | A OR B |
| `A && B` | A AND B |
```

### Celdas multilínea

Markdown puro no soporta celdas que ocupen múltiples líneas. Para eso necesitas HTML:

```html
<table>
  <tr>
    <th>Nombre</th>
    <th>Descripción</th>
  </tr>
  <tr>
    <td>Elemento 1</td>
    <td>
      Primera línea<br>
      Segunda línea<br>
      Tercera línea
    </td>
  </tr>
</table>
```

### Celda vacía

Simplemente deja la celda sin contenido:

```markdown
| A | B | C |
|---|---|---|
| 1 |   | 3 |
|   | 5 |   |
```

| A | B | C |
|---|---|---|
| 1 |   | 3 |
|   | 5 |   |

---

## Generadores de Tablas

Escribir tablas Markdown a mano puede ser tedioso. Usa estas herramientas:

- [Tables Generator](https://www.tablesgenerator.com/markdown_tables)
- [Markdown Table Generator](https://jakebathman.github.io/Markdown-Table-Generator/)
- Extension de VS Code: **Markdown Table** o **Markdown All in One**

---

[← Volver al README](../README.md) | [← Anterior](04-codigo.md) | [Siguiente: Citas y Separadores →](06-citas-separadores.md)
