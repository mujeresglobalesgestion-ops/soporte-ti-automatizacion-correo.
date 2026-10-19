# Automatización de correo empresarial — Caso práctico de Soporte TI

**Estado:** Proyecto cerrado y validación funcional aprobada el 19 de octubre de 2026.

## Objetivo

Documentar la implementación, las pruebas y la resolución de incidencias de un sistema de respuestas automáticas para consultas generales de Mujeres Globales SpA, utilizando Hostinger Mail API, PHP y Cron.

Este repositorio forma parte de un **portafolio de aprendizaje en Soporte TI**. Contiene documentación técnica del caso práctico, no el código de producción ni información confidencial.

## Herramientas utilizadas

- **Hostinger Mail API:** consulta, lectura y envío de mensajes mediante HTTP.
- **PHP:** procesamiento de mensajes, clasificación y controles.
- **Cron:** ejecución automática programada cada hora.
- **Hostinger Mail y Gmail:** verificación de mensajes enviados y recepción.
- **GitHub:** documentación técnica y seguimiento del proyecto.

## Funcionamiento del sistema

1. Consultar el buzón mediante la API.
2. Obtener el contenido original del mensaje.
3. Clasificar la consulta según su contenido.
4. Seleccionar una plantilla de respuesta cuando corresponda.
5. Derivar consultas sensibles, como contratos y pagos, a revisión humana.
6. Comprobar los registros para evitar procesamientos duplicados.
7. Enviar respuestas autorizadas y registrar los resultados.

## Pruebas y evidencias verificadas

| Prueba | Evidencia | Resultado |
| --- | --- | --- |
| Conexión con Hostinger Mail API | HTTP 200 | Verificada |
| Envío mediante API | HTTP 204 y recepción confirmada | Verificada |
| Respuesta automática inicial, 14-10-2026 | ENVIO_CONFIRMADO y PROCESADO_REGISTRADO | Verificada |
| Derivación de consulta contractual, 14-10-2026 | REVISION_REGISTRADA, sin respuesta automática | Verificada |
| Control de duplicados | REGISTRO_EXISTENTE | Verificado |
| Exclusión de mensajes propios | IGNORADO_PROPIO | Verificada |
| Continuidad de Cron, 17 al 19-10-2026 | 48 ejecuciones horarias consecutivas, FINALIZADA y HTTP 200 | Verificada |
| Consulta externa sobre servicios, 19-10-2026 | Respuesta automática confirmada en Enviados | Verificada |
| Consulta externa sobre Levora, 19-10-2026 | Respuesta automática confirmada en Enviados | Verificada |
| Consulta externa sobre pagos, 19-10-2026 | Derivación humana, respuesta manual enviada y recepción confirmada | Verificada |

## Diagnóstico y resolución de incidencias

Durante el desarrollo se verificaron por separado la conexión con la API, la extracción del contenido RFC822, la clasificación de consultas, la selección de plantillas, el envío y los registros de procesamiento.

Se ajustó la lógica para seleccionar una única plantilla, conservar la trazabilidad y evitar respuestas duplicadas.

También se incorporó un registro fechado de ejecuciones para comprobar la continuidad del Cron.

## Cierre del proyecto

**Estado final: CERRADO / APROBADO — 19 de octubre de 2026.**

Las tres pruebas externas finalizaron satisfactoriamente:

- **Servicios:** respuesta automática enviada correctamente.
- **Levora:** respuesta automática enviada correctamente.
- **Pagos:** consulta derivada a revisión humana, respuesta manual enviada y recepción confirmada.

Los tres registros históricos de revisión humana del 14 y 15 de octubre se consideran cerrados administrativamente como antecedentes de pruebas, por decisión de la responsable del proyecto. Su atención individual no fue acreditada.

Este cierre documental no modifica los estados de los archivos operativos de Hostinger.

La operación habitual del sistema y la atención de futuras consultas continúan de manera independiente del cierre del caso práctico.

## Seguridad y confidencialidad

Este repositorio no publica:

- Tokens ni credenciales.
- Mensajes reales ni datos personales.
- Identificadores privados.
- Rutas internas del servidor.
- Registros operativos completos.
- Código de producción.

Las pruebas realizadas validan los escenarios descritos, pero no garantizan el funcionamiento de todos los casos posibles.

## Competencias de Soporte TI demostradas

- Diagnóstico técnico por etapas.
- Interpretación de respuestas HTTP.
- Integración y pruebas de API.
- Programación de tareas mediante Cron.
- Análisis de registros y resolución de incidencias.
- Control de duplicados.
- Escalamiento a revisión humana.
- Documentación técnica y protección de datos.

## Documentación complementaria

Consulta el [caso práctico detallado](docs/caso-practico.md).
