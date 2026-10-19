# Caso práctico: integración, pruebas y resolución de incidencias

**Estado:** CERRADO / APROBADO — 19 de octubre de 2026.

## 1. Contexto

Implementación y validación de un sistema de automatización de correo empresarial para Mujeres Globales SpA.

El sistema utiliza Hostinger Mail API, PHP y Cron para responder consultas generales y derivar solicitudes sensibles a revisión humana.

Este caso documenta conocimientos y competencias prácticas de Soporte TI. No incluye código de producción ni información confidencial.

## 2. Metodología de Soporte TI

- **Identificar:** distinguir problemas de conectividad, lectura, clasificación, envío y registro.
- **Diagnosticar:** analizar respuestas HTTP, resultados de ejecución y comportamiento de los mensajes.
- **Corregir:** realizar ajustes controlados y comprobar sus resultados.
- **Validar:** efectuar pruebas funcionales con mensajes reales de prueba.
- **Documentar:** registrar evidencias, decisiones y resultados comprobados.

## 3. Implementación técnica

### Integración con Hostinger Mail API

Se verificó la conexión con la API y la lectura de mensajes del buzón.

**Resultado:** HTTP 200.

También se comprobó el envío mediante API, con respuesta HTTP 204 y recepción confirmada.

### Procesamiento mediante PHP

El sistema permite:

1. Consultar mensajes.
2. Obtener contenido RFC822.
3. Clasificar consultas.
4. Seleccionar plantillas de respuesta.
5. Identificar solicitudes sensibles.
6. Registrar mensajes procesados.
7. Evitar reprocesamientos.

### Automatización mediante Cron

Se configuró una ejecución automática cada hora.

Entre el 17 y el 19 de octubre de 2026 se verificaron 48 ejecuciones horarias consecutivas, registradas como FINALIZADA y HTTP 200.

Estos resultados acreditan continuidad de ejecución y acceso a la API, pero no garantizan el éxito individual de todos los mensajes.

## 4. Pruebas funcionales

### Pruebas iniciales — 14 de octubre de 2026

**Respuesta automática:**
- ENVIO_CONFIRMADO.
- PROCESADO_REGISTRADO.
- Recepción comprobada en Gmail.
- Respuesta asociada al hilo original.

**Consulta contractual sensible:**
- REVISION_REGISTRADA.
- PROCESADO_REGISTRADO.
- Sin respuesta automática confirmada en esa ejecución.

**Controles adicionales:**
- REGISTRO_EXISTENTE: reconocimiento de mensajes previamente procesados.
- IGNORADO_PROPIO: exclusión de mensajes del propio buzón.

### Pruebas externas finales — 19 de octubre de 2026

Se realizaron tres consultas externas para comprobar el funcionamiento integral.

**Prueba 1: Servicios de Mujeres Globales**

- Consulta general recibida.
- Clasificación correcta.
- Respuesta automática enviada.
- Mensaje comprobado en Enviados.

**Resultado: VERIFICADO.**

**Prueba 2: Producto digital Levora**

- Consulta informativa recibida.
- Selección de plantilla correspondiente.
- Respuesta automática enviada.
- Contenido y envío comprobados.

**Resultado: VERIFICADO.**

**Prueba 3: Contratos y pagos**

- Consulta sensible recibida.
- Derivación automática a revisión humana.
- Registro REVISION_REGISTRADA.
- Sin respuesta automática.
- Respuesta manual enviada por la responsable.
- Recepción confirmada por el destinatario.

**Resultado: VERIFICADO.**

Esta última prueba confirmó el funcionamiento del circuito de revisión humana.

## 5. Interpretación de registros

- `ENVIO_CONFIRMADO`: confirmación de envío registrada por el sistema.
- `PROCESADO_REGISTRADO`: mensaje registrado como procesado.
- `REVISION_REGISTRADA`: consulta derivada a revisión humana.
- `REGISTRO_EXISTENTE`: mensaje previamente registrado.
- `IGNORADO_PROPIO`: exclusión de un mensaje del propio buzón.
- `FINALIZADA`: ejecución de Cron terminada.

La derivación a revisión humana no demuestra, por sí sola, que la consulta haya sido atendida.

## 6. Resolución y cierre de antecedentes

Durante las pruebas se corrigieron aspectos relacionados con la lectura de mensajes, la selección de plantillas y la trazabilidad de respuestas.

Los tres registros históricos de revisión humana del 14 y 15 de octubre se consideran cerrados administrativamente como antecedentes de pruebas, por decisión de la responsable.

No se acreditó la atención individual de esos tres registros históricos. Su cierre documental no modifica los estados conservados en Hostinger.

La prueba externa de Pagos del 19 de octubre sí confirmó el circuito completo de derivación, respuesta manual y recepción.

## 7. Seguridad y confidencialidad

El repositorio no publica:

- Credenciales ni tokens.
- Mensajes privados.
- Datos personales de remitentes.
- Identificadores internos.
- Rutas privadas del servidor.
- Registros operativos completos.
- Código de producción.

La documentación utiliza resultados técnicos y descripciones de pruebas sin exponer información confidencial.

## 8. Competencias demostradas

- Diagnóstico y resolución de incidencias.
- Integración y validación de API.
- Interpretación de códigos HTTP.
- Automatización mediante Cron.
- Análisis de registros técnicos.
- Clasificación de solicitudes.
- Control de duplicados.
- Escalamiento a revisión humana.
- Validación funcional.
- Documentación y trazabilidad.
- Protección de información sensible.

## 9. Resultado final

**PROYECTO CERRADO / APROBADO — 19 DE OCTUBRE DE 2026.**

Las tres pruebas externas finalizaron satisfactoriamente y permitieron comprobar el funcionamiento de respuestas automáticas y revisión humana.

La operación cotidiana del sistema continúa de manera independiente del cierre de este caso práctico de portafolio.

Este proyecto constituye evidencia práctica de aprendizaje en Soporte TI, integración de servicios, diagnóstico técnico y documentación de soluciones.
