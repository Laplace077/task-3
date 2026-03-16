# Plantilla de Casos de Prueba — Grupo 4
**Proyecto:** Sistema de Gestion Academica (SGA)  
**Curso:** Ingenieria de Software I — Universidad Invenio  
**Ciclo:** 2026  

---

## Como usar esta plantilla

Cada caso de prueba debe completarse en su propia tabla. Copie el bloque de tabla tantas veces como casos necesite y rellene cada campo. El campo **Estado** se completa al momento de ejecutar la prueba, no antes.

---

## Niveles de prueba

| Nivel | Cuando usarlo |
|---|---|
| Unitaria | Validar una funcion o metodo de forma aislada |
| Integracion | Verificar la interaccion entre modulos o con la base de datos |
| E2E | Simular un flujo completo desde el navegador como usuario final |

---

## Campos del caso de prueba

| Campo | Descripcion | Valores posibles |
|---|---|---|
| ID | Identificador unico del caso | TC-U## / TC-I## / TC-E## |
| Modulo | Modulo funcional al que pertenece | Calificaciones, Inscripciones, Autenticacion, etc. |
| Tipo | Nivel de la prueba | Unitaria / Integracion / E2E |
| Prioridad | Importancia del caso para el negocio | Alta / Media / Baja |
| Precondiciones | Estado del sistema antes de ejecutar | Texto libre |
| Pasos | Secuencia de acciones a ejecutar | Texto libre numerado |
| Resultado esperado | Salida o estado esperado al terminar | Texto libre |
| Resultado obtenido | Salida real al ejecutar el caso | Completar al ejecutar |
| Estado | Resultado de la ejecucion | Pass / Fail / Bloqueado / Pendiente |
| Notas | Observaciones adicionales o defectos encontrados | Texto libre |

---

## Bloque de caso de prueba (copiar y rellenar)

| Campo | Valor |
|---|---|
| **ID** | TC-___ |
| **Modulo** | |
| **Tipo** | |
| **Prioridad** | |
| **Precondiciones** | |
| **Pasos** | 1. <br> 2. <br> 3. |
| **Resultado esperado** | |
| **Resultado obtenido** | |
| **Estado** | |
| **Notas** | |

---

## Ejemplos completados

### Ejemplo 1 — Prueba Unitaria

| Campo | Valor |
|---|---|
| **ID** | TC-U01 |
| **Modulo** | Calificaciones |
| **Tipo** | Unitaria |
| **Prioridad** | Alta |
| **Precondiciones** | Ninguna. La funcion no depende de base de datos. |
| **Pasos** | 1. Llamar calcularPromedio con el arreglo [80, 90, 70] |
| **Resultado esperado** | La funcion retorna 80.0 |
| **Resultado obtenido** | 80.0 |
| **Estado** | Pass |
| **Notas** | — |

### Ejemplo 2 — Prueba Unitaria (caso negativo)

| Campo | Valor |
|---|---|
| **ID** | TC-U02 |
| **Modulo** | Calificaciones |
| **Tipo** | Unitaria |
| **Prioridad** | Alta |
| **Precondiciones** | Ninguna. |
| **Pasos** | 1. Llamar calcularPromedio con un arreglo vacio [] |
| **Resultado esperado** | La funcion lanza la excepcion "Sin notas registradas" |
| **Resultado obtenido** | Excepcion lanzada correctamente |
| **Estado** | Pass |
| **Notas** | — |

### Ejemplo 3 — Prueba de Integracion

| Campo | Valor |
|---|---|
| **ID** | TC-I01 |
| **Modulo** | Calificaciones |
| **Tipo** | Integracion |
| **Prioridad** | Alta |
| **Precondiciones** | Base de datos inicializada con datos de prueba. Token de autenticacion valido disponible. |
| **Pasos** | 1. Enviar GET /api/estudiantes/1001/notas con header Authorization: Bearer token_valido |
| **Resultado esperado** | HTTP 200 con un arreglo de notas en el cuerpo de la respuesta |
| **Resultado obtenido** | HTTP 200, arreglo con 5 entradas |
| **Estado** | Pass |
| **Notas** | — |

### Ejemplo 4 — Prueba de Integracion (caso negativo)

| Campo | Valor |
|---|---|
| **ID** | TC-I02 |
| **Modulo** | Calificaciones |
| **Tipo** | Integracion |
| **Prioridad** | Media |
| **Precondiciones** | Base de datos inicializada. Token valido disponible. |
| **Pasos** | 1. Enviar GET /api/estudiantes/9999/notas con header Authorization: Bearer token_valido |
| **Resultado esperado** | HTTP 404 con mensaje de error "Estudiante no encontrado" |
| **Resultado obtenido** | HTTP 404 |
| **Estado** | Pass |
| **Notas** | — |

### Ejemplo 5 — Prueba E2E

| Campo | Valor |
|---|---|
| **ID** | TC-E01 |
| **Modulo** | Autenticacion / Calificaciones |
| **Tipo** | E2E |
| **Prioridad** | Alta |
| **Precondiciones** | Ambiente de pruebas activo. Usuario estudiante01 registrado con contrasena Pass1234! |
| **Pasos** | 1. Navegar a https://sga.invenio.ac.cr/login <br> 2. Ingresar usuario estudiante01 y contrasena Pass1234! <br> 3. Hacer clic en el boton de inicio de sesion <br> 4. Hacer clic en Mis Notas en el menu lateral |
| **Resultado esperado** | El usuario llega al dashboard y la tabla de notas es visible |
| **Resultado obtenido** | Dashboard cargado, tabla visible con 5 filas |
| **Estado** | Pass |
| **Notas** | Tiempo de carga del dashboard: 1.2 s |

---

## Registro de ejecucion

Use esta tabla para llevar el resumen del estado de todos los casos en una sesion de pruebas.

| ID | Modulo | Tipo | Prioridad | Estado | Fecha | Ejecutado por |
|---|---|---|---|---|---|---|
| TC-U01 | Calificaciones | Unitaria | Alta | Pass | 2026-03-18 | |
| TC-U02 | Calificaciones | Unitaria | Alta | Pass | 2026-03-18 | |
| TC-I01 | Calificaciones | Integracion | Alta | Pass | 2026-03-18 | |
| TC-I02 | Calificaciones | Integracion | Media | Pass | 2026-03-18 | |
| TC-E01 | Autenticacion / Calificaciones | E2E | Alta | Pass | 2026-03-18 | |
