## Declaración de Uso de IA

## Herramientas Utilizadas
- **Herramientas:** Google Gemini
- **Fechas:** 2026-11-23

## Contexto de Uso por Artefacto

### Actores y Casos de Uso · v1 y v2 (Issue #15)
- **¿Se usó?:** Sí
- **Propósito:** Estructurar la documentación funcional (`documentos/casos-uso/documentacion/actores-casos-uso.md`) trazada al Modelo del dominio v3 y a la minuta de la sesión 01, generar el código fuente PlantUML para las iteraciones `v1` (`actoresCasosUso.puml`) y `v2` (`actoresCasosUso-v2.puml`), y redactar la guía de lectura (`documentos/casos-uso/README.md`).
- **Evaluación crítica:**
  - **Aceptado:** Modelado de los 6 actores externos fuera de la frontera del sistema (`Gestor (ordenación académica)`, `Alumno`, `Tiempo`, `Profesor`, `Director de grado` y `Departamento de calidad`), redacción de los casos de uso a nivel de negocio y refactorización en `v2` mediante herencia (`--|>`) desde `Profesor` hacia `Director de grado` y `Departamento de calidad`.
  - **Rechazado:** Propuestas intermedias con relaciones `<<include>>`, verbos de apertura de pantalla (`abrir...()`), división en múltiples diagramas funcionales por versión y enlaces superiores de navegación (`Índice`) innecesarios.

## Trazabilidad de Conversaciones

### Conversación 1: Identificación de actores y casos de uso (Issue #15)
- **URL:** `https://share.gemini.google/WByScE1PAU3p`
- **Fecha:** 2026-11-23
- **Resumen:** Definición del catálogo de casos de uso a nivel de negocio para los 6 actores externos, generación de los diagramas PlantUML (`v1` con asociaciones directas y `v2` con herencia de roles de consulta) y redacción de la documentación y guía de lectura tras depurar errores de abstracción y formato señalados durante la revisión.
- **Commits asociados:**
  - [`4acc0cd`](https://github.com/Raultascon/26-27-IdSw1-SDR/commit/4acc0cd) (`feat(cu): añade diagramas v1 y v2 de actores y casos de uso [refs #15]`)
  - [`d6c9a0a`](https://github.com/Raultascon/26-27-IdSw1-SDR/commit/d6c9a0a) (`docs(cu): documenta actores y casos de uso a nivel de negocio [refs #15]`)
  - Commits posteriores de corrección (`fix(cu)`) y guía de lectura (`docs(cu)`) vinculados a `[refs #15]` en la rama `feat/issue-15-encontrar-actores-y-casos-de-uso`

## Validación Humana

- **Mecanismos de validación:** Revisión crítica de cada propuesta generada por la IA contrastándola con los criterios explicados por el profesor en clase, la minuta de la sesión 01 (`sesion01.md`) y el Modelo del dominio v3 (`modelo-v3.md`), además de comprobar visualmente el renderizado de diagramas `.svg` y enlaces en GitHub.
- **Errores detectados:**
  - **Abuso de `<<include>>` y mezcla de niveles de abstracción:** Al mostrarle un repositorio antiguo de ejemplo (`pySigHor`), la IA copió literalmente ese patrón introduciendo flechas `<<include>>` y casos de uso de navegación de interfaz (`abrirCuestionario()`, `abrirConvocatorias()`, `abrirAsignaciones()`). Se rechazó porque en clase se indicó evitar el uso excesivo de `<<include>>`/`<<extend>>` y mantener esta primera iteración estrictamente a nivel de negocio sin detalles técnicos ni de pantalla.
  - **Cruce innecesario de flechas en `v1`:** La propuesta inicial de la IA conectaba por separado a `Profesor`, `Director de grado` y `Departamento de calidad` con los casos de uso de consulta y exportación, generando 6 líneas cruzadas difíciles de leer. Se le indicó aplicar herencia (`--|>`) en una segunda iteración (`v2`) siguiendo las buenas prácticas vistas en clase.
  - **División errónea de diagramas y enlaces rotos:** La IA sugirió dividir una misma iteración en dos diagramas distintos (`001` y `002`) en lugar de mantener un único diagrama por iteración, e incluyó enlaces superiores al índice que no cargaban o sobraban en los archivos Markdown, por lo que se le ordenó eliminarlos.
