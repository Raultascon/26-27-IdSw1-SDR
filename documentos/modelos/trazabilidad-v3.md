# Reglas y trazabilidad · v3

[Índice provisional](indice-provisional.md) · [← Escenarios](escenarios-v3.md) · [Evolución →](evolucion.md)

Origen funcional: [minuta de la sesión 01 (26/10/2026)](../sesiones/sesion01.md), en su [revisión 3e37c8f](https://github.com/Raultascon/26-27-IdSw1-SDR/blob/3e37c8f/documentos/sesiones/sesion01.md). Propuesta vinculada al [issue #16](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/16) y a la [discussion #14](https://github.com/Raultascon/26-27-IdSw1-SDR/discussions/14).

**RN** identifica una regla recogida en la minuta; no equivale a una aprobación posterior del modelo. **S** identifica una decisión propuesta para representarla. **D** identifica una duda para el cliente. Los [escenarios E-01 y E-02 y las comprobaciones C-01 a C-08](escenarios-v3.md) permiten revisar la propuesta.

## Reglas del negocio

| ID | Regla recogida en la minuta | Fuente | Representación y comprobación |
| --- | --- | --- | --- |
| RN-01 | La encuesta se personaliza con las asignaturas del alumno. Los alumnos Erasmus no la reciben. | [§1–2](../sesiones/sesion01.md#2-profesores-alumnos-y-asignaturas) | Estudiante recibe Docencia; solo se crean asignaciones para estudiantes no Erasmus que hayan recibido esa docencia. E-01, C-01. |
| RN-02 | Se evalúa por separado a cada profesor y asignatura, incluidos los profesores fijo y temporal que hayan impartido clase. | [§2](../sesiones/sesion01.md#2-profesores-alumnos-y-asignaturas) | Docencia relaciona profesor, asignatura, grado y semestre. Evaluacion valora una sola Docencia. E-01. |
| RN-03 | Responder es voluntario y las encuestas son anónimas. | [§1 y §3](../sesiones/sesion01.md#3-cuestionarios-respuestas-y-conservación-del-progreso) | No se exige un mínimo de evaluaciones. Evaluacion carece de estudiante y no se enlaza con su asignación. E-02, C-05; D-02. |
| RN-04 | Todos usan el mismo cuestionario: 11 ítems obligatorios de 1 a 5 y una pregunta abierta opcional; plantilla fija antes del lanzamiento. | [§2–3 y tabla](../sesiones/sesion01.md#detalle-de-los-ítems-del-cuestionario) | Una Convocatoria utiliza un Cuestionario común e invariable durante la campaña. Cada Evaluacion contiene una puntuación para cada uno de sus 11 ítems. Observaciones opcionales. E-02, C-02, C-08. |
| RN-05 | Cada evaluación individual se envía y guarda al completarse; se descarta lo parcial si se abandona. Las ya finalizadas se conservan. | [§3](../sesiones/sesion01.md#3-cuestionarios-respuestas-y-conservación-del-progreso) | Evaluacion solo representa contenido aceptado completo; el diagrama de actividad distingue abandono y envío. E-01, C-03. |
| RN-06 | Una evaluación enviada no se puede modificar ni volver atrás. | [§3](../sesiones/sesion01.md#3-cuestionarios-respuestas-y-conservación-del-progreso) | AsignacionEvaluacion pasa de pendiente a enviada y no vuelve a pendiente. No se acepta otro envío para la misma asignación. C-04; la prevención de reenvíos es la interpretación S-02. |
| RN-07 | Los resultados contienen once medias, media global, número de valoraciones y comentarios; se separan por grado. | [§5](../sesiones/sesion01.md#5-resultados-medias-y-visualización) | Derivados de Evaluacion → Docencia → Profesor/Asignatura/Grado/Semestre. No se mezclan asignaturas ni grados. E-02, C-06; fórmula y consolidación pendientes en D-04. |
| RN-08 | Hay una convocatoria por semestre, habitualmente en la semana 10 y con una semana para responder. El administrador fija la fecha exacta. | [§4](../sesiones/sesion01.md#4-calendario-lanzamiento-y-notificaciones) | Convocatoria tiene apertura y cierre; cada Semestre admite como máximo una convocatoria planificada. Semana 10 y duración no se convierten en constantes inalterables. C-07; D-06. |
| RN-09 | Se avisa por campus y correo; el aviso del campus se repite hasta completar la encuesta o finalizar el plazo. | [§4](../sesiones/sesion01.md#4-calendario-lanzamiento-y-notificaciones) | Pendientes del estudiante en el semestre + plazo abierto determinan la necesidad del aviso. No se inventa frecuencia ni repetición por correo. C-07. |
| RN-10 | Después del cierre, los resultados finales llegan al administrador y a los profesores evaluados simultáneamente. | [§5](../sesiones/sesion01.md#5-resultados-medias-y-visualización) | Regla temporal de publicación; no se publica el informe final tras cada respuesta individual. Incluye a quien fue sustituido. C-07. |
| RN-11 | Hay un administrador único que ve todas las respuestas; se prefiere no permitir borrado. No se considera necesario bloquear comentarios. | [§6](../sesiones/sesion01.md#6-administración-y-control) | Rol documentado, sin clase técnica. Su consulta de respuestas no incorpora la identidad del autor. No se propone borrado ni moderación; confirmar carácter obligatorio en D-05. |
| RN-12 | Se exportan resultados a PDF/Excel; no se necesita medir el tiempo de respuesta. La integración se simula en Panal/campus; la evaluación posterior queda fuera. | [§5 y §7](../sesiones/sesion01.md#7-integración-y-herramientas) | Capacidades y límites: no precisan clases InformeExportable, FormatoExportacion, PanalUniversitario ni atributos de duración. Se retomarán al detallar casos de uso (#15). |

## Decisiones propuestas y restricciones de consistencia

| ID | Decisión | Motivo y límite |
| --- | --- | --- |
| S-01 | Docencia representa una combinación de profesor, asignatura, grado y semestre. Se trata como única en ese contexto; el alumno se vincula a las docencias efectivamente recibidas. | Evita cruzar asignaturas, profesores o resultados de grados distintos. No se inventan grupos, matrículas administrativas ni intervalos de sustitución. Si existen grupos o dobles grados con reglas especiales, habrá que revisar esta simplificación (D-03). |
| S-02 | Una asignación por estudiante elegible y docencia; solo pendiente o enviada, sin enlace al contenido. Su convocatoria es la del semestre de la docencia. Se crean asignaciones al preparar esa convocatoria. | Expresa personalización y progreso sin unir autor y respuesta. Un envío aceptado conserva el contenido y cambia el estado como un único hecho de negocio; aún no decide cómo conseguirlo técnicamente (D-02). |
| S-03 | Cada convocatoria tiene un cuestionario; se permite reutilizarlo. Un ítem pertenece a un cuestionario y no se comparte como objeto entre plantillas. | Mantiene una sola plantilla durante la campaña. No se ha pedido edición histórica ni versionado funcional; una modificación futura no debe alterar respuestas anteriores. |
| S-04 | Medias aritméticas por convocatoria, profesor, asignatura y grado; sin valor de media cuando no hay respuestas. | Propuesta calculable, no fórmula confirmada por el cliente (D-04). |

Además de las multiplicidades, deben cumplirse estas restricciones:

1. `fechaApertura < fechaCierre`; solo se acepta el envío dentro del plazo y con asignación pendiente. La hora exacta de corte queda en D-06.
2. La docencia de una evaluación y su convocatoria corresponden al mismo semestre.
3. Una asignación solo puede referirse a una docencia recibida por su estudiante; `esErasmus = verdadero` impide asignarla. La unicidad estudiante–docencia evita duplicar oportunidades dentro del semestre.
4. Cada evaluación contiene exactamente once puntuaciones, una por cada ítem distinto de su cuestionario, con enteros de 1 a 5. Tener once valores del mismo ítem no es válido.
5. La ausencia de observaciones es válida. El envío aceptado no crea una relación con la asignación, ni guarda nombre o identificador del estudiante en las respuestas.
6. La ausencia de respuestas no elimina la convocatoria ni obliga a crear evaluaciones vacías. Tampoco se borran las respuestas completas de otras docencias al abandonar.

## Preguntas para la siguiente validación

Estas preguntas quedan preparadas para revisión del equipo y conversación con el cliente; no se han publicado como nuevas consultas ni se atribuyen respuestas inexistentes.

| ID | Pregunta concreta | Por qué importa / tratamiento provisional |
| --- | --- | --- |
| D-01 | La minuta dice «los profesores deben ser evaluadores sí o sí»: ¿quiere decir que deben ser evaluados o que también responden cuestionarios? | Puede añadir un colectivo participante. No se incorpora Profesor como autor de evaluaciones mientras no se aclare. |
| D-02 | ¿Qué información de participación puede conocer el administrador y qué entiende el cliente por anonimato frente a grupos pequeños o comentarios con nombres? ¿Cómo debe poder retomarse lo pendiente sin identificar respuestas enviadas? | La separación conceptual no elimina la inferencia ni resuelve el mecanismo de control de duplicados. No se promete anonimato técnico demostrado. |
| D-03 | ¿Cómo se identifican las docencias recibidas por cada alumno si hay grupos, asignaturas compartidas entre grados, dobles grados o cambios de profesor? | Confirmar la unidad profesor–asignatura–grado–semestre y el origen de los datos de personalización. No se supone que todos los matriculados hayan tenido a todos los profesores. |
| D-04 | ¿La media global pondera igual los 11 ítems? ¿Se quiere un total por profesor además del detalle por asignatura y grado? ¿Cómo se redondea y se muestran los casos sin respuestas? | La propuesta mantiene la granularidad más fina para no perder información. La fórmula y presentación no están cerradas. |
| D-05 | ¿La ausencia de borrado debe ser una prohibición definitiva? ¿El administrador puede consultar respuestas durante el plazo, aunque los resultados finales se entreguen al cierre? | Se conserva la preferencia de no borrar y la publicación final simultánea. No se presupone el momento de acceso a respuestas individuales. |
| D-06 | ¿Una semana de plazo es una duración obligatoria o habitual? ¿Qué hora y límites exactos tienen apertura y cierre? | Se modelan fechas configurables; no se fija la semana 10 ni una hora de corte por suposición. |

Resolver estas dudas exige nueva evidencia del cliente. Una nueva iteración debe enlazar la respuesta correspondiente y revisar los elementos afectados; no basta con cambiar «pendiente» por «validado».

---

[Índice provisional](indice-provisional.md) · [← Escenarios](escenarios-v3.md) · [Evolución →](evolucion.md) · [Volver arriba](#reglas-y-trazabilidad--v3)
