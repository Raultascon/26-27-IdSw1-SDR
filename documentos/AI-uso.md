## Declaración de Uso de IA

## Herramientas Utilizadas
- **Herramientas:** Google Gemini, Claude (Anthropic)
- **Fechas:** 2026-11-23 a 2026-11-24

## Contexto de Uso por Artefacto

### Actores y Casos de Uso · v1 y v2 ([Issue #15](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/15))
- **¿Se usó?:** Sí
- **Propósito:** Estructurar la documentación funcional (`documentos/casos-uso/documentacion/actores-casos-uso.md`) trazada al Modelo del dominio v3 y a la minuta de la sesión 01, generar el código fuente PlantUML para las iteraciones `v1` (`actoresCasosUso.puml`) y `v2` (`actoresCasosUso-v2.puml`), y redactar la guía de lectura (`documentos/casos-uso/README.md`).
- **Evaluación crítica:**
  - **Aceptado:** Modelado de los 6 actores externos fuera de la frontera del sistema (`Gestor (ordenación académica)`, `Alumno`, `Tiempo`, `Profesor`, `Director de grado` y `Departamento de calidad`), redacción de los casos de uso a nivel de negocio y refactorización en `v2` mediante herencia (`--|>`) desde `Profesor` hacia `Director de grado` y `Departamento de calidad`.
  - **Rechazado:** Propuestas intermedias con relaciones `<<include>>`, verbos de apertura de pantalla (`abrir...()`), división en múltiples diagramas funcionales por versión y enlaces superiores de navegación (`Índice`) innecesarios.

### Refactor de actores y casos de uso · v3 ([Issue #22](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/22))
- **¿Se usó?:** Sí
- **Propósito:** Apoyo para revisar el PR #19 frente a la minuta de la sesión 01, redactar la propuesta de mejoras publicada en Discussions y aplicar en los archivos los cambios acordados por el equipo en el Issue #22, con un commit por cambio.
- **Evaluación crítica:**
  - **Aceptado tras revisión:** actor abstracto `ConsultorResultados` en lugar de la herencia desde `Profesor`; herencia del `Gestor` desde ese rol (comprobada con la sesión 01); Campus Virtual / Panal como actor secundario; casos de uso de gestión de convocatoria y asignaciones (marcados como pendientes de validar con el cliente); diagramas de contexto y glosario propio enlazado al del modelo del dominio.
  - **Rechazado:** mover los diagramas a una carpeta `modelosUML`, porque el resto del repositorio usa `diagramas/` y cambiarlo solo en casos de uso rompía la coherencia. Se deja como decisión de grupo.
  - **Rechazado:** modelar el Servidor de correo como actor secundario. El correo es solo un canal de notificación y no una entidad externa con interacción propia.
  - **Corregido por el equipo:** la propuesta inicial sustituía el contenido de la v2. Se decidió conservar el texto original de la v2 y documentar el refactor en una sección propia con registro de cambios, para mantener la trazabilidad.

## Trazabilidad de Conversaciones

### Conversación 1: Identificación de actores y casos de uso (Issue #15)
- **URL:** `https://share.gemini.google/WByScE1PAU3p`
- **Fecha:** 2026-11-23
- **Resumen:** Definición del catálogo de casos de uso a nivel de negocio para los 6 actores externos, generación de los diagramas PlantUML (`v1` con asociaciones directas y `v2` con herencia de roles de consulta) y redacción de la documentación y guía de lectura tras depurar errores de abstracción y formato señalados durante la revisión.
- **Commits asociados:**
  - [`4acc0cd`](https://github.com/Raultascon/26-27-IdSw1-SDR/commit/4acc0cd) (`feat(cu): añade diagramas v1 y v2 de actores y casos de uso [refs #15]`)
  - [`d6c9a0a`](https://github.com/Raultascon/26-27-IdSw1-SDR/commit/d6c9a0a) (`docs(cu): documenta actores y casos de uso a nivel de negocio [refs #15]`)
  - Commits posteriores de corrección (`fix(cu)`) y guía de lectura (`docs(cu)`) vinculados a `[refs #15]` en la rama `feat/issue-15-encontrar-actores-y-casos-de-uso`

### Conversación 2: Revisión del PR #19 y refactor de actores y casos de uso (Issue #22)
- **URL:** `https://claude.ai/code/session_01SfiCNLLgbq132FYQ84Y1eY`
- **Fecha:** 2026-11-23 a 2026-11-24
- **Resumen:** Apoyo en la revisión del PR #19 y en la aplicación del refactor acordado en Discussions. La IA propuso alternativas y aplicó los cambios en la rama `refactor/issue-22-refactorizar-actores-y-casos-de-uso`; el equipo decidió qué cambios aceptar, cuáles descartar y cómo documentarlos, y revisó el resultado antes de subirlo.
- **Commits asociados:**
  - `d87b04b` (`refactor(cu): unifica diagrama y añade actor abstracto ConsultorResultados [refs #22]`)
  - `5e3b9d5` (`fix(cu): asocia consulta y exportación de resultados al Gestor [refs #22]`)
  - `653e87e` (`feat(cu): añade Campus Virtual y Servidor de correo como actores secundarios [refs #22]`)
  - `f522d34` (`feat(cu): añade casos de uso de gestión de convocatoria y asignaciones [refs #22]`)
  - `2dac07b` (`feat(cu): añade diagramas de contexto del Gestor y del Alumno [refs #22]`)
  - `e6ecbe0` (`docs(cu): añade glosario de actores y casos de uso [refs #22]`)
  - `f65f73c` (`docs(cu): registra la revisión v3 en la información del artefacto [refs #22]`)
  - `b7fa992` (`refactor(cu): retira Servidor de correo como actor secundario [refs #22]`)
  - `ab412c1` (`feat(cu): exporta diagramas v3 y de contexto a SVG [refs #22]`)
  - `3b4257f` (`fix(cu): corrige enlace roto al modelo del dominio v3 [refs #22]`)
  - `4880ae1` (`docs(cu): conserva la versión v2 y documenta el refactor v3 en sección propia [refs #22]`)

## Validación Humana

- **Mecanismos de validación:** Revisión crítica de cada propuesta generada por la IA contrastándola con los criterios explicados por el profesor en clase, la minuta de la sesión 01 (`sesion01.md`) y el Modelo del dominio v3 (`modelo-v3.md`), además de comprobar visualmente el renderizado de diagramas `.svg` y enlaces en GitHub.
- **Errores detectados:**
  - **Abuso de `<<include>>` y mezcla de niveles de abstracción:** Al mostrarle un repositorio antiguo de ejemplo (`pySigHor`), la IA copió literalmente ese patrón introduciendo flechas `<<include>>` y casos de uso de navegación de interfaz (`abrirCuestionario()`, `abrirConvocatorias()`, `abrirAsignaciones()`). Se rechazó porque en clase se indicó evitar el uso excesivo de `<<include>>`/`<<extend>>` y mantener esta primera iteración estrictamente a nivel de negocio sin detalles técnicos ni de pantalla.
  - **Cruce innecesario de flechas en `v1`:** La propuesta inicial de la IA conectaba por separado a `Profesor`, `Director de grado` y `Departamento de calidad` con los casos de uso de consulta y exportación, generando 6 líneas cruzadas difíciles de leer. Se le indicó aplicar herencia (`--|>`) en una segunda iteración (`v2`) siguiendo las buenas prácticas vistas en clase.
  - **División errónea de diagramas y enlaces rotos:** La IA sugirió dividir una misma iteración en dos diagramas distintos (`001` y `002`) en lugar de mantener un único diagrama por iteración, e incluyó enlaces superiores al índice que no cargaban o sobraban en los archivos Markdown, por lo que se le ordenó eliminarlos.
  - **Actores sin respaldo en la minuta (Issue #22):** Al contrastar el catálogo con la sesión 01 se detectó que `Director de grado` y `Departamento de calidad` no aparecen en ella; la minuta solo menciona al administrador y a los profesores como receptores de resultados. Se mantienen en `v3`, pero se propone confirmarlos con el cliente mediante un Issue `[Duda]`.
