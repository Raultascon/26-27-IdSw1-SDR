<p align="center">
  <img src="../../documentos/recursos/cabecera-casos.svg" alt="Encuestas de evaluación docente · Casos de uso · Guía de lectura · UNEATLANTICO" width="1200">
</p>

<p align="center">
<a href="../../README.md"><img src="../../documentos/recursos/inicio.svg" alt="Inicio" height="32"></a>
<a href="../../documentos/sesiones/README.md"><img src="../../documentos/recursos/sesiones.svg" alt="Sesiones" height="32"></a>
<a href="../../documentos/modelos/README.md"><img src="../../documentos/recursos/modelo.svg" alt="Dominio" height="32"></a>
<a href="../../documentos/casos-uso/README.md"><img src="../../documentos/recursos/casos.svg" alt="Casos de uso" height="32"></a>
<a href="../../documentos/modelos/documentacion/glosario.md"><img src="../../documentos/recursos/glosario.svg" alt="Glosario" height="32"></a>
<a href="../../documentos/AI-uso.md"><img src="../../documentos/recursos/ia.svg" alt="Uso de IA" height="32"></a>
</p>

# Casos de uso · Guía de lectura

Documentación de actores y casos de uso del sistema de encuestas. La propuesta vigente es el **refactor v3 del issue #22**, integrado en `develop`; el documento conserva la v2 original y explica los cambios en una sección propia.

<details>
<summary>En esta página</summary>

- <a href="#orden-de-lectura"><img src="../../documentos/recursos/seccion.svg" alt="Ir a Orden de lectura" width="20"></a> Orden de lectura
- <a href="#actores-y-casos-de-uso-v3"><img src="../../documentos/recursos/seccion.svg" alt="Ir a Actores y casos de uso v3" width="20"></a> Actores y casos de uso v3
- <a href="#diagramas-de-contexto"><img src="../../documentos/recursos/seccion.svg" alt="Ir a Diagramas de contexto" width="20"></a> Diagramas de contexto
- <a href="#versiones-y-seguimiento"><img src="../../documentos/recursos/seccion.svg" alt="Ir a Versiones y seguimiento" width="20"></a> Versiones y seguimiento
- <a href="#organización-de-la-carpeta"><img src="../../documentos/recursos/seccion.svg" alt="Ir a Organización de la carpeta" width="20"></a> Organización de la carpeta

</details>

## Orden de lectura

| Paso | Contenido | Acceso |
| :--- | :--- | :--- |
| 1 | Refactor v3 y cambios respecto a v2 | <a href="documentacion/actores-casos-uso.md#refactor-v3-issue-22"><img src="../../documentos/recursos/leer.svg" alt="Leer el refactor v3" height="32"></a> |
| 2 | Actores y catálogo de casos de uso v3 | <a href="documentacion/actores-casos-uso.md#catálogo-de-casos-de-uso-v3"><img src="../../documentos/recursos/leer.svg" alt="Leer el catálogo de casos de uso v3" height="32"></a> |
| 3 | Glosario de actores y casos de uso | <a href="documentacion/actores-casos-uso.md#glosario-de-actores-y-casos-de-uso"><img src="../../documentos/recursos/glosario.svg" alt="Consultar glosario de actores y casos de uso" height="32"></a> |
| 4 | Trazabilidad y exclusiones del dominio | <a href="documentacion/actores-casos-uso.md#trazabilidad-y-exclusiones-del-dominio-v3"><img src="../../documentos/recursos/leer.svg" alt="Leer trazabilidad de los casos de uso" height="32"></a> |
| 5 | Asistencia con IA en v1, v2 y v3 | <a href="../AI-uso.md#actores-y-casos-de-uso-v1-y-v2"><img src="../../documentos/recursos/ia.svg" alt="Consultar uso de IA en casos de uso" height="32"></a> |

## Actores y casos de uso v3

<a href="diagramas/actoresCasosUso.svg"><img src="diagramas/actoresCasosUso.svg" alt="Diagrama de actores y casos de uso v3; abrir para ampliar" width="1000"></a>

<a href="diagramas/actoresCasosUso.svg"><img src="../../documentos/recursos/imagen.svg" alt="Ampliar actores y casos de uso v3" height="32"></a> <a href="diagramas/actoresCasosUso.puml"><img src="../../documentos/recursos/codigo.svg" alt="Abrir fuente PlantUML de actores y casos de uso" height="32"></a>

El rol abstracto `ConsultorResultados` agrupa los roles de consulta. Campus Virtual / Panal figura como actor secundario. Los roles de Director de grado y Departamento de calidad y las operaciones de gestión propuestas siguen sujetos a confirmación del cliente, como indica el documento del refactor.

## Diagramas de contexto

| Gestor | Alumno |
| :---: | :---: |
| <a href="diagramas/diagramaContexto-gestor.svg"><img src="diagramas/diagramaContexto-gestor.svg" alt="Contexto del Gestor; abrir para ampliar" width="420"></a> | <a href="diagramas/diagramaContexto-alumno.svg"><img src="diagramas/diagramaContexto-alumno.svg" alt="Contexto del Alumno; abrir para ampliar" width="420"></a> |
| <a href="diagramas/diagramaContexto-gestor.svg"><img src="../../documentos/recursos/imagen.svg" alt="Ampliar contexto del Gestor" height="32"></a> <a href="diagramas/diagramaContexto-gestor.puml"><img src="../../documentos/recursos/codigo.svg" alt="Abrir fuente PlantUML del contexto del Gestor" height="32"></a> | <a href="diagramas/diagramaContexto-alumno.svg"><img src="../../documentos/recursos/imagen.svg" alt="Ampliar contexto del Alumno" height="32"></a> <a href="diagramas/diagramaContexto-alumno.puml"><img src="../../documentos/recursos/codigo.svg" alt="Abrir fuente PlantUML del contexto del Alumno" height="32"></a> |

## Versiones y seguimiento

| Versión | Contenido | Diagrama | Fuente |
| :--- | :--- | :--- | :--- |
| v1 · Issue #15 | Asociaciones directas | <a href="historico/v1/actoresCasosUso-v1.svg"><img src="../../documentos/recursos/imagen.svg" alt="Ver diagrama histórico v1" height="32"></a> | <a href="historico/v1/actoresCasosUso-v1.puml"><img src="../../documentos/recursos/codigo.svg" alt="Abrir fuente histórica v1" height="32"></a> |
| v2 · Issue #15 | Generalización desde Profesor, conservada como referencia | <a href="historico/v2/actoresCasosUso-v2.svg"><img src="../../documentos/recursos/imagen.svg" alt="Ver diagrama histórico v2" height="32"></a> | <a href="historico/v2/actoresCasosUso-v2.puml"><img src="../../documentos/recursos/codigo.svg" alt="Abrir fuente histórica v2" height="32"></a> |
| v3 · Issue #22 | ConsultorResultados, Panal y gestión de campaña | <a href="diagramas/actoresCasosUso.svg"><img src="../../documentos/recursos/imagen.svg" alt="Ver diagrama vigente v3" height="32"></a> | <a href="diagramas/actoresCasosUso.puml"><img src="../../documentos/recursos/codigo.svg" alt="Abrir fuente vigente v3" height="32"></a> |

Seguimiento: [identificación inicial · #15](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/15), [refactor · #22](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/22) e [integración · PR #24](https://github.com/Raultascon/26-27-IdSw1-SDR/pull/24).

## Organización de la carpeta

```text
casos-uso/
├── README.md        Guía de lectura y accesos
├── documentacion/   Identificación v2 y refactor v3 con registro de cambios
├── diagramas/       Diagramas vigentes: fuente PUML e imagen SVG juntas
└── historico/       Iteraciones v1 y v2 conservadas como referencia
```

La priorización, el detallado con criterios de aceptación y el prototipado están pendientes. Se abordarán a partir de los casos acordados con el cliente.

---

<p align="center">
<a href="../../README.md"><img src="../../documentos/recursos/inicio.svg" alt="Inicio" height="32"></a>
<a href="../../documentos/CONVENCIONES.md"><img src="../../documentos/recursos/normas.svg" alt="Convenciones" height="32"></a>
<a href="../../documentos/AI-uso.md"><img src="../../documentos/recursos/ia.svg" alt="Uso de IA" height="32"></a>
<a href="#"><img src="../../documentos/recursos/arriba.svg" alt="Subir" height="32"></a>
</p>

<p align="center"><sub>Ingeniería del Software I · UNEATLANTICO · 2026–2027</sub></p>
