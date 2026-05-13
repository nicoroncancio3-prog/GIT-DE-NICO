### Notas de Markdown


---

## ¿Qué es Markdown?

Markdown es un lenguaje de marcado ligero creado en 2004 por John Gruber. Su propósito es escribir texto con formato usando símbolos simples y legibles, que luego se convierten en HTML.

Por ejemplo, en lugar de escribir `<h1>Hola</h1>`, simplemente escribes `# Hola`.

Su gran ventaja es que el archivo `.md` es legible incluso sin renderizar, a diferencia del HTML que se ve lleno de etiquetas. Es simple, rápido y funciona en casi todas las plataformas de desarrollo.

---

## ¿Para qué sirve?

Es muy usado para escribir READMEs en GitHub, documentación de proyectos, blogs técnicos y notas de estudio. Es el formato estándar para documentar proyectos de software.

---

## ¿En qué casos se usa?

Markdown se usa principalmente cuando necesitas escribir contenido con formato de forma rápida y simple, sin depender de un editor como Word.

### En GitHub y desarrollo de software

- El `README.md` de cualquier repositorio
- Documentación de proyectos y librerías
- Comentarios en Pull Requests e Issues
- Wikis de repositorios

### Tomando notas técnicas

- Apuntes de cursos y tutoriales
- Cheat sheets de lenguajes o herramientas
- Resúmenes de libros técnicos

### Escribiendo en plataformas digitales

- Posts en Dev.to, Hashnode o Medium
- Respuestas en Stack Overflow
- Mensajes en Slack o Discord (con sintaxis básica)

### Creando documentación

- Sitios de documentación con herramientas como MkDocs o Docusaurus
- Manuales de usuario de proyectos open source

---

## ¿Cuándo NO se usa?

No es ideal cuando necesitas diseño visual complejo, como presentaciones elaboradas, documentos con estilos corporativos, o formularios. Para eso es mejor Word, PowerPoint o HTML/CSS.

En resumen: si estás en un entorno técnico y necesitas escribir algo legible y bien estructurado rápidamente, Markdown es la herramienta indicada.

---

## Referencia rápida de sintaxis

| Sintaxis | Resultado | Cuándo usarlo |
|:---------|:----------|:--------------|
| `# Título` | Título grande (h1) | Título principal del documento |
| `## Título` | Subtítulo (h2) | Secciones principales |
| `### Título` | Subtítulo (h3) | Subsecciones |
| `**texto**` | **negrita** | Resaltar algo importante |
| `*texto*` | *cursiva* | Énfasis suave o términos técnicos |
| `~~texto~~` | ~~tachado~~ | Mostrar algo eliminado o incorrecto |
| `` `código` `` | `código` | Nombrar funciones, comandos o variables inline |
| `[texto](url)` | [enlace](https://example.com) | Insertar un hipervínculo |
| `![alt](url)` | *(imagen)* | Mostrar una imagen |
| `> texto` | *cita visual* | Resaltar frases o citar a alguien |
| `---` | línea horizontal | Separar secciones visualmente |
| `- elemento` | lista con puntos | Elementos sin orden específico |
| `1. elemento` | lista numerada | Pasos o elementos ordenados |
| `- [x] hecho` | ✅ tarea completada | Listas de pendientes |
| `- [ ] pendiente` | ☐ tarea pendiente | Listas de pendientes |

---

## Explicación detallada con ejemplos

Cada elemento se muestra con su sintaxis cruda y cómo se ve renderizado.

---

### `#` — Encabezados

El símbolo `#` convierte una línea en título. Entre más `#` uses, más pequeño es el título.

**Sintaxis:**
```md
# Mi portafolio
## Sobre mí
### Mis proyectos
```

**Resultado:** se ven como títulos de diferentes tamaños, equivalentes a `<h1>`, `<h2>` y `<h3>` en HTML.

---

### `**texto**` — Negrita

Rodear una palabra con doble asterisco la pone en negrita. Se usa para resaltar algo importante.

**Sintaxis:**
```md
El comando **git push** sube los cambios a GitHub.
```

**Resultado:** El comando **git push** sube los cambios a GitHub.

---

### `*texto*` — Cursiva

Con un solo asterisco el texto queda en cursiva. Se usa para énfasis suave o términos técnicos.

**Sintaxis:**
```md
Aprendí *HTML* la semana pasada.
```

**Resultado:** Aprendí *HTML* la semana pasada.

---

### `~~texto~~` — Tachado

Dos virgulillas a cada lado tachan el texto. Se usa para mostrar algo eliminado o incorrecto.

**Sintaxis:**
```md
El examen es ~~el lunes~~ el martes.
```

**Resultado:** El examen es ~~el lunes~~ el martes.

---

### `` `texto` `` — Código en línea

La tilde invertida enmarca una palabra como código dentro de un párrafo.

**Sintaxis:**
```md
Usa `console.log()` para ver el resultado en pantalla.
```

**Resultado:** Usa `console.log()` para ver el resultado en pantalla.

---

### ` ``` ` — Bloque de código

Tres tildes invertidas crean un bloque separado para código. Si le pones el nombre del lenguaje, GitHub aplica resaltado de sintaxis automáticamente.

**Sintaxis:**
````md
```javascript
let nombre = "Nicolas";
console.log("Hola, " + nombre);
```
````

**Resultado:** un bloque con colores resaltando el código JavaScript.

> Lenguajes comunes para el resaltado: `javascript`, `python`, `bash`, `html`, `css`, `json`, `sql`, `markdown`.

---

### `-` — Lista sin orden

El guion crea una lista de puntos. Se usa cuando los elementos no tienen un orden específico.

**Sintaxis:**
```md
- HTML
- CSS
- JavaScript
```

**Resultado:**
- HTML
- CSS
- JavaScript

---

### `1.` — Lista numerada

Los números crean una lista ordenada. Se usa cuando el orden importa, como en pasos de un tutorial.

**Sintaxis:**
```md
1. Abre el editor
2. Escribe el código
3. Guarda el archivo
```

**Resultado:**
1. Abre el editor
2. Escribe el código
3. Guarda el archivo

---

### `- [x]` y `- [ ]` — Tareas

Los corchetes crean casillas de verificación. `[x]` significa completado y `[ ]` pendiente.

**Sintaxis:**
```md
- [x] Aprender HTML
- [x] Aprender CSS
- [ ] Aprender JavaScript
```

**Resultado:**
- [x] Aprender HTML
- [x] Aprender CSS
- [ ] Aprender JavaScript

---

### `[texto](url)` — Enlace

Los corchetes contienen el texto visible y los paréntesis la dirección web.

**Sintaxis:**
```md
Visita [freeCodeCamp](https://www.freecodecamp.org) para aprender gratis.
```

**Resultado:** Visita [freeCodeCamp](https://www.freecodecamp.org) para aprender gratis.

---

### `![descripción](url)` — Imagen

Igual que el enlace pero con `!` al inicio. El `!` le dice a Markdown que debe mostrar la imagen.

**Sintaxis:**
```md
![Logo de GitHub](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png)
```

**Resultado:** muestra la imagen directamente en el documento.

---

### `|` — Tablas

Las barras verticales separan columnas. La segunda fila con `---` es obligatoria y define el encabezado.

**Sintaxis:**
```md
| Lenguaje   | Dificultad |
|------------|------------|
| HTML       | Fácil      |
| CSS        | Media      |
| JavaScript | Alta       |
```

**Resultado:**

| Lenguaje   | Dificultad |
|------------|------------|
| HTML       | Fácil      |
| CSS        | Media      |
| JavaScript | Alta       |

---

### `>` — Cita

El símbolo `>` convierte una línea en cita visual.

**Sintaxis:**
```md
> "El código limpio se lee como una buena prosa." — Robert C. Martin
```

**Resultado:**
> "El código limpio se lee como una buena prosa." — Robert C. Martin

---

### `---` — Línea divisoria

Tres guiones crean una línea horizontal para separar secciones visualmente.

**Sintaxis:**
```md
Sección 1

---

Sección 2
```

---

## Funcionalidades avanzadas

### Alineación de columnas en tablas

Puedes alinear el contenido de cada columna con dos puntos en la fila de separación:

```md
| Izquierda | Centro  | Derecha |
|:----------|:-------:|--------:|
| texto     | texto   |   texto |
```

| Izquierda | Centro  | Derecha |
|:----------|:-------:|--------:|
| texto     | texto   |   texto |

---

### Enlace interno a una sección

Puedes enlazar a cualquier encabezado del mismo documento. El ancla se genera automáticamente convirtiendo el título a minúsculas y reemplazando espacios con guiones.

```md
[Ver ejercicios](#ejercicios-prácticos)
```

> Útil para crear índices navegables en READMEs largos.

---

### Escapar caracteres especiales

Si necesitas que Markdown muestre literalmente un símbolo como `*`, `#` o `` ` `` sin interpretarlo, usa la barra invertida `\` antes del carácter.

```md
\*esto no es cursiva\*
\# esto no es un título
\`esto no es código\`
```

**Resultado:**

\*esto no es cursiva\*

\# esto no es un título

---

### HTML inline

GitHub y la mayoría de renderizadores permiten mezclar HTML directamente dentro de Markdown cuando necesitas algo que Markdown no soporta nativamente:

```md
Texto normal y <mark>texto resaltado</mark> con HTML.

<details>
<summary>Haz clic para ver más</summary>

Contenido oculto que se expande al hacer clic.

</details>
```

> El elemento `<details>` es especialmente útil para ocultar secciones largas como soluciones de ejercicios o configuraciones opcionales.

---

### Notas al pie

Algunos renderizadores como GitHub soportan notas al pie:

```md
Este concepto fue definido por John Gruber.[^1]

[^1]: John Gruber, creador de Markdown en 2004.
```

---

## Diferencias entre renderizadores

No todos los Markdown son iguales. El texto se puede ver diferente dependiendo de dónde se renderice:

| Característica | GitHub (GFM) | VS Code | CommonMark | Obsidian |
|:---------------|:------------:|:-------:|:----------:|:--------:|
| Tablas | ✅ | ✅ | ❌ | ✅ |
| Tareas `- [x]` | ✅ | ✅ | ❌ | ✅ |
| Tachado `~~` | ✅ | ✅ | ❌ | ✅ |
| Notas al pie | ✅ | ✅ | ❌ | ✅ |
| HTML inline | ✅ | ⚠️ | ✅ | ⚠️ |
| `<details>` | ✅ | ❌ | ✅ | ❌ |

> **GFM** (GitHub Flavored Markdown) es el estándar más extendido en desarrollo de software. Si escribes para GitHub, usa GFM.

---

## Herramientas recomendadas

### Editores con preview en tiempo real

| Herramienta | Tipo | Descripción |
|:------------|:-----|:------------|
| **VS Code** | Editor de código | Activa la preview con `Ctrl+Shift+V` o el ícono de preview arriba a la derecha |
| **Obsidian** | Notas personales | Todo el vault usa Markdown; ideal para apuntes y documentación personal |
| **Typora** | Editor dedicado | Renderiza en tiempo real mientras escribes, sin panel dividido |
| **StackEdit** | Online | Editor web con sincronización a Google Drive y Dropbox |

### Extensiones útiles para VS Code

- **Markdown All in One** — atajos, autocompletado de listas y tabla de contenidos automática
- **Markdown Preview Enhanced** — preview mejorada con soporte para diagramas
- **markdownlint** — avisa de errores de formato y malas prácticas

---

## Ejercicios prácticos

### Ejercicio 1 — Encabezados

Crea un documento con:
- Un título principal que diga tu nombre
- Un subtítulo que diga "Sobre mí"
- Un subtítulo más pequeño que diga "Mis hobbies"

<details>
<summary>Ver solución</summary>

```md
# Nicolás García
## Sobre mí
### Mis hobbies
```

</details>

---

### Ejercicio 2 — Formato de texto

Escribe esta oración aplicando formato:
- La palabra `JavaScript` en negrita
- La palabra `difícil` en cursiva
- La palabra `aburrido` tachada
- El comando `alert()` como código en línea

<details>
<summary>Ver solución</summary>

```md
Aprender **JavaScript** puede ser *difícil* pero nunca ~~aburrido~~. Usa `alert()` para probarlo.
```

</details>

---

### Ejercicio 3 — Listas

Crea dos listas:
- Una sin orden con 3 lenguajes de programación que quieras aprender
- Una numerada con los pasos para crear un archivo en tu computador

<details>
<summary>Ver solución</summary>

```md
- Python
- Rust
- Go

1. Abre el explorador de archivos
2. Navega a la carpeta deseada
3. Haz clic derecho → Nuevo archivo
4. Escribe el nombre y presiona Enter
```

</details>

---

### Ejercicio 4 — Tareas

Crea una lista de 4 temas que estás aprendiendo. Marca 2 como completados y 2 como pendientes.

<details>
<summary>Ver solución</summary>

```md
- [x] HTML
- [x] CSS
- [ ] JavaScript
- [ ] Git
```

</details>

---

### Ejercicio 5 — Enlace e imagen

- Crea un enlace a `https://www.google.com` con el texto "Buscar en Google"
- Agrega una imagen usando esta URL: `https://upload.wikimedia.org/wikipedia/commons/thumb/6/61/HTML5_logo_and_wordmark.svg/240px-HTML5_logo_and_wordmark.svg.png`

<details>
<summary>Ver solución</summary>

```md
[Buscar en Google](https://www.google.com)

![Logo de HTML5](https://upload.wikimedia.org/wikipedia/commons/thumb/6/61/HTML5_logo_and_wordmark.svg/240px-HTML5_logo_and_wordmark.svg.png)
```

</details>

---

### Ejercicio 6 — Tabla con alineación

Crea una tabla con 3 lenguajes con estas columnas: Lenguaje | Para qué sirve | Nivel (alinea la columna "Nivel" a la derecha).

<details>
<summary>Ver solución</summary>

```md
| Lenguaje   | Para qué sirve          | Nivel        |
|:-----------|:------------------------|-------------:|
| HTML       | Estructura de páginas web | Principiante |
| CSS        | Estilos visuales          | Principiante |
| JavaScript | Interactividad web        | Medio        |
```

</details>

---

### Ejercicio 7 — Bloque de código

Escribe un bloque de código en JavaScript con esto adentro:

<details>
<summary>Ver solución</summary>

````md
```javascript
let saludo = "Hola mundo";
console.log(saludo);
```
````

</details>

---