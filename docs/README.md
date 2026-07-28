# Registros de Decisiones de Arquitectura (ADR)

Esta carpeta guarda las decisiones importantes de Reparify: las que son
costosas de revertir o cuyo "por qué" se olvida con el tiempo.

Cada ADR es un archivo Markdown numerado (`0001-...`, `0002-...`). No se borran
ni se reescriben: si una decisión se reemplaza, se crea un ADR nuevo que la
marca como *reemplazada* y se actualiza el estado del anterior.

## Cómo crear uno

1. Copia `template.md`.
2. Renómbralo con el siguiente número libre y un título corto en minúsculas
   con guiones (ej. `0002-estrategia-de-multi-tenancy.md`).
3. Escríbelo, ábrelo en un Pull Request y mergéalo.

## Índice

| #    | Título                                      | Estado    |
|------|---------------------------------------------|-----------|
| 0001 | Usar ADRs y un flujo basado en GitHub       | Aceptada  |
