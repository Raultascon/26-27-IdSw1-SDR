# Declaración de Uso de IA

## Herramientas Utilizadas
- **Herramientas:** Google Gemini
- **Fechas:** Noviembre 2026

## Contexto de Uso por Artefacto

### Modelo del Dominio (v1)
- **¿Se usó?:** Sí
- **Propósito:** Asistencia técnica en la sintaxis de PlantUML para representar el diagrama de clases del modelo del dominio a partir de las entidades, atributos y relaciones conceptuales identificadas.
- **Evaluación crítica:** La IA propuso una estructuración básica en PlantUML. Se revisó y adaptó manualmente la jerarquía de herencia, las asociaciones y la nomenclatura para asegurar que se respetara estrictamente el lenguaje del cliente y el formato de clases conceptuales de la asignatura.

## Trazabilidad de Conversaciones

### Conversación 1: Transcripción a sintaxis PlantUML del Modelo del Dominio
- **URL:** https://share.gemini.google/6Pxj8vXCknue
- **Fecha:** 2026-11-05
- **Resumen:** Se utilizó la sesión para traducir a código PlantUML las clases conceptuales, atributos lógicos y relaciones previamente acordadas en el glosario. Se realizaron ajustes en la distribución de las conexiones para optimizar la legibilidad del diagrama.
- **Commits asociados:** [`aa93fa7`](https://github.com/Raultascon/26-27-IdSw1-SDR/commit/aa93fa78f59a17c95670d932ddb26ebf58cecece)

## Validación Humana

- **Mecanismos de validación:** Se contrastó la estructura del diagrama generado en PlantUML contra los apuntes de la asignatura (verificando la ausencia de tipos de datos técnicos de programación o atributos propios de bases de datos) y contra los requerimientos establecidos en la toma de notas.
- **Errores detectados:** Se corrigieron dependencias y asociaciones innecesarias sugeridas en el borrador inicial, conservando únicamente las clases conceptuales, enumerados y relaciones esenciales del dominio.