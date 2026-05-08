# 📡 Documentación de API — Mi Servicio REST

**Base URL:** `https://api.miservicio.com/v1`  
**Versión:** `1.0.0`  
**Autenticación:** Bearer Token (JWT)

---

## Autenticación

Todas las peticiones (excepto login/registro) requieren el header:

```
Authorization: Bearer <tu_token_jwt>
```

### Obtener Token

**`POST /auth/login`**

```json
// Request body
{
  "email": "usuario@ejemplo.com",
  "password": "contraseña123"
}
```

```json
// Response 200 OK
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "expiresIn": "7d",
  "usuario": {
    "id": 1,
    "email": "usuario@ejemplo.com",
    "nombre": "Juan García"
  }
}
```

**Errores posibles:**

| Código | Descripción |
|--------|-------------|
| `401` | Credenciales incorrectas |
| `422` | Datos de entrada inválidos |
| `429` | Demasiados intentos fallidos |

---

## Usuarios

### Listar usuarios

**`GET /usuarios`**

**Headers requeridos:** `Authorization: Bearer <token>`

**Parámetros de query:**

| Parámetro | Tipo | Default | Descripción |
|-----------|------|---------|-------------|
| `pagina` | integer | `1` | Número de página |
| `limite` | integer | `20` | Items por página (máx. 100) |
| `buscar` | string | — | Filtro por nombre o email |
| `activo` | boolean | — | Filtrar por estado |
| `orden` | string | `createdAt` | Campo para ordenar |
| `dir` | string | `desc` | `asc` o `desc` |

**Ejemplo de petición:**

```bash
curl -X GET "https://api.miservicio.com/v1/usuarios?pagina=1&limite=10&buscar=juan" \
  -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
```

**Respuesta 200 OK:**

```json
{
  "data": [
    {
      "id": 1,
      "nombre": "Juan García",
      "email": "juan@ejemplo.com",
      "activo": true,
      "rol": "admin",
      "createdAt": "2024-01-15T10:30:00Z",
      "updatedAt": "2024-03-20T14:22:00Z"
    }
  ],
  "meta": {
    "pagina": 1,
    "limite": 10,
    "total": 48,
    "totalPaginas": 5
  }
}
```

---

### Obtener usuario

**`GET /usuarios/:id`**

```bash
curl -X GET "https://api.miservicio.com/v1/usuarios/1" \
  -H "Authorization: Bearer <token>"
```

**Respuesta 200 OK:**

```json
{
  "id": 1,
  "nombre": "Juan García",
  "email": "juan@ejemplo.com",
  "activo": true,
  "rol": "admin",
  "perfil": {
    "telefono": "+57 300 123 4567",
    "ciudad": "Bogotá",
    "avatar": "https://api.miservicio.com/uploads/avatars/1.jpg"
  },
  "createdAt": "2024-01-15T10:30:00Z"
}
```

---

### Crear usuario

**`POST /usuarios`**

```json
// Request body
{
  "nombre": "María López",
  "email": "maria@ejemplo.com",
  "password": "ContraseñaSegura123!",
  "rol": "usuario",
  "perfil": {
    "telefono": "+57 310 987 6543",
    "ciudad": "Medellín"
  }
}
```

**Validaciones del body:**

| Campo | Tipo | Requerido | Reglas |
|-------|------|-----------|--------|
| `nombre` | string | ✅ | 2-100 caracteres |
| `email` | string | ✅ | Email válido y único |
| `password` | string | ✅ | Mín. 8 chars, 1 mayúscula, 1 número |
| `rol` | string | No | `admin`, `usuario`, `editor` |

**Respuesta 201 Created:**

```json
{
  "id": 49,
  "nombre": "María López",
  "email": "maria@ejemplo.com",
  "activo": true,
  "rol": "usuario",
  "createdAt": "2024-05-08T09:00:00Z"
}
```

---

### Actualizar usuario

**`PATCH /usuarios/:id`**

Solo envía los campos que quieres actualizar:

```json
{
  "nombre": "María López Rodríguez",
  "perfil": {
    "ciudad": "Cali"
  }
}
```

**Respuesta 200 OK:** Retorna el usuario actualizado.

---

### Eliminar usuario

**`DELETE /usuarios/:id`**

**Respuesta 204 No Content** (sin cuerpo)

---

## Códigos de Error Globales

| Código HTTP | Código interno | Descripción |
|-------------|---------------|-------------|
| `400` | `BAD_REQUEST` | Petición malformada |
| `401` | `UNAUTHORIZED` | No autenticado |
| `403` | `FORBIDDEN` | Sin permisos para este recurso |
| `404` | `NOT_FOUND` | Recurso no encontrado |
| `409` | `CONFLICT` | Conflicto (ej: email ya registrado) |
| `422` | `VALIDATION_ERROR` | Datos de entrada inválidos |
| `429` | `RATE_LIMIT` | Demasiadas peticiones |
| `500` | `INTERNAL_ERROR` | Error interno del servidor |

**Formato de error:**

```json
{
  "error": {
    "codigo": "VALIDATION_ERROR",
    "mensaje": "Los datos enviados no son válidos",
    "detalles": [
      {
        "campo": "email",
        "mensaje": "Debe ser un email válido"
      },
      {
        "campo": "password",
        "mensaje": "Debe tener al menos 8 caracteres"
      }
    ]
  }
}
```

---

## Rate Limiting

| Endpoint | Límite |
|----------|--------|
| `POST /auth/login` | 10 req / 15 min por IP |
| `GET /*` | 100 req / min por token |
| `POST /PUT /PATCH` | 30 req / min por token |
| `DELETE` | 10 req / min por token |

Los headers de respuesta incluyen:

```
X-RateLimit-Limit: 100
X-RateLimit-Remaining: 87
X-RateLimit-Reset: 1715162460
```

---

*Última actualización: Mayo 2024 | [Reporte un problema](../../issues)*
