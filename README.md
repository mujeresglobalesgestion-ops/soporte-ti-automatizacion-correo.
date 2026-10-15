# Automatización de correo empresarial — Caso práctico de Soporte TI

**Estado:** validación técnica completada el 14 de octubre de 2026. Seguimiento operativo en curso.

## Objetivo
Documentar la implementación y validación de un flujo de respuestas automáticas para consultas generales de Mujeres Globales SpA, utilizando Hostinger Mail API, PHP y Cron. Este repositorio es una **evidencia de aprendizaje en Soporte TI**; no contiene el código de producción ni información confidencial.

## Herramientas
- Hostinger Mail API: lectura y envío de mensajes mediante HTTP.
- PHP: procesamiento de mensajes, clasificación y controles.
- Cron: ejecución programada cada hora.
- Gmail: validación externa de recepción y asociación a la conversación.
- GitHub: documentación y seguimiento técnico.

## Flujo funcional
1. Consultar el buzón mediante API.
2. Obtener el contenido del mensaje.
3. Clasificar la consulta y elegir una única plantilla cuando corresponda.
4. Derivar solicitudes sensibles a revisión humana.
5. Verificar registros para evitar reprocesamientos.
6. Enviar respuestas autorizadas y registrar el resultado.

## Evidencias verificadas
| Prueba | Evidencia | Resultado |
| --- | --- | --- |
| Lectura del buzón | HTTP 200 | Verificada |
| Envío de prueba mediante API | HTTP 204 y recepción | Verificada |
| Respuesta automática (21:00, 14-10-2026) | `ENVIO_CONFIRMADO`, `PROCESADO_REGISTRADO`; respuesta recibida en Gmail dentro del hilo | Verificada |
| Consulta contractual sensible (22:00) | `REVISION_REGISTRADA`, `PROCESADO_REGISTRADO`; sin nuevo envío en la salida Cron | Verificada |
| Control de reprocesamiento (22:00) | Tres `REGISTRO_EXISTENTE` | Verificado en prueba controlada |
| Exclusión de correo propio (22:00) | `IGNORADO_PROPIO` | Verificada |

## Diagnóstico y resolución
Durante las pruebas se revisaron la extracción del contenido original, la selección de plantillas y la vinculación de respuestas con el mensaje recibido. Se ajustó la lógica para seleccionar una única plantilla y conservar registros de procesamiento.

## Seguridad y alcance
No se publican tokens, credenciales, identificadores privados, mensajes reales, rutas internas ni código de producción. La revisión humana efectiva y el monitoreo de excepciones son tareas operativas continuas. Estas pruebas no acreditan cobertura de todos los escenarios posibles.

Más detalles: [documentación del caso práctico](docs/caso-practico.md).
