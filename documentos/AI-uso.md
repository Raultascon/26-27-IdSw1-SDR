# Declaración de uso de IA

[Inicio](../README.md) · [Convenciones](CONVENCIONES.md)

Registro central de la asistencia con IA en el proyecto. Reúne las entradas de documentación y casos de uso de este archivo y las del modelo del dominio antes ubicadas en `modelos/seguimiento/AI-uso.md`. La ruta antigua se conserva como acceso a este registro.

Cada entrada recoge herramientas y fechas, contexto y evaluación crítica, trazabilidad de la conversación y validación. «No consta» indica información ausente en el registro original; no presupone que se realizara o no una revisión.

## Índice

- [Modelo del dominio v1](#modelo-del-dominio-v1)
- [Modelo del dominio v3](#modelo-del-dominio-v3)
- [Actores y casos de uso v1 y v2](#actores-y-casos-de-uso-v1-y-v2)
- [Refactor de actores y casos de uso v3](#refactor-de-actores-y-casos-de-uso-v3)
- [Estructuración inicial de la documentación](#estructuración-inicial-de-la-documentación)
- [Rediseño de README y unificación del registro](#rediseño-de-readme-y-unificación-del-registro)
- [Validación histórica de casos de uso](#validación-histórica-de-casos-de-uso)

## Modelo del dominio v1

### Herramientas y fechas

- **Herramienta:** Google Gemini.
- **Fecha de la conversación:** 2026-11-05 (el registro original indicaba noviembre de 2026 como periodo de uso).

### Contexto y evaluación crítica

- **¿Se usó?:** Sí
- **Propósito:** Asistencia técnica en la sintaxis de PlantUML para representar el diagrama de clases del modelo del dominio a partir de las entidades, atributos y relaciones conceptuales identificadas.
- **Evaluación crítica:** La IA propuso una estructuración básica en PlantUML. Se revisó y adaptó manualmente la jerarquía de herencia, las asociaciones y la nomenclatura para asegurar que se respetara estrictamente el lenguaje del cliente y el formato de clases conceptuales de la asignatura.

### Trazabilidad de la conversación

- **URL:** https://share.gemini.google/6Pxj8vXCknue
- **Fecha:** 2026-11-05
- **Resumen:** Se utilizó la sesión para traducir a código PlantUML las clases conceptuales, atributos lógicos y relaciones previamente acordadas en el glosario. Se realizaron ajustes en la distribución de las conexiones para optimizar la legibilidad del diagrama.
- **Commits asociados:** [`aa93fa7`](https://github.com/Raultascon/26-27-IdSw1-SDR/commit/aa93fa78f59a17c95670d932ddb26ebf58cecece)

### Validación

- **Mecanismos de validación:** Se contrastó la estructura del diagrama generado en PlantUML contra los apuntes de la asignatura (verificando la ausencia de tipos de datos técnicos de programación o atributos propios de bases de datos) y contra los requerimientos establecidos en la toma de notas.
- **Errores detectados:** Se corrigieron dependencias y asociaciones innecesarias sugeridas en el borrador inicial, conservando únicamente las clases conceptuales, enumerados y relaciones esenciales del dominio.

## Modelo del dominio v3

### Herramientas y fechas

- **Herramienta:** Codex.
- **Fecha:** 2026-11-20.

### Contexto y evaluación crítica

- **¿Se usó?:** Sí.
- **Propósito:** Obtener el código PUML, revisar posibles errores y proponer mejoras a la versión del modelo del dominio; ayudar a redactar los archivos Markdown, revisar la documentación y añadir enlaces y vínculos entre documentos y referencias.
- **Evaluación crítica:** No consta el detalle de propuestas aceptadas o rechazadas en la entrada original.

### Trazabilidad de la conversación

- **URL:** No consta en la entrada original.
- **Resumen:** Asistencia al modelo v3 y a su documentación, con el alcance indicado en el propósito.
- **Commits asociados:** No constan en la entrada original.

### Validación

- **Revisión humana y errores detectados:** No constan en la entrada original.

## Actores y casos de uso v1 y v2

### Herramientas y fechas

- **Herramienta:** Google Gemini, según la conversación registrada.
- **Fecha:** 2026-11-23.
- **Seguimiento:** [Issue #15](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/15).

### Contexto y evaluación crítica

- **¿Se usó?:** Sí
- **Propósito:** Estructurar la documentación funcional (`documentos/casos-uso/documentacion/actores-casos-uso.md`) trazada al Modelo del dominio v3 y a la minuta de la sesión 01, generar el código fuente PlantUML para las iteraciones `v1` (`actoresCasosUso.puml`) y `v2` (`actoresCasosUso-v2.puml`), y redactar la guía de lectura (`documentos/casos-uso/README.md`).
- **Evaluación crítica:**
  - **Aceptado:** Modelado de los 6 actores externos fuera de la frontera del sistema (`Gestor (ordenación académica)`, `Alumno`, `Tiempo`, `Profesor`, `Director de grado` y `Departamento de calidad`), redacción de los casos de uso a nivel de negocio y refactorización en `v2` mediante herencia (`--|>`) desde `Profesor` hacia `Director de grado` y `Departamento de calidad`.
  - **Rechazado:** Propuestas intermedias con relaciones `<<include>>`, verbos de apertura de pantalla (`abrir...()`), división en múltiples diagramas funcionales por versión y enlaces superiores de navegación (`Índice`) innecesarios.

### Trazabilidad de la conversación

- **URL:** `https://share.gemini.google/WByScE1PAU3p`
- **Fecha:** 2026-11-23
- **Resumen:** Definición del catálogo de casos de uso a nivel de negocio para los 6 actores externos, generación de los diagramas PlantUML (`v1` con asociaciones directas y `v2` con herencia de roles de consulta) y redacción de la documentación y guía de lectura tras depurar errores de abstracción y formato señalados durante la revisión.
- **Commits asociados:**
  - [`4acc0cd`](https://github.com/Raultascon/26-27-IdSw1-SDR/commit/4acc0cd) (`feat(cu): añade diagramas v1 y v2 de actores y casos de uso [refs #15]`)
  - [`d6c9a0a`](https://github.com/Raultascon/26-27-IdSw1-SDR/commit/d6c9a0a) (`docs(cu): documenta actores y casos de uso a nivel de negocio [refs #15]`)
  - Commits posteriores de corrección (`fix(cu)`) y guía de lectura (`docs(cu)`) vinculados a `[refs #15]` en la rama `feat/issue-15-encontrar-actores-y-casos-de-uso`

### Validación

La revisión y los errores detectados se conservan en la [validación histórica de casos de uso](#validación-histórica-de-casos-de-uso), tal como estaban documentados en el registro general.

## Refactor de actores y casos de uso v3

### Herramientas y fechas

- **Herramienta:** Claude (Anthropic).
- **Fechas:** 2026-11-23 a 2026-11-24.
- **Seguimiento:** [Issue #22](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/22).

### Contexto y evaluación crítica

- **¿Se usó?:** Sí
- **Propósito:** Apoyo para revisar el PR #19 frente a la minuta de la sesión 01, redactar la propuesta de mejoras publicada en Discussions y aplicar en los archivos los cambios acordados por el equipo en el Issue #22, con un commit por cambio.
- **Evaluación crítica:**
  - **Aceptado tras revisión:** actor abstracto `ConsultorResultados` en lugar de la herencia desde `Profesor`; herencia del `Gestor` desde ese rol (comprobada con la sesión 01); Campus Virtual / Panal como actor secundario; casos de uso de gestión de convocatoria y asignaciones (marcados como pendientes de validar con el cliente); diagramas de contexto y glosario propio enlazado al del modelo del dominio.
  - **Rechazado:** mover los diagramas a una carpeta `modelosUML`, porque el resto del repositorio usa `diagramas/` y cambiarlo solo en casos de uso rompía la coherencia. Se deja como decisión de grupo.
  - **Rechazado:** modelar el Servidor de correo como actor secundario. El correo es solo un canal de notificación y no una entidad externa con interacción propia.
  - **Corregido por el equipo:** la propuesta inicial sustituía el contenido de la v2. Se decidió conservar el texto original de la v2 y documentar el refactor en una sección propia con registro de cambios, para mantener la trazabilidad.

### Trazabilidad de la conversación

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

### Validación

El registro original indica que el equipo decidió qué cambios aceptar, cuáles descartar y cómo documentarlos, y revisó el resultado antes de subirlo. Se conserva el detalle en la [validación histórica de casos de uso](#validación-histórica-de-casos-de-uso).

## Estructuración inicial de la documentación

### Herramientas y fechas

- **Herramienta:** OpenAI Codex.
- **Fecha:** 2026-11-24.
- **Seguimiento:** [Issue #21](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/21).

### Contexto y evaluación crítica

- **¿Se usó?:** Sí.
- **Propósito:** Comparar repositorios de cursos anteriores, reorganizar la navegación, redactar el README y revisar el formato y los enlaces de la documentación.
- **Evaluación crítica:** Se adoptó la navegación por artefactos de [Jorgestor](https://github.com/martinlopez7/25-26-IdSw1-SdR) mediante enlaces Markdown. El estado de los entregables se contrastó con la minuta, `develop` y el seguimiento de los issues. En esa revisión, los artefactos de fases posteriores figuraban como pendientes de elaboración o de integración, según su estado.

### Trazabilidad de la conversación

- **Conversación:** Sesión de Codex del 24/11/2026. Sin URL consignada; el registro quedó vinculado al issue.
- **Mensaje declarado originalmente:** `docs(repo): reorganiza la navegación de la documentación [refs #21]`.
- **Commit localizado en el historial:** [`869cabe`](https://github.com/Raultascon/26-27-IdSw1-SDR/commit/869cabe), con el mensaje `docs(repo): reorganiza la portada y la navegación [refs #21]`.

### Validación

- **Comprobaciones registradas:** Revisión de rutas y anclas internas, tablas y bloques de código. Se corrigió un enlace al modelo v3 y se cerró el bloque de plantilla de las convenciones.
- **Revisión humana:** Pendiente según la entrada original.

## Rediseño de README y unificación del registro

### Herramientas y fechas

- **Herramienta:** OpenAI Codex.
- **Fecha:** 2026-11-24.
- **Seguimiento:** [Issue #21](https://github.com/Raultascon/26-27-IdSw1-SDR/issues/21), rama `feat/issue-21-estructuracion-visual`.

### Contexto y evaluación crítica

- **¿Se usó?:** Sí.
- **Propósito:** Rediseñar los cuatro README con recursos SVG locales y navegación mediante iconos, contrastar su contenido con la minuta y el refactor ya integrado y reunir los registros de IA.
- **Criterios aplicados a la propuesta:** Paleta inspirada en las capturas de Panal aportadas por el usuario y organización visual de Jorgestor; marca gráfica propia para el proyecto académico. Se conserva la documentación de requisitos y sus diagramas. La ruta antigua del registro de IA mantiene un enlace al central para conservar las referencias.
- **Corrección detectada:** La portada anterior indicaba que los diagramas de contexto estaban pendientes de integración; el merge de `develop` ya los incorporaba. Se actualizó ese estado.
- **Límite de la consolidación:** Se conservan las declaraciones históricas, sin atribuir herramientas, conversaciones o revisiones humanas no documentadas.

### Trazabilidad de la conversación

- **Conversación:** Sesión actual de Codex del 24/11/2026; no se ha consignado una URL compartida.
- **Referencias consultadas:** README y documentos de los repositorios del profesor de 2026–2027, temario general y sesiones de 2025–2026 y 2024–2025; README del modelo y registro de IA de Jorgestor.
- **Commits asociados:** Identificados por los mensajes `style(readme): unifica la identidad visual con Panal [refs #21]` y `docs(ia-uso): centraliza los registros de asistencia [refs #21]` en la rama del issue.

### Validación

- **Comprobaciones técnicas:** Revisión de enlaces relativos y anclas, validez de los SVG y visualización de los README. Comparación del alcance de archivos con el estado inicial.
- **Revisión humana:** Pendiente de la revisión manual solicitada por el usuario. No se ha abierto un pull request.

## Validación histórica de casos de uso

Este bloque conserva la declaración de validación de los issues #15 y #22 del registro original.

- **Mecanismos de validación:** Revisión crítica de cada propuesta generada por la IA contrastándola con los criterios explicados por el profesor en clase, la [minuta de la sesión 01](sesiones/sesion01.md) y el [modelo del dominio v3](modelos/documentacion/dominio-v3.md), además de comprobar visualmente el renderizado de diagramas `.svg` y enlaces en GitHub.
- **Errores detectados:**
  - **Abuso de `<<include>>` y mezcla de niveles de abstracción:** Al mostrarle un repositorio antiguo de ejemplo (`pySigHor`), la IA copió literalmente ese patrón introduciendo flechas `<<include>>` y casos de uso de navegación de interfaz (`abrirCuestionario()`, `abrirConvocatorias()`, `abrirAsignaciones()`). Se rechazó porque en clase se indicó evitar el uso excesivo de `<<include>>`/`<<extend>>` y mantener esta primera iteración estrictamente a nivel de negocio sin detalles técnicos ni de pantalla.
  - **Cruce innecesario de flechas en `v1`:** La propuesta inicial de la IA conectaba por separado a `Profesor`, `Director de grado` y `Departamento de calidad` con los casos de uso de consulta y exportación, generando 6 líneas cruzadas difíciles de leer. Se le indicó aplicar herencia (`--|>`) en una segunda iteración (`v2`) siguiendo las buenas prácticas vistas en clase.
  - **División errónea de diagramas y enlaces rotos:** La IA sugirió dividir una misma iteración en dos diagramas distintos (`001` y `002`) en lugar de mantener un único diagrama por iteración, e incluyó enlaces superiores al índice que no cargaban o sobraban en los archivos Markdown, por lo que se le ordenó eliminarlos.
  - **Actores sin respaldo en la minuta (Issue #22):** Al contrastar el catálogo con la sesión 01 se detectó que `Director de grado` y `Departamento de calidad` no aparecen en ella; la minuta solo menciona al administrador y a los profesores como receptores de resultados. Se mantienen en `v3`, pero se propone confirmarlos con el cliente mediante un Issue `[Duda]`.
