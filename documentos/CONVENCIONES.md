# Convenciones de trabajo en GitHub

[Inicio](../README.md) · [Sesiones con el cliente](sesiones/README.md) · [Registro de IA](AI-uso.md)

**En esta página**

- [Etiquetas](#1-etiquetas-labels)
- [Incidencias](#2-incidencias-issues)
- [Ramas](#3-ramas-branches)
- [Commits](#4-commits)
- [Pull requests](#5-pull-requests-prs)
- [Registro de uso de IA](#6-registro-de-uso-de-ia-ai-usomd)

## 1. Etiquetas (Labels)

| Etiqueta             | Descripción                                                         |
| :------------------- | :------------------------------------------------------------------ |
| `bug`                | Error o inconsistencia en un artefacto existente.                   |
| `casoDeUso`          | Actores, casos de uso, diagramas, fichas o prototipos.              |
| `documentation`      | Minutas, guías de lectura o registro de IA.                         |
| `duda`               | Pregunta al cliente para aclarar requisitos.                        |
| `modeloDominio`      | Modelo del dominio, diagramas o glosario.                           |
| `tarea-interna`      | Trabajo del equipo que no requiere interacción con el cliente.      |
| `validación-cliente` | Solicitud de revisión o aprobación de un entregable por el cliente. |

## 2. Incidencias (Issues)

Cada tarea, duda o error se registra en un issue antes de trabajar. Cuando una propuesta nace en Discussions, el issue enlaza la conversación que explica la decisión.

### 2.1. Título del issue

| Prefijo        | Formato                                                                  | Etiquetas habituales                  |
| :------------- | :----------------------------------------------------------------------- | :------------------------------------ |
| `[Duda]`       | Pregunta concreta, como «¿Quién consulta los resultados tras el cierre?» | `duda`                                |
| `[Validación]` | Artefacto y versión, como «Modelo del dominio v3»                        | `validación-cliente`, `modeloDominio` |
| `[Tarea]`      | Acción y alcance, como «Refinar la minuta de la sesión 01»               | `tarea-interna`, `documentation`      |
| `[Bug]`        | Inconsistencia observada, como «Enlace roto a la minuta»                 | `bug`, `documentation`                |

### 2.2. Cuerpo del issue

- En una consulta o validación, mencionar al cliente y enlazar el apartado de la minuta que da contexto. [Minuta de la sesión 01](sesiones/sesion01.md)
- En una tarea interna, identificar al responsable principal en `Assignees` y describir los entregables esperados, con sus rutas cuando existan.

## 3. Ramas (Branches)

Cada issue tiene una rama de trabajo creada desde `develop`. Los cambios se revisan e integran primero en `develop` y se incorporan a `main` mediante un pull request. Los commits de trabajo se realizan en la rama del issue.

```text
tipo/issue-<número>-<descripción-en-kebab-case>
```

| Tipo       | Uso                                                         |
| :--------- | :---------------------------------------------------------- |
| `feat`     | Nueva funcionalidad o primera versión de un artefacto.      |
| `fix`      | Corrección de un error o inconsistencia.                    |
| `docs`     | Inclusión o modificación de documentación.                  |
| `refactor` | Reestructuración que conserva el significado del artefacto. |
| `chore`    | Mantenimiento del repositorio.                              |

El número identifica el issue y la descripción se escribe en minúsculas, con palabras separadas por guiones. Ejemplos del repositorio: `docs/issue-10-refinar-minuta-de-la-sesion-1` y `feat/issue-15-encontrar-actores-y-casos-de-uso`.

## 4. Commits

```text
tipo(alcance): <mensaje breve en imperativo> [refs #NÚMERO_ISSUE]
```

- Usar los tipos de rama indicados arriba o `style` para cambios de formato.
- Añadir un alcance cuando ayude a identificar el cambio, por ejemplo `mdd`, `cu`, `cu-01`, `glosario`, `minuta`, `repo` o `ia-uso`.
- Escribir una acción breve, como `añade` o `corrige`, y usar `[refs #N]` para vincular cada commit a su issue. Las palabras de cierre se reservan para el pull request.

```text
docs(cu): añade guia de lectura de casos de uso [refs #15]
docs(ia-uso): registra uso de IA en actores y casos de uso [refs #15]
```

## 5. Pull requests (PRs)

### 5.1. Título del PR

```text
[TIPO_PRINCIPAL] <Título del issue principal>
```

Ejemplo de título: `[Docs] [Tarea] Refinar la minuta de la sesión 01`.

### 5.2. Reglas de integración

1. **Trazabilidad.** Referenciar el issue en la descripción con `Closes #N` o `Fixes #N`. GitHub aplica el cierre automático cuando el pull request se integra en la rama predeterminada (`main`). En un PR hacia `develop`, la referencia documenta qué issue aborda. [Documentación de GitHub](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue)
2. **Revisión por pares.** Solicitar revisión al resto del equipo y obtener al menos una aprobación explícita de otro integrante antes de integrar.
3. **Registro de IA.** Si se utilizó IA, incluir la actualización del [registro](AI-uso.md) en el mismo pull request.
4. **Validación del cliente.** Si el PR contiene un entregable finalizado, se puede mencionar al cliente para avisarle o solicitar su validación.

## 6. Registro de uso de IA (`AI-uso.md`)

Añadir al [registro de IA](AI-uso.md) las herramientas y fechas, el propósito por artefacto, la evaluación de las sugerencias, la conversación y los commits asociados. Dejar constancia de cómo se validó el resultado y de cualquier error detectado.

```markdown
## Herramientas Utilizadas

- **Herramientas:** nombre y fechas de uso

## Contexto de Uso por Artefacto

### Artefacto (issue #N)

- **¿Se usó?:** Sí/No
- **Propósito:** tarea para la que se utilizó IA
- **Evaluación crítica:** propuestas aceptadas o descartadas y motivo

## Trazabilidad de Conversaciones

### Conversación N: título (issue #N)

- **URL:** enlace, si está disponible para el equipo
- **Fecha:** AAAA-MM-DD
- **Resumen:** resultado y ajustes aplicados
- **Commits asociados:** referencias a los cambios

## Validación Humana

- **Mecanismos de validación:** revisión realizada y fuentes consultadas
- **Errores detectados:** correcciones aplicadas y motivos
```
