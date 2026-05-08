# 📅 Acta de Reunión

**Proyecto:** Nombre del proyecto  
**Tipo:** Reunión de seguimiento / Planning / Retrospectiva  
**Fecha:** 8 de mayo de 2024  
**Hora:** 10:00 AM – 11:30 AM  
**Lugar:** Sala de reuniones B / Google Meet  
**Facilitador:** Juan García

---

## 👥 Participantes

| Nombre | Rol | Asistió |
|--------|-----|---------|
| Juan García | Tech Lead | ✅ |
| María López | Product Manager | ✅ |
| Carlos Ruiz | Backend Developer | ✅ |
| Ana Martínez | Frontend Developer | ✅ |
| Luis Torres | QA | ⚠️ Tarde (llegó 10:20) |
| Pedro Sánchez | Diseñador | ❌ Ausente (excusado) |

---

## 📋 Agenda

1. Revisión de pendientes de la reunión anterior
2. Estado actual del Sprint 4
3. Bloqueos y riesgos identificados
4. Planificación de la demo del viernes
5. Varios

---

## 📝 Resumen y Decisiones

### 1. Revisión de pendientes anteriores

- ✅ **Juan** completó la integración con la API de pagos
- ✅ **María** finalizó el documento de requisitos del módulo de reportes
- ❌ **Carlos** aún no completó la migración de la base de datos (reprogramado para el jueves)

---

### 2. Estado del Sprint 4

**Progreso general: 68%** (objetivo: 75% a mitad de sprint)

| Historia de Usuario | Responsable | Estado | Puntos |
|--------------------|-------------|--------|--------|
| Login con Google | Ana | ✅ Completado | 5 |
| Dashboard de métricas | Carlos | 🚧 En progreso (80%) | 8 |
| Exportar reportes PDF | Ana | 🚧 En progreso (40%) | 5 |
| Notificaciones email | Carlos | ❌ Sin iniciar | 3 |
| Módulo de permisos | Juan | 🚧 En revisión | 8 |

---

### 3. Bloqueos y Riesgos

> ⚠️ **Bloqueo crítico:** Carlos no puede avanzar en las notificaciones de email hasta que el módulo de permisos esté mergeado.

> ⚠️ **Riesgo:** La integración con el servicio de terceros tiene una API inestable. Podría retrasar el módulo de pagos.

**Decisiones tomadas:**

1. Juan hará merge del módulo de permisos hoy antes de las 5 PM para desbloquear a Carlos
2. Se añadirá manejo de errores robusto en la integración con el servicio externo
3. Se reprograma la historia de exportar PDFs para el siguiente sprint si no termina esta semana

---

### 4. Demo del viernes

- **Fecha:** Viernes 10 de mayo, 3:00 PM
- **Asistentes:** Equipo + stakeholders (Patricia y Roberto del cliente)
- **Duración:** 45 minutos

**Lo que se mostrará:**
- [ ] Login con Google (Ana)
- [ ] Dashboard de métricas básico (Carlos)
- [ ] Gestión de permisos (Juan)
- [ ] Prototipo del módulo de reportes (María - Figma)

**Preparación:**
- Ana prepara ambiente de demo para el jueves
- María prepara presentación de 5 slides con contexto para el cliente
- Juan prepara datos de ejemplo en el ambiente de demo

---

### 5. Varios

- Se acordó migrar el canal de comunicación de Slack a Discord (votación: 4 a favor, 1 en contra)
- Próxima retrospectiva del sprint: viernes 17 de mayo, 4:00 PM
- La empresa cerrará el lunes 13 de mayo por festivo nacional

---

## ✅ Compromisos y Próximos Pasos

| # | Tarea | Responsable | Fecha límite |
|---|-------|-------------|-------------|
| 1 | Merge del módulo de permisos a `main` | Juan | Hoy, 5 PM |
| 2 | Preparar ambiente de demo | Ana | Jueves 9 mayo |
| 3 | Preparar slides para el cliente | María | Jueves 9 mayo |
| 4 | Completar migración de base de datos | Carlos | Jueves 9 mayo |
| 5 | Investigar alternativa al servicio externo | Carlos | Viernes 10 mayo |
| 6 | Enviar invitación a stakeholders para la demo | María | Hoy |

---

## 📅 Próxima Reunión

**Fecha:** Lunes 13 de mayo de 2024 *(si no es festivo)* / Martes 14 de mayo  
**Hora:** 10:00 AM  
**Tipo:** Daily de inicio de semana + planning

---

*Acta elaborada por: Juan García*  
*Revisada por: María López*  
*Última actualización: 8 de mayo de 2024, 11:45 AM*
