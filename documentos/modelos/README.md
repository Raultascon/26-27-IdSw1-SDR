# Modelo del dominio · Guía de lectura

Índice de la documentación del modelo del dominio v3. Puedes empezar por el modelo y consultar el resto según lo necesites; no hace falta leer todos los documentos de principio a fin.

## Organización de la carpeta

```text
modelos/
├── README.md                 Guía de lectura y accesos
├── documentacion/            Modelo v3, glosario, escenarios y reglas
├── diagramas/                Diagramas de v3: fuente PUML e imagen SVG juntas
│   ├── clases/
│   ├── objetos/
│   └── actividad/
├── seguimiento/              Evolución del modelo y registro de uso de IA
└── historico/                Versiones anteriores, conservadas sin cambios
    ├── v1/
    └── v2/
```

La propuesta actual se consulta en `documentacion/` y `diagramas/`. La comparación con versiones anteriores y el registro de trabajo están en `seguimiento/`; los archivos de v1 y v2 se reservan para consulta histórica.

## Orden de lectura

| Paso | Documento | Para qué leerlo |
| --- | --- | --- |
| 1 | [Modelo del dominio v3](documentacion/dominio-v3.md) | Entender las clases, sus relaciones y cómo se envía una evaluación. Es el documento principal. |
| 2 | [Glosario](documentacion/glosario.md) | Consultar qué significa cada concepto, especialmente Docencia, AsignacionEvaluacion y Evaluacion. |
| 3 | [Escenarios con objetos](documentacion/escenarios-v3.md) | Ver dos ejemplos concretos: una sustitución y respuestas separadas por grado. |
| 4 | [Reglas y decisiones](documentacion/trazabilidad-v3.md) | Comprobar de dónde sale cada regla y cómo se representa en el modelo. |
| 5 | [Evolución y referencias](seguimiento/evolucion.md) | Entender qué cambia respecto a v1/v2 y qué aportan los trabajos anteriores. |
| 6 | [Uso de IA](seguimiento/AI-uso.md) | Consultar el registro de asistencia con IA, incluida la entrada de v3. |

Para una primera revisión visual, lee **Modelo → Escenarios** y abre el glosario cuando aparezca un término poco claro. Para revisar la justificación, continúa con **Reglas y decisiones → Evolución**.

## Ir directamente a lo que buscas

| Quiero… | Ir a… |
| --- | --- |
| Ver las clases y sus relaciones. | [Diagrama y explicación](documentacion/dominio-v3.md#clases-conceptuales) · [SVG ampliable](diagramas/clases/clases.svg) · [PUML](diagramas/clases/clases.puml). |
| Entender los números de las relaciones. | [Asociaciones y multiplicidades](documentacion/dominio-v3.md#asociaciones-y-multiplicidades). |
| Ver qué pasa al enviar o abandonar. | [Envío y conservación](documentacion/dominio-v3.md#envío-y-conservación) · [Actividad en SVG](diagramas/actividad/actividad.svg) · [PUML](diagramas/actividad/actividad.puml). |
| Ver el ejemplo de sustitución. | [Escenario E-01](documentacion/escenarios-v3.md#e-01--dos-asignaturas-sustitución-y-abandono) · [Objetos en SVG](diagramas/objetos/objetos-01.svg) · [PUML](diagramas/objetos/objetos-01.puml). |
| Ver el ejemplo de respuestas por grado. | [Escenario E-02](documentacion/escenarios-v3.md#e-02--contenido-anónimo-y-separación-por-grado) · [Objetos en SVG](diagramas/objetos/objetos-02.svg) · [PUML](diagramas/objetos/objetos-02.puml). |
| Consultar una regla RN o una decisión S. | [Reglas del negocio](documentacion/trazabilidad-v3.md#reglas-del-negocio) · [Decisiones propuestas](documentacion/trazabilidad-v3.md#decisiones-propuestas-y-restricciones-de-consistencia). |
| Revisar situaciones que el modelo debe admitir o impedir. | [Comprobaciones de consistencia](documentacion/escenarios-v3.md#comprobaciones-de-consistencia). |
| Comparar con las versiones anteriores. | [Versiones y archivos históricos](seguimiento/evolucion.md#versiones-y-evidencia) · [Explicación de los cambios](seguimiento/evolucion.md#revisión-de-v1-y-v2). |
| Volver a lo que dijo el cliente. | [Minuta de la sesión 01](../sesiones/sesion01.md#notas-de-la-sesión-del-26-10-2026). |

## Qué significan las referencias

El número identifica una entrada concreta; no indica importancia ni orden de ejecución. Son referencias de documentación, no símbolos de UML.

| Prefijo | Significado | Dónde se define |
| --- | --- | --- |
| **RN-01, RN-02…** | Regla de negocio recogida en la minuta. | [Reglas del negocio](documentacion/trazabilidad-v3.md#reglas-del-negocio). |
| **S-01, S-02…** | Decisión o supuesto propuesto para representar el dominio; no equivale a un requisito confirmado. | [Decisiones propuestas](documentacion/trazabilidad-v3.md#decisiones-propuestas-y-restricciones-de-consistencia). |
| **E-01, E-02** | Escenario de ejemplo con datos ficticios. | [Escenarios](documentacion/escenarios-v3.md). |
| **C-01, C-02…** | Comprobación de consistencia del modelo. | [Comprobaciones](documentacion/escenarios-v3.md#comprobaciones-de-consistencia). |

Los documentos de v3 tienen enlaces de navegación al principio y al final. Los históricos se consultan desde Evolución y conservan su contenido original.

---

[Empezar por el modelo →](documentacion/dominio-v3.md) · [Volver arriba](#modelo-del-dominio--guía-de-lectura)
