# Evolución del modelo del dominio

[Índice provisional](indice-provisional.md) · [← Reglas y dudas](trazabilidad-v3.md) · [Uso de IA →](AI-uso.md)

La propuesta actual está documentada en [dominio-v3.md](dominio-v3.md). Este documento conserva la procedencia de las versiones y explica sus cambios; no convierte los modelos antiguos en modelos vigentes.

## Versiones y evidencia

| Versión | Evidencia original | Artefactos y situación |
| --- | --- | --- |
| v1 | [Issue #8](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/8), [commit aa93fa7](https://github.com/Raultascon/26-27-IdSw1-SDR/commit/aa93fa78f59a17c95670d932ddb26ebf58cecece), [PR #9](https://github.com/Raultascon/26-27-IdSw1-SDR/pull/9). | [PUML recuperado](historico/v1/dominio-v1.puml), [SVG original](historico/v1/dominio-v1.svg), [glosario original](historico/v1/glosario.md). Copias exactas del commit de creación. |
| v2 | [Issue #12](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/12), [commit 71298ae](https://github.com/Raultascon/26-27-IdSw1-SDR/commit/71298ae44a8dc99bd5cab9b9c6fbfc7701697fd2), [PR #13](https://github.com/Raultascon/26-27-IdSw1-SDR/pull/13). | [PUML](dominio-v2.puml) y [SVG](dominio-v2.svg) conservados en su ruta; [glosario v2](historico/v2/glosario.md) preservado antes de actualizar el glosario vigente. |
| v3 | [Discussion #14](https://github.com/Raultascon/26-27-IdSw1-SDR/discussions/14), [issue #16](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/16), rama `feat/issue-16-mejorar-modelo-dominio-v3`. | Propuesta de clases, dos vistas de objetos, actividad de envío y documentación. Los commits usan `refs #16`; el PR se dirige a `develop`, como los PR #9 y #13. Pendiente de revisión y validación. |

El commit de v2 eliminó los archivos de v1. Recuperarlos en `historico/v1/` permite comparar sin reescribir el historial ni alterar la autoría original. Su contenido, incluidas agregaciones y composiciones antiguas, se conserva como evidencia histórica: **v3 no utiliza esas relaciones**. No se regeneran las imágenes antiguas ni se corrigen sus errores retrospectivamente.

El registro de IA anterior también se conserva. La nueva entrada se limita al uso de Codex para código PUML, revisión de posibles errores y propuestas de mejora.

## Revisión de v1 y v2

| Aspecto observado | Consecuencia | Cambio en v3 |
| --- | --- | --- |
| v1 utiliza relaciones de parte–todo para acciones como entrar, consultar o responder y apenas expresa multiplicidades. | Mezcla el vocabulario del dominio con navegación y operaciones; dificulta verificar cardinalidades. | Asociaciones simples con nombres y multiplicidades justificadas. Las capacidades se documentan como reglas. |
| v2 añade multiplicidades y vincula las valoraciones a los ítems. | Mejora la precisión respecto a v1; esa intención se conserva. | Se explicita además que los once ítems de una evaluación son distintos y pertenecen al cuestionario de su convocatoria. |
| En v2 se puede recorrer Estudiante → EncuestaSemestral → EvaluacionDocente. | El contenido tiene un vínculo de autoría, contrario al anonimato recogido en la minuta. | Separación entre AsignacionEvaluacion y Evaluacion; se documentan las limitaciones de privacidad aún pendientes. |
| EstudianteOrdinario/Erasmus y ProfesorFijo/Temporal introducen cuatro subclases sin diferencias estructurales suficientes en sus evaluaciones. | Añaden complejidad e inducen a tratar las sustituciones como jerarquía de tipos. | Estudiante con condición Erasmus; Profesor único y varias Docencia para las imparticiones. |
| Semestre organiza directamente Asignatura en v2. | Puede interpretarse que una materia del catálogo pertenece a un único semestre. | Semestre sitúa Docencia; Asignatura conserva su identidad independiente. |
| ResumenDocente tiene grado, pero la evaluación no determina inequívocamente el grado de la docencia mediante sus asociaciones. | La procedencia de la agrupación de resultados queda insuficientemente expresada. | Grado forma parte del contexto de Docencia, con las reservas de S-01 y D-03. |
| Los resúmenes, medias, comentario, pregunta abierta y calendario aparecen como numerosas clases. | Mezcla información derivada con contenido básico y amplía el diagrama sin aportar siempre identidad propia. | Resultados derivados; observaciones y fechas como atributos. Se conserva su significado en reglas y glosario. |
| La escala añade etiquetas de acuerdo/desacuerdo no especificadas; el glosario presenta la semana 10 como fija. | Convierte interpretaciones en requisitos. | Valores 1..5 sin etiquetas añadidas y fechas configurables. Fórmulas y ambigüedades se marcan como propuestas. |
| No había escenarios de objetos ni vista dinámica del envío. | Era difícil contrastar los casos de sustitución y abandono con la estructura. | E-01, E-02 y actividad de envío individual, con comprobaciones de consistencia. |

## Referencias consultadas y aplicación

Consulta realizada el 20/11/2026. Las referencias orientan la forma de trabajar; la fuente de requisitos de este proyecto sigue siendo su propia minuta.

| Referencia | Qué aporta | Aplicación y límites |
| --- | --- | --- |
| [Repositorio de la asignatura 26–27: «A día de hoy»](https://github.com/mmasias/26-27-idsw1/blob/main/temario/aDiaDeHoy.md) | Sitúa el modelo del dominio entre los contenidos trabajados. | Se mantiene el alcance inicial. No se presupone que el equipo deba entregar ya todas las disciplinas o fases. |
| [Apuntes generales: modelo del dominio](https://github.com/mmasias/idsw1/blob/main/temario/contenidos/00004-MdD.md) | Conceptos del mundo real, asociaciones necesarias, atributos relevantes, distintas vistas y revisión de consistencia. | Lenguaje conceptual, ausencia de claves y métodos técnicos, estructura mínima justificada. |
| [Apuntes generales: disciplina de requisitos](https://github.com/mmasias/idsw1/blob/main/temario/00003-disciplinaDeRequisitos.md) | Distingue encontrar, priorizar, detallar y prototipar casos de uso. | No se amplía el issue #16 al trabajo de casos de uso del #15. |
| [Rúbrica de MdD del repositorio 25–26](https://github.com/mmasias/25-26-IdSw1-SdR/blob/main/documents/l%27Rubrica.MdD.md) | Glosario, dos escenarios, vista dinámica y validación explícita. | Se añaden las vistas y se reconoce que falta validación. Se consulta como referencia histórica, no como confirmación de los criterios vigentes de 26–27. |
| [Rúbrica de trazabilidad 25–26](https://github.com/mmasias/25-26-IdSw1-SdR/blob/main/documents/l%27Rubrica.T.md) | Historia Git, issues, PR y referencias entre artefactos. | Se enlaza evidencia real y se explica la evolución sin fabricar aprobaciones, reuniones o actividad retroactiva. |
| [Modelo de Martín López](https://github.com/martinlopez7/25-26-IdSw1-SdR/tree/main/documents/modelos/diagramas) | Separación de clases, objetos y estados, más explicación de cardinalidades. | Se adopta la separación de vistas y sus fuentes/SVG. Su dominio es generación de exámenes: no se trasladan sus entidades, multiplicidades, claves de corrección ni estructura de navegación. |

El ejemplo de Martín es útil como organización, pero no es una plantilla semántica: por ejemplo, sus supuestos sobre un profesor por asignatura no encajan con nuestra minuta. Sus asociaciones y la tabla de cardinalidades tampoco deben copiarse sin contrastarlas.

## Qué faltaba y qué queda para después

| Elemento observado en las referencias | Situación tras esta propuesta |
| --- | --- |
| Glosario consistente con las clases. | Actualizado para los doce conceptos, los términos derivados y los nombres propuestos. |
| Multiplicidades explicadas y decisiones visibles. | Documentadas en v3, separando reglas, propuestas y dudas. |
| Dos escenarios de objetos y vista dinámica. | Añadidos con datos ficticios y omisiones gráficas expresas. Se elige actividad porque explica mejor el abandono y el envío que un simple estado «pendiente/enviada». |
| Evolución verificable y fuentes editables. | v1 recuperada, v2 conservada y v3 acompañada de PUML/SVG. |
| Validación explícita del cliente. | Sigue pendiente. La aprobación interna para trabajar en el issue #16 no equivale a validar el modelo. |
| Encontrar, priorizar, detallar y prototipar casos de uso. | Trabajo posterior; la identificación ya está en #15. No es un defecto que este PR de dominio no los implemente. |
| Navegación, índices generales y presentación del repositorio. | Fuera del encargo actual; no se modifica el README ni se añaden README de índices. |

La rúbrica histórica valora agregación/composición y menciona cantidades de atributos, pero no se introducen ahora: el alcance pedido es trabajar sin esas relaciones y evitar atributos inventados. La adecuación a la evaluación de este curso deberá contrastarse con el profesor cuando corresponda.

---

[Índice provisional](indice-provisional.md) · [← Reglas y dudas](trazabilidad-v3.md) · [Uso de IA →](AI-uso.md) · [Volver arriba](#evolución-del-modelo-del-dominio)
