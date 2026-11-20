# Glosario del modelo del dominio · v3

[Índice del modelo](../README.md) · [← Modelo](dominio-v3.md) · [Escenarios →](escenarios-v3.md)

Vocabulario de la [propuesta v3](dominio-v3.md), basado en la [sesión 01](../../sesiones/sesion01.md). Las denominaciones nuevas que ayudan a precisar el modelo se identifican como propuestas; aún no han sido validadas por el cliente.

## Conceptos del diagrama

| Concepto | Significado y delimitación | Origen |
| --- | --- | --- |
| **Estudiante** | Alumno que recibe enseñanza en determinadas docencias. `esErasmus` indica la condición que excluye la recepción de encuestas; no excluye al alumno del contexto académico. No se almacena su identidad en la evaluación. | Sesión 01 §2–3. |
| **Profesor** | Docente que ha impartido una asignatura y cuya actividad se evalúa. El fijo y quien lo sustituye se representan con el mismo concepto, mediante docencias diferentes. | Sesión 01 §2. |
| **Asignatura** | Materia académica. Su nombre no la vincula a un curso o semestre concreto; cada impartición se sitúa mediante Docencia. | Sesión 01 §2. |
| **Grado** | Titulación o carrera por la que deben separarse los resultados. Son sinónimos en esta propuesta. | Sesión 01 §3 y §5. |
| **Semestre** | Periodo académico, identificado conceptualmente por `periodo` y `añoAcademico`, en el que se sitúan las docencias y la convocatoria. | Sesión 01 §4; [S-01](trazabilidad-v3.md#s-01 "Decisión propuesta 01"). |
| **Docencia** | Contexto de un profesor que imparte una asignatura para un grado en un semestre. No es una clase lectiva ni el vínculo laboral del profesor. Permite evaluar por separado varias asignaturas, varios profesores y sustituciones. | Término propuesto a partir de §2 y §5; [S-01](trazabilidad-v3.md#s-01 "Decisión propuesta 01"). |
| **AsignacionEvaluacion** | Oportunidad de evaluar una docencia que corresponde a un estudiante elegible. `estadoEnvio` es `pendiente` o `enviada`. No guarda puntuaciones, comentarios ni referencia a una Evaluacion. La convocatoria se obtiene del semestre de la docencia. | Término propuesto a partir de §1, §3 y §4; [S-02](trazabilidad-v3.md#s-02 "Decisión propuesta 02"). |
| **Convocatoria** | Campaña común de encuestas de un semestre. Sus fechas exactas de apertura y cierre las establece el administrador. No es la encuesta individual de un alumno. | Sesión 01 §4. |
| **Cuestionario** | Plantilla común fijada antes del lanzamiento: 11 ítems numéricos y un enunciado de observaciones. La obligatoriedad de sus preguntas no convierte la participación en obligatoria. | Sesión 01 §2–3. |
| **Item** | Pregunta numérica del cuestionario, con número de 1 a 11 y enunciado tomado de la minuta. Cada ítem debe contestarse para enviar una evaluación. | Sesión 01 §3, tabla de ítems. |
| **Evaluacion** | Contenido anónimo, completo y enviado que valora una docencia dentro de una convocatoria. Tiene once puntuaciones y, opcionalmente, observaciones. No representa un borrador ni toda la participación del alumno. | Sesión 01 §3. |
| **Puntuacion** | Respuesta numérica a un único ítem dentro de una evaluación; `valor` es un entero de 1 a 5. No se asignan significados verbales a la escala que el cliente no haya indicado. | Sesión 01 §3. |

## Términos que no requieren otra clase

| Término | Significado y representación |
| --- | --- |
| **Encuesta** | Palabra ambigua de la minuta: se distingue entre convocatoria común, cuestionario y evaluación individual. El conjunto personalizado de pendientes se expresa mediante asignaciones. |
| **Administrador** | Único responsable de fijar fechas y consultar todas las respuestas. David desempeña este papel según la minuta. Es un rol del negocio documentado en [RN-11](trazabilidad-v3.md#rn-11 "Regla de negocio 11"). |
| **Observaciones** | Pregunta abierta opcional y su posible respuesta. Se representan como atributos del cuestionario y de la evaluación. |
| **Resultados** | Número de evaluaciones, once medias, media global y comentarios, derivados de las respuestas en su contexto académico. No identifican al autor. |
| **Notificación / recordatorio** | Aviso por campus y correo; el aviso recurrente del campus cesa al completar las evaluaciones asignadas o al cerrar el plazo. No se ha acordado una frecuencia exacta. |
| **Panal / campus** | Entorno universitario de integración, preferentemente Panal. No se modela su arquitectura ni sus datos internos. |

Los glosarios anteriores se conservan en [v1](../historico/v1/glosario.md) y [v2](../historico/v2/glosario.md); no son definiciones vigentes de v3.

---

[Índice del modelo](../README.md) · [← Modelo](dominio-v3.md) · [Escenarios →](escenarios-v3.md) · [Volver arriba](#glosario-del-modelo-del-dominio--v3)
