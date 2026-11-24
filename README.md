# Encuestas de evaluación docente

Proyecto de requisitado de **Ingeniería del Software I · UNEATLANTICO · Curso 2026–2027**

[Sesiones con el cliente](documentos/sesiones/README.md) · [Modelo del dominio](documentos/modelos/README.md) · [Actores y casos de uso](documentos/casos-uso/README.md) · [Glosario](documentos/modelos/documentacion/glosario.md) · [Uso de IA](documentos/AI-uso.md)

**En esta página**

- [Descripción del sistema](#descripción-del-sistema)
- [Estado de los entregables](#estado-de-los-entregables)
- [Equipo](#equipo)
- [Estructura del repositorio](#estructura-del-repositorio)
- [Flujo de trabajo](#flujo-de-trabajo)

## Descripción del sistema

El sistema automatiza las encuestas semestrales de satisfacción docente. Cada estudiante elegible recibe las evaluaciones de los profesores que le han impartido cada asignatura. La participación es voluntaria y las respuestas son anónimas. El cuestionario contiene 11 ítems obligatorios, puntuados del 1 al 5, y un campo opcional de observaciones.

El administrador fija las fechas de la convocatoria. El sistema avisa por el campus virtual y por correo, conserva cada evaluación enviada y publica los resultados al cierre. Los resultados se separan por grado y se pueden exportar a PDF o Excel. La integración con el entorno universitario se plantea como una simulación. [Minuta de la sesión 01](documentos/sesiones/sesion01.md#notas-de-la-sesión-del-26-10-2026)

## Estado de los entregables

Estado tras la primera sesión con el cliente, celebrada el **26/10/2026**. La tabla recoge qué se ha documentado en la rama base y qué queda por preparar o validar.

| Entregable                   | Estado                                                | Evidencia o seguimiento                                                                                                                                                                                        |
| :--------------------------- | :---------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Minuta de la sesión 01       | Documentada                                           | [Minuta y cuestionario](documentos/sesiones/sesion01.md) · [Issue #10](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/10)                                                                                |
| Modelo del dominio v3        | Documentado, pendiente de validación con el cliente   | [Modelo y diagramas](documentos/modelos/README.md) · [Reglas y trazabilidad](documentos/modelos/documentacion/trazabilidad-v3.md) · [Issue #16](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/16)       |
| Glosario y escenarios        | Documentados como parte del modelo v3                 | [Glosario](documentos/modelos/documentacion/glosario.md) · [Escenarios](documentos/modelos/documentacion/escenarios-v3.md)                                                                                     |
| Actores y casos de uso       | Identificación inicial documentada, revisión en curso | [Catálogo y diagramas](documentos/casos-uso/README.md) · [Issue #15](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/15) · [Issue #22](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/22)           |
| Diagramas de contexto        | Pendientes de integración en `develop`                | [Discusión #18](https://github.com/Raultascon/26-27-IdSw1-SDR/discussions/18) · [Rama del issue #22](https://github.com/Raultascon/26-27-IdSw1-SDR/tree/refactor/issue-22-refactorizar-actores-y-casos-de-uso) |
| Priorización de casos de uso | Pendiente                                             | Acordar prioridades con el cliente.                                                                                                                                                                            |
| Detallado de casos de uso    | Pendiente                                             | Describir los flujos de los casos priorizados.                                                                                                                                                                 |
| Prototipado de casos de uso  | Pendiente                                             | Preparar vistas para validar los flujos con el cliente.                                                                                                                                                        |

Las etapas de priorización, detallado y prototipado se describen en la [disciplina de requisitos del temario](https://github.com/mmasias/idsw1/blob/main/temario/00003-disciplinaDeRequisitos.md).

## Equipo

| Integrante                | GitHub                                                         |
| :------------------------ | :------------------------------------------------------------- |
| Raúl Tascón (coordinador) | [@Raultascon](https://github.com/Raultascon)                   |
| Adrián Solar              | [@adriansolar](https://github.com/adriansolar)                 |
| Carlos Valdés Barquín     | [@carlosvaldesbarquin](https://github.com/carlosvaldesbarquin) |
| Diego Alonso Díaz         | [@Diego-alonsodiaz](https://github.com/Diego-alonsodiaz)       |
| Diego Arellano            | [@DiegoArellano30](https://github.com/DiegoArellano30)         |
| Héctor Ares Ibáñez        | [@hectorares3](https://github.com/hectorares3)                 |
| Marcos González Hidalgo   | [@mglezz](https://github.com/mglezz)                           |

## Estructura del repositorio

```text
.
├── README.md
└── documentos/
    ├── AI-uso.md
    ├── CONVENCIONES.md
    ├── casos-uso/
    │   ├── README.md
    │   ├── diagramas/
    │   └── documentacion/
    ├── modelos/
    │   ├── README.md
    │   ├── diagramas/
    │   │   ├── actividad/
    │   │   ├── clases/
    │   │   └── objetos/
    │   ├── documentacion/
    │   ├── historico/
    │   │   ├── v1/
    │   │   └── v2/
    │   └── seguimiento/
    └── sesiones/
        ├── README.md
        └── sesion01.md
```

## Flujo de trabajo

1. Registrar la tarea en un [issue](https://github.com/Raultascon/26-27-IdSw1-SDR/issues). Usar [Discussions](https://github.com/Raultascon/26-27-IdSw1-SDR/discussions) para debatir propuestas y enlazar las decisiones relevantes desde el issue.
2. Crear una rama por issue a partir de `develop`, con el patrón `tipo/issue-N-descripcion`. Referenciar el issue en cada commit con `[refs #N]`.
3. Abrir un pull request hacia `develop` y obtener al menos una aprobación de otro integrante antes de integrar. `main` recibe cambios desde `develop` mediante pull request.
4. Enlazar la minuta en los artefactos que deriven de la reunión y registrar el uso de IA cuando corresponda.

[Convenciones del equipo](documentos/CONVENCIONES.md) · [Materiales del curso 2026–2027](https://github.com/mmasias/26-27-idsw1) · [Volver arriba](#encuestas-de-evaluación-docente)
