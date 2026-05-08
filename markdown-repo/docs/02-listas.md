# 02 — Listas

## Listas Desordenadas

Usa `-`, `*` o `+` seguido de un espacio:

```markdown
- Elemento uno
- Elemento dos
- Elemento tres

* También funciona con asterisco
* Segundo elemento

+ Y también con más
+ Segundo elemento
```

**Resultado:**

- Elemento uno
- Elemento dos
- Elemento tres

> 💡 **Buena práctica:** Elige un solo símbolo y úsalo consistentemente en todo el documento.

---

## Listas Ordenadas

```markdown
1. Primer elemento
2. Segundo elemento
3. Tercer elemento
```

**Resultado:**

1. Primer elemento
2. Segundo elemento
3. Tercer elemento

**Truco:** El número que uses no importa, Markdown los reordena automáticamente:

```markdown
1. Primero
1. Segundo (sigo poniendo 1)
1. Tercero (sigo poniendo 1)
```

**Resultado:**

1. Primero
1. Segundo
1. Tercero

Esto es útil cuando reordenas elementos y no quieres renumerar todo.

---

## Listas Anidadas

Indenta con 2 o 4 espacios (según el parser) para crear sub-listas:

```markdown
- Frutas
  - Manzana
  - Naranja
    - Naranja Valencia
    - Naranja Navel
  - Plátano
- Verduras
  - Zanahoria
  - Brócoli
```

**Resultado:**

- Frutas
  - Manzana
  - Naranja
    - Naranja Valencia
    - Naranja Navel
  - Plátano
- Verduras
  - Zanahoria
  - Brócoli

---

## Mezcla de Tipos

```markdown
1. Primer paso
   - Sub-opción A
   - Sub-opción B
2. Segundo paso
   - Sub-opción C
     1. Detalle 1
     2. Detalle 2
3. Tercer paso
```

**Resultado:**

1. Primer paso
   - Sub-opción A
   - Sub-opción B
2. Segundo paso
   - Sub-opción C
     1. Detalle 1
     2. Detalle 2
3. Tercer paso

---

## Listas de Tareas (Checkboxes)

Disponibles en GitHub Flavored Markdown (GFM):

```markdown
- [x] Instalar Node.js
- [x] Crear el proyecto
- [ ] Escribir pruebas
- [ ] Desplegar en producción
- [ ] Escribir documentación
```

**Resultado:**

- [x] Instalar Node.js
- [x] Crear el proyecto
- [ ] Escribir pruebas
- [ ] Desplegar en producción
- [ ] Escribir documentación

---

## Listas con Múltiples Párrafos

Si necesitas párrafos dentro de un elemento de lista, indenta el párrafo:

```markdown
- Este es el primer elemento de la lista.

  Este párrafo también pertenece al primer elemento
  porque está indentado.

- Este es el segundo elemento.
```

**Resultado:**

- Este es el primer elemento de la lista.

  Este párrafo también pertenece al primer elemento porque está indentado.

- Este es el segundo elemento.

---

## Listas con Código o Citas

```markdown
- Para instalar, ejecuta:

  ```bash
  npm install mi-paquete
  ```

- Recuerda lo que dijo el autor:

  > "La simplicidad es la máxima sofisticación."

- Luego continúa normalmente.
```

---

## Ejemplos Prácticos

### Lista de requisitos

```markdown
**Requisitos del sistema:**

- Sistema operativo: Windows 10+, macOS 11+, o Ubuntu 20.04+
- RAM: mínimo 8 GB (recomendado 16 GB)
- Espacio en disco: 2 GB libres
- Conexión a internet para instalación
```

### Pasos numerados

```markdown
**Instalación:**

1. Descarga el instalador desde [la página oficial](#)
2. Abre el archivo descargado
3. Sigue el asistente de instalación:
   - Acepta los términos de licencia
   - Elige el directorio de instalación
   - Selecciona los componentes opcionales
4. Haz clic en "Instalar"
5. Reinicia el sistema cuando se te solicite
```

---

[← Volver al README](../README.md) | [← Anterior](01-sintaxis-basica.md) | [Siguiente: Enlaces e Imágenes →](03-enlaces-imagenes.md)
