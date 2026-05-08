# 04 — Código

## Código Inline

Para código dentro de una frase, usa comillas invertidas `` ` ``:

```markdown
Usa el comando `npm install` para instalar dependencias.
La función `console.log()` imprime en la consola.
El archivo se llama `index.js`.
```

**Resultado:**

Usa el comando `npm install` para instalar dependencias.  
La función `console.log()` imprime en la consola.  
El archivo se llama `index.js`.

### Escapar comillas invertidas dentro del código inline

Si el código contiene una comilla invertida, usa dobles comillas para envolverlo:

```markdown
``Esto contiene una `comilla invertida` dentro``
```

---

## Bloques de Código

Para bloques de código multilínea, usa tres comillas invertidas o tres tildes:

````markdown
```
function saludar(nombre) {
  return `Hola, ${nombre}!`;
}
```
````

O con tildes:

```markdown
~~~
código aquí
~~~
```

---

## Resaltado de Sintaxis

Especifica el lenguaje justo después de las tres comillas para activar el resaltado:

### JavaScript

````markdown
```javascript
const saludo = (nombre) => {
  return `Hola, ${nombre}!`;
};

console.log(saludo("mundo"));
```
````

```javascript
const saludo = (nombre) => {
  return `Hola, ${nombre}!`;
};

console.log(saludo("mundo"));
```

### Python

````markdown
```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)

print([fibonacci(i) for i in range(10)])
```
````

```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)

print([fibonacci(i) for i in range(10)])
```

### Bash / Shell

````markdown
```bash
#!/bin/bash
echo "Hola, mundo!"

# Instalar dependencias
npm install
npm run build
npm start
```
````

```bash
#!/bin/bash
echo "Hola, mundo!"

# Instalar dependencias
npm install
npm run build
npm start
```

### HTML

````markdown
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Mi Página</title>
</head>
<body>
  <h1>Hola, mundo!</h1>
</body>
</html>
```
````

### CSS

````markdown
```css
.contenedor {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  padding: 2rem;
}
```
````

### TypeScript

````markdown
```typescript
interface Usuario {
  id: number;
  nombre: string;
  email: string;
  activo: boolean;
}

function crearUsuario(datos: Omit<Usuario, 'id'>): Usuario {
  return { id: Date.now(), ...datos };
}
```
````

### SQL

````markdown
```sql
SELECT 
  u.nombre,
  u.email,
  COUNT(p.id) AS total_pedidos
FROM usuarios u
LEFT JOIN pedidos p ON u.id = p.usuario_id
WHERE u.activo = true
GROUP BY u.id
ORDER BY total_pedidos DESC;
```
````

### JSON

````markdown
```json
{
  "nombre": "mi-proyecto",
  "version": "1.0.0",
  "scripts": {
    "start": "node index.js",
    "dev": "nodemon index.js",
    "test": "jest"
  },
  "dependencies": {
    "express": "^4.18.0"
  }
}
```
````

### YAML

````markdown
```yaml
name: CI/CD Pipeline
on:
  push:
    branches: [main, develop]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Ejecutar pruebas
        run: npm test
```
````

---

## Lenguajes más Comunes

| Lenguaje | Identificador |
|----------|--------------|
| JavaScript | `javascript` o `js` |
| TypeScript | `typescript` o `ts` |
| Python | `python` o `py` |
| Bash/Shell | `bash` o `sh` |
| HTML | `html` |
| CSS | `css` |
| SCSS | `scss` |
| SQL | `sql` |
| JSON | `json` |
| YAML | `yaml` o `yml` |
| XML | `xml` |
| Markdown | `markdown` o `md` |
| Java | `java` |
| C# | `csharp` o `cs` |
| C++ | `cpp` |
| Go | `go` |
| Rust | `rust` |
| PHP | `php` |
| Ruby | `ruby` o `rb` |
| Swift | `swift` |
| Kotlin | `kotlin` |
| Dockerfile | `dockerfile` |

---

## Código con diff (para mostrar cambios)

````markdown
```diff
- const nombre = "Juan";
+ const nombre = "María";
  console.log(nombre);
```
````

```diff
- const nombre = "Juan";
+ const nombre = "María";
  console.log(nombre);
```

---

## Bloque de Código con Indentación (método antiguo)

Puedes crear bloques de código indentando con 4 espacios:

```markdown
    function ejemplo() {
        return "esto también es código";
    }
```

> ⚠️ Este método no soporta resaltado de sintaxis. Prefiere las comillas invertidas.

---

[← Volver al README](../README.md) | [← Anterior](03-enlaces-imagenes.md) | [Siguiente: Tablas →](05-tablas.md)
