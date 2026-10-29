# Convenciones de Trabajo en GitHub


Para asegurar un flujo de trabajo eficiente, una trazabilidad clara, todo el equipo debe adherirse a las siguientes convenciones para nombrar y gestionar elementos en GitHub.


---


## 1. Etiquetas (Labels)


Las etiquetas permiten categorizar y filtrar rápidamente las incidencias (Issues). Se emplearán las siguientes etiquetas estandarizadas:


| Etiqueta | Descripción |
| :--- | :--- |
| `bug` | Error o inconsistencia en un artefacto existente que debe ser corregido. |
| `casoDeUso` | Tareas relacionadas con Casos de Uso (diagramas, fichas, prototipos, etc.). |
| `documentation` | Tareas de documentación general: minutas, README, o el archivo `AI-uso.md`. |
| `duda` | Preguntas dirigidas explícitamente al cliente para aclarar requisitos. |
| `modeloDominio` | Tareas vinculadas al Modelo del Dominio (diagrama de clases, glosario, etc.). |
| `tarea-interna` | Tareas organizativas o técnicas del equipo que no requieren interacción con el cliente. |
| `validación-cliente` | Solicitudes formales al cliente para la revisión y aprobación de entregables. |


---


## 2. Incidencias (Issues)


Los Issues son el motor de nuestra trazabilidad. Toda tarea, duda o error debe estar registrada en un Issue antes de escribir código o documentación.


### 2.1. Título del Issue


Se utilizará un prefijo entre corchetes para identificar rápidamente el propósito:


* **Para el Cliente (Duda):**
  * Sintaxis: `[Duda] <Pregunta clara y concisa>`
  * Ejemplo: `[Duda] ¿Puede un usuario tener múltiples perfiles de pago vinculados?`
  * Etiquetas: `duda`


* **Para el Cliente (Validación):**
  * Sintaxis: `[Validación] <Artefacto y versión a validar>`
  * Ejemplo: `[Validación] v1 del Modelo del Dominio y Glosario`
  * Etiquetas: `validación-cliente`, `modeloDominio`


* **Para el Equipo (Tarea Interna):**
  * Sintaxis: `[Tarea] <Acción específica a realizar>`
  * Ejemplo: `[Tarea] Redactar v1 de la ficha del CU-03: Generar Informe`
  * Etiquetas: `tarea-interna`, `casoDeUso`


* **Para Corregir un Error:**
  * Sintaxis: `[Bug] <Descripción del error>`
  * Ejemplo: `[Bug] El CU-01 no contempla el caso de usuario ya existente`
  * Etiquetas: `bug`, `casoDeUso`


### 2.2. Cuerpo del Issue


* **Issues dirigidos al cliente:**
  * Mencionar explícitamente usando su `@usuario-github-del-cliente`.
  * Contextualizar la consulta vinculando la minuta de la reunión correspondiente.
  * Ejemplo:
    > Hola @usuario-del-cliente, en relación con la reunión del 20/03 (ver `/documentos/sesiones/sesion01.md`), nos surge la duda de si un usuario podría tener más de un perfil de pago. ¡Gracias!


* **Issues de tareas internas:**
  * Asignar un único miembro del equipo en `Assignees` como responsable principal.
  * Describir los entregables esperados (rutas de archivos, diagramas, etc.).


---


## 3. Ramas (Branches)


Todo trabajo se desarrollará en ramas independientes partiendo de `main`. **Queda estrictamente prohibido hacer commits directos sobre la rama `main`.**
Ademas vamos a tener una rama `develop` en la que previamente comprobaremos que todos los añadidos funcionan correctamente y posterior a eso se hace un  merge la develop en la main.


### Formato del Nombre de la Rama:


`tipo/issue-<NÚMERO_ISSUE>-<descripcion-corta-en-kebab-case>`


* **Tipos permitidos (`tipo`):**
  * `feat`: Nueva funcionalidad o artefacto inicial (ej. v1 de un CU).
  * `fix`: Corrección de un error o inconsistencia (`bug`).
  * `docs`: Inclusión o modificación de documentación (minutas, `AI-uso.md`).
  * `refactor`: Reestructuración sin alterar semántica (ej. reorganizar carpetas).
  * `chore`: Mantenimiento del repositorio (configuraciones, ignorados).
* **`<NÚMERO_ISSUE>`**: Número del Issue de GitHub que esta rama resuelve.
* **`<descripcion-corta>`**: Resumen breve en minúsculas y separado por guiones.


**Ejemplos:**
* `feat/issue-10-modelo-dominio-v1`
* `fix/issue-15-cu01-usuario-existente`


---


## 4. Commits


Los mensajes de commit deben cumplir el estándar **Conventional Commits** y garantizar la trazabilidad bidireccional hacia los Issues.


### Formato del Mensaje:


`tipo(alcance): <mensaje breve en imperativo> [refs #NÚMERO_ISSUE]`


* **`tipo`**: Igual que los tipos de rama (`feat`, `fix`, `docs`, `style`, `refactor`, `chore`).
* **`(alcance)`**: Ámbito afectado, opcional pero recomendado (`mdd`, `cu`, `cu-01`, `glosario`, `minuta`, `repo`, `ia-uso`).
* **`<mensaje>`**: Acción realizada escrita en modo imperativo (ej. "añade", "corrige").
* **`[refs #NÚMERO_ISSUE]`**: Enlace explícito al Issue de GitHub.


⚠️ **REGLA CRÍTICA DE TRAZABILIDAD:** En los commits intermedios de una rama, usaremos SIEMPRE la palabra `refs` (ej. `[refs #12]`). **Nunca uses palabras clave como `closes` o `fixes` en los commits individuales**, ya que esto cerraría el Issue prematuramente antes de que la rama sea revisada en un Pull Request.


**Ejemplos:**
* `feat(mdd): añade clases Usuario y Reserva iniciales [refs #10]`
* `docs(ia-uso): registra prompt de revisión de CU-02 [refs #22]`


---


## 5. Pull Requests (PRs)


Los Pull Requests son la herramienta obligatoria para integrar código en `main` y en `develop` y asegurar la revisión por pares (Peer Review).


### 5.1. Título del PR:
`[TIPO_PRINCIPAL] <Mismo título del Issue principal que resuelve>`
* Ejemplo: `[Feat] [Tarea] Redactar v1 de la ficha del CU-03: Generar Informe`


### 5.2. Reglas Obligatorias para Integración (Merge):


1. **Cierre Automático:** El cuerpo del PR debe incluir obligatoriamente la frase `Closes #NÚMERO_ISSUE` (o `Fixes #NÚMERO_ISSUE`). Esto permite que GitHub cierre el Issue de forma automática, vinculándolo permanentemente al PR.
2. **Revisión por Pares (Reviewers):** Se debe asignar al resto de miembros del equipo como "Reviewers". Es **obligatoria al menos 1 aprobación explícita** de otro miembro del equipo antes de realizar el *Merge*.
3. **Sincronización de IA:** Si se ha utilizado Inteligencia Artificial para el trabajo de esa rama, el mismo PR debe incluir las actualizaciones correspondientes en el archivo `AI-uso.md`.
4. **Validación del Cliente:** Si el PR contiene un entregable finalizado, se puede mencionar al `@usuario-github-del-cliente` para notificarle o solicitar su validación simbólica.


---


## 6. Registro de Uso de IA (`AI-uso.md`)


Todo uso de IA generativa debe auditarse para evaluar el pensamiento crítico del equipo. El archivo `AI-uso.md` debe mantenerse actualizado mediante la siguiente estructura incremental:


```markdown
## Declaración de Uso de IA


## Herramientas Utilizadas
- **Herramientas:** [ej. ChatGPT 4, Gemini Advanced]
- **Fechas:** [Rango de fechas]


## Contexto de Uso por Artefacto


### [Nombre del Artefacto, ej. Modelo del Dominio]
- **¿Se usó?:** [Sí/No]
- **Propósito:** [Para qué se empleó la IA]
- **Evaluación crítica:** [Qué sugirió la IA, qué se aceptó y qué se rechazó justificadamente]


## Trazabilidad de Conversaciones


### Conversación N: [Título descriptivo]
- **URL:** `https://...`
- **Fecha:** AAAA-MM-DD
- **Resumen:** [Breve descripción de lo obtenido y si se modificó o descartó]
- **Commits asociados:** [Enlaces a los commits afectados]


## Validación Humana


- **Mecanismos de validación:** [Cómo se contrastó la salida de la IA con los apuntes, minutas o cliente]
- **Errores detectados:** [Ejemplos concretos de alucinaciones o errores conceptuales corregidos por el equipo]
