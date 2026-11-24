<p align="center">
  <img src="documentos/recursos/portada.svg" alt="Encuestas de evaluación docente · Encuestas de evaluación docente · UNEATLANTICO" width="1200">
</p>

<p align="center">
<a href="README.md"><img src="documentos/recursos/inicio.svg" alt="Inicio" height="32"></a>
<a href="documentos/sesiones/README.md"><img src="documentos/recursos/sesiones.svg" alt="Sesiones" height="32"></a>
<a href="documentos/modelos/README.md"><img src="documentos/recursos/modelo.svg" alt="Dominio" height="32"></a>
<a href="documentos/casos-uso/README.md"><img src="documentos/recursos/casos.svg" alt="Casos de uso" height="32"></a>
<a href="documentos/modelos/documentacion/glosario.md"><img src="documentos/recursos/glosario.svg" alt="Glosario" height="32"></a>
<a href="documentos/AI-uso.md"><img src="documentos/recursos/ia.svg" alt="Uso de IA" height="32"></a>
</p>

# Encuestas de evaluación docente

Proyecto de requisitado de **Ingeniería del Software I · Curso 2026–2027**. Documentación elaborada a partir de la primera reunión con el cliente, celebrada el **26/10/2026**.

<details>
<summary>En esta página</summary>

- <a href="#el-proyecto"><img src="documentos/recursos/seccion.svg" alt="Ir a El proyecto" width="20"></a> El proyecto
- <a href="#explorar-la-documentación"><img src="documentos/recursos/seccion.svg" alt="Ir a Explorar la documentación" width="20"></a> Explorar la documentación
- <a href="#estado-de-los-entregables"><img src="documentos/recursos/seccion.svg" alt="Ir a Estado de los entregables" width="20"></a> Estado de los entregables
- <a href="#próximos-pasos-y-referencias"><img src="documentos/recursos/seccion.svg" alt="Ir a Próximos pasos y referencias" width="20"></a> Próximos pasos y referencias
- <a href="#equipo"><img src="documentos/recursos/seccion.svg" alt="Ir a Equipo" width="20"></a> Equipo
- <a href="#estructura-del-repositorio"><img src="documentos/recursos/seccion.svg" alt="Ir a Estructura del repositorio" width="20"></a> Estructura del repositorio
- <a href="#flujo-de-trabajo"><img src="documentos/recursos/seccion.svg" alt="Ir a Flujo de trabajo" width="20"></a> Flujo de trabajo

</details>

## El proyecto

El sistema automatiza las encuestas semestrales de satisfacción docente. Cada estudiante elegible recibe las evaluaciones de los profesores que le han impartido cada asignatura. La participación es voluntaria y las respuestas son anónimas. El cuestionario contiene 11 ítems obligatorios, puntuados del 1 al 5, y un campo opcional de observaciones.

El administrador fija las fechas de la convocatoria. El sistema avisa por el campus virtual y por correo, conserva cada evaluación enviada y publica los resultados al cierre. Los resultados se separan por grado y se pueden exportar a PDF o Excel. La integración con el entorno universitario se plantea como una simulación. [Minuta de la sesión 01](documentos/sesiones/sesion01.md#notas-de-la-sesión-del-26-10-2026)

## Explorar la documentación

| Sesiones con el cliente | Modelo del dominio | Actores y casos de uso |
| :--- | :--- | :--- |
| Preguntas, minuta y cuestionario de la primera reunión. | Conceptos, glosario, escenarios y reglas trazadas a la minuta. | Catálogo de negocio, refactor v3 y diagramas de contexto. |
| <a href="documentos/sesiones/README.md"><img src="documentos/recursos/sesiones.svg" alt="Sesiones" height="32"></a> | <a href="documentos/modelos/README.md"><img src="documentos/recursos/modelo.svg" alt="Dominio" height="32"></a> | <a href="documentos/casos-uso/README.md"><img src="documentos/recursos/casos.svg" alt="Casos de uso" height="32"></a> |

**Ruta de lectura:** minuta → modelo del dominio y reglas → actores y casos de uso. Las decisiones propuestas se distinguen de lo confirmado por el cliente.

## Estado de los entregables

Estado documental tras la sesión 01 y la integración del refactor del issue #22 en `develop`. La integración en Git no implica validación del cliente.

| Entregable | Estado | Consultar |
| :--- | :--- | :--- |
| Minuta de la sesión 01 | Documentada | <a href="documentos/sesiones/sesion01.md"><img src="documentos/recursos/leer.svg" alt="Consultar Minuta de la sesión 01" height="32"></a> |
| Modelo del dominio v3 | Documentado; pendiente de validación con el cliente | <a href="documentos/modelos/documentacion/dominio-v3.md"><img src="documentos/recursos/leer.svg" alt="Consultar Modelo del dominio v3" height="32"></a> |
| Glosario y escenarios | Documentados como parte del modelo v3 | <a href="documentos/modelos/README.md#orden-de-lectura"><img src="documentos/recursos/leer.svg" alt="Consultar Glosario y escenarios" height="32"></a> |
| Reglas y decisiones | Trazadas a la minuta; supuestos identificados | <a href="documentos/modelos/documentacion/trazabilidad-v3.md"><img src="documentos/recursos/leer.svg" alt="Consultar Reglas y decisiones" height="32"></a> |
| Actores y casos de uso v3 | Refactor integrado; propuestas pendientes de validar | <a href="documentos/casos-uso/documentacion/actores-casos-uso.md#refactor-v3-issue-22"><img src="documentos/recursos/leer.svg" alt="Consultar Actores y casos de uso v3" height="32"></a> |
| Diagramas de contexto | Gestor y Alumno integrados | <a href="documentos/casos-uso/README.md#diagramas-de-contexto"><img src="documentos/recursos/leer.svg" alt="Consultar Diagramas de contexto" height="32"></a> |
| Priorización de casos de uso | Pendiente de acordar con el cliente | — |
| Detallado y criterios de aceptación | Pendientes para los casos priorizados | — |
| Prototipado de casos de uso | Pendiente para validar los flujos | — |

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

## Flujo de trabajo

1. Registrar cada tarea en un issue y enlazar las decisiones debatidas en Discussions.
2. Trabajar en una rama por issue desde `develop`: `tipo/issue-N-descripcion`. Referenciar el issue en los commits con `[refs #N]`.
3. Revisar mediante pull request hacia `develop`, con al menos una aprobación de otro integrante. Integrar en `main` mediante pull request desde `develop`.
4. Vincular los artefactos a la minuta y registrar la asistencia con IA y su revisión humana.

<p>
<a href="https://github.com/Raultascon/26-27-IdSw1-SDR/issues"><img src="documentos/recursos/issues.svg" alt="Issues" height="32"></a>
<a href="https://github.com/Raultascon/26-27-IdSw1-SDR/discussions"><img src="documentos/recursos/debate.svg" alt="Discussions" height="32"></a>
<a href="documentos/CONVENCIONES.md"><img src="documentos/recursos/normas.svg" alt="Convenciones" height="32"></a>
</p>

<details>
<summary>Identidad visual y procedencia</summary>

Paleta inspirada en las capturas de Panal aportadas por el equipo: azul `#0086C9`, pizarra `#2C3540`, gris claro `#F3F5F6` y blanco. Los SVG de `documentos/recursos/` son recursos propios de este proyecto académico; la marca de encuesta no es un logotipo oficial de la universidad. La navegación visual y las vistas de diagramas toman como referencia la organización de Jorgestor.

</details>

---

<p align="center">
<a href="README.md"><img src="documentos/recursos/inicio.svg" alt="Inicio" height="32"></a>
<a href="documentos/CONVENCIONES.md"><img src="documentos/recursos/normas.svg" alt="Convenciones" height="32"></a>
<a href="documentos/AI-uso.md"><img src="documentos/recursos/ia.svg" alt="Uso de IA" height="32"></a>
<a href="#"><img src="documentos/recursos/arriba.svg" alt="Subir" height="32"></a>
</p>

<p align="center"><sub>Ingeniería del Software I · UNEATLANTICO · 2026–2027</sub></p>
