# Índice provisional del modelo del dominio

Guía de lectura para revisar la propuesta v3. Puedes empezar por el modelo y consultar el resto según lo necesites; no hace falta leer todos los documentos de principio a fin.

## Orden de lectura

| Paso | Documento | Para qué leerlo |
| --- | --- | --- |
| 1 | [Modelo del dominio v3](dominio-v3.md) | Entender las clases, sus relaciones y cómo se envía una evaluación. Es el documento principal. |
| 2 | [Glosario](glosario.md) | Consultar qué significa cada concepto, especialmente Docencia, AsignacionEvaluacion y Evaluacion. |
| 3 | [Escenarios con objetos](escenarios-v3.md) | Ver dos ejemplos concretos: una sustitución y respuestas separadas por grado. |
| 4 | [Reglas, decisiones y dudas](trazabilidad-v3.md) | Comprobar de dónde sale cada regla y qué falta preguntar al cliente. |
| 5 | [Evolución y referencias](evolucion.md) | Entender qué cambia respecto a v1/v2 y qué aportan los trabajos anteriores. |
| 6 | [Uso de IA](AI-uso.md) | Consultar el registro de asistencia con IA, incluida la entrada de v3. |

Para una primera revisión visual, lee **Modelo → Escenarios** y abre el glosario cuando aparezca un término poco claro. Para revisar la justificación, continúa con **Reglas y dudas → Evolución**.

## Ir directamente a lo que buscas

| Quiero… | Ir a… |
| --- | --- |
| Ver las clases y sus relaciones. | [Diagrama y explicación](dominio-v3.md#clases-conceptuales) · [SVG ampliable](imagenes/v3/clases.svg) · [PUML](modelosUML/v3/clases.puml). |
| Entender los números de las relaciones. | [Asociaciones y multiplicidades](dominio-v3.md#asociaciones-y-multiplicidades). |
| Ver qué pasa al enviar o abandonar. | [Envío y conservación](dominio-v3.md#envío-y-conservación) · [Actividad en SVG](imagenes/v3/actividad.svg) · [PUML](modelosUML/v3/actividad.puml). |
| Ver el ejemplo de sustitución. | [Escenario E-01](escenarios-v3.md#e-01--dos-asignaturas-sustitución-y-abandono) · [Objetos en SVG](imagenes/v3/objetos-01.svg) · [PUML](modelosUML/v3/objetos-01.puml). |
| Ver el ejemplo de respuestas por grado. | [Escenario E-02](escenarios-v3.md#e-02--contenido-anónimo-y-separación-por-grado) · [Objetos en SVG](imagenes/v3/objetos-02.svg) · [PUML](modelosUML/v3/objetos-02.puml). |
| Consultar una regla RN o una decisión S. | [Reglas del negocio](trazabilidad-v3.md#reglas-del-negocio) · [Decisiones propuestas](trazabilidad-v3.md#decisiones-propuestas-y-restricciones-de-consistencia). |
| Saber qué debemos preguntar al cliente. | [Preguntas pendientes](trazabilidad-v3.md#preguntas-para-la-siguiente-validación). |
| Revisar situaciones que el modelo debe admitir o impedir. | [Comprobaciones de consistencia](escenarios-v3.md#comprobaciones-de-consistencia). |
| Comparar con las versiones anteriores. | [Versiones y archivos históricos](evolucion.md#versiones-y-evidencia) · [Explicación de los cambios](evolucion.md#revisión-de-v1-y-v2). |
| Volver a lo que dijo el cliente. | [Minuta de la sesión 01](../sesiones/sesion01.md#notas-de-la-sesión-del-26-10-2026). |

## Qué significan las referencias

El número identifica una entrada concreta; no indica importancia ni orden de ejecución. Son referencias de documentación, no símbolos de UML.

| Prefijo | Significado | Dónde se define |
| --- | --- | --- |
| **RN-01, RN-02…** | Regla de negocio recogida en la minuta. | [Reglas del negocio](trazabilidad-v3.md#reglas-del-negocio). |
| **S-01, S-02…** | Decisión o supuesto propuesto para representar el dominio; no equivale a un requisito confirmado. | [Decisiones propuestas](trazabilidad-v3.md#decisiones-propuestas-y-restricciones-de-consistencia). |
| **D-01, D-02…** | Duda pendiente de aclarar con el cliente. | [Preguntas pendientes](trazabilidad-v3.md#preguntas-para-la-siguiente-validación). |
| **E-01, E-02** | Escenario de ejemplo con datos ficticios. | [Escenarios](escenarios-v3.md). |
| **C-01, C-02…** | Comprobación de consistencia del modelo. | [Comprobaciones](escenarios-v3.md#comprobaciones-de-consistencia). |

Los documentos de v3 tienen enlaces de navegación al principio y al final. Los históricos se consultan desde Evolución y conservan su contenido original.

---

[Empezar por el modelo →](dominio-v3.md) · [Volver arriba](#índice-provisional-del-modelo-del-dominio)
