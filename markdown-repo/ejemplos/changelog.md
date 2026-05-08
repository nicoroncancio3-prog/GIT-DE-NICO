# Changelog

Todos los cambios notables de este proyecto serán documentados aquí.

El formato está basado en [Keep a Changelog](https://keepachangelog.com/es-ES/1.0.0/),
y este proyecto sigue [Semantic Versioning](https://semver.org/lang/es/).

---

## [Sin publicar]

### Añadido
- Soporte para notificaciones push
- Endpoint `GET /usuarios/exportar` para exportar a CSV

### En progreso
- Migración a TypeScript

---

## [2.1.0] — 2024-05-01

### Añadido
- Autenticación con Google OAuth2
- Sistema de roles: `admin`, `editor`, `usuario`
- Paginación en todos los endpoints de lista
- Filtros avanzados en búsqueda de usuarios
- Documentación de la API con Swagger en `/api/docs`

### Cambiado
- Mejorado el rendimiento de las consultas a base de datos con índices
- Actualizado Express de v4.17 a v4.18
- Los tokens JWT ahora expiran en 7 días (antes 24 horas)

### Corregido
- `#89` Error al crear usuarios con caracteres especiales en el nombre
- `#92` Los filtros de fecha no funcionaban correctamente en zona UTC-5
- Fuga de memoria en el módulo de caché

---

## [2.0.0] — 2024-03-15

> ⚠️ **Versión con cambios de ruptura.** Lee la [guía de migración](docs/migracion-v2.md).

### ⚠️ Cambios de Ruptura (Breaking Changes)

- La URL base cambió de `/api` a `/api/v1`
- El campo `usuario_id` en respuestas fue renombrado a `usuarioId` (camelCase)
- El endpoint `GET /usuario` fue renombrado a `GET /usuarios` (plural)
- Se eliminó soporte para autenticación básica (user:password)

### Añadido
- Nueva arquitectura de microservicios
- Soporte para WebSockets en tiempo real
- Sistema de logs centralizado con Winston
- Health check en `GET /health`
- Métricas en `GET /metrics`

### Cambiado
- **Completa reescritura** del módulo de autenticación
- Base de datos migrada de MySQL a PostgreSQL
- API ahora devuelve respuestas en formato JSON:API

### Eliminado
- Soporte para Node.js < 16
- Endpoints deprecados: `/api/login`, `/api/logout` (usar `/api/v1/auth/login`)

---

## [1.5.2] — 2024-02-28

### Corregido
- `#78` Vulnerabilidad de seguridad en la validación de tokens (crítico)
- `#81` El endpoint de registro no enviaba email de confirmación

### Seguridad
- Actualizado `jsonwebtoken` de v8.5 a v9.0 (CVE-2022-23539)

---

## [1.5.1] — 2024-02-10

### Corregido
- `#71` Error 500 al intentar crear un usuario sin contraseña
- `#73` Las imágenes de perfil no se eliminaban correctamente

---

## [1.5.0] — 2024-01-20

### Añadido
- Subida de avatar de usuario (`POST /usuarios/:id/avatar`)
- Recuperación de contraseña por email
- Soporte para i18n (español e inglés)

### Cambiado
- Mejorada la velocidad de respuesta en un 40% con caché Redis
- Los mensajes de error ahora están en español por defecto

---

## [1.0.0] — 2023-12-01

### 🎉 Lanzamiento Inicial

- Autenticación JWT
- CRUD completo de usuarios
- Paginación básica
- Documentación básica en README

---

[Sin publicar]: https://github.com/usuario/repo/compare/v2.1.0...HEAD
[2.1.0]: https://github.com/usuario/repo/compare/v2.0.0...v2.1.0
[2.0.0]: https://github.com/usuario/repo/compare/v1.5.2...v2.0.0
[1.5.2]: https://github.com/usuario/repo/compare/v1.5.1...v1.5.2
[1.5.1]: https://github.com/usuario/repo/compare/v1.5.0...v1.5.1
[1.5.0]: https://github.com/usuario/repo/compare/v1.0.0...v1.5.0
[1.0.0]: https://github.com/usuario/repo/releases/tag/v1.0.0
