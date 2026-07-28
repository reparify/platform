# Guía de contribución

Convenciones de trabajo de Reparify. Hoy el desarrollo es de una persona; estas
reglas mantienen el historial limpio y dejan la mecánica lista para cuando
entren colaboradores.

## Frontera de idiomas

Lo que mira hacia el código o la máquina, en inglés; lo que es para leer, en
español.

- **Inglés:** identificadores y comentarios del código, nombres de ramas,
  mensajes de commit completos y el título del PR (se vuelve el commit de `main`).
- **Español:** los ADR y sus nombres de archivo, archivos Markdown y el cuerpo de
  issues y pull requests.

Los *slugs* (ramas y archivos) son ASCII: minúsculas, guiones, sin tildes ni ñ.

## Ramas

Formato: `<type>/<issue-number>-<short-slug>`. De vida corta.

```
feat/142-device-intake
fix/158-tax-calculation
docs/160-adr-multi-tenancy
```

## Commits

Conventional Commits, en inglés, en imperativo: `type(opcional-scope): description`.

Tipos: `feat`, `fix`, `docs`, `chore`, `refactor`, `test`, `perf`, `build`, `ci`.

```
feat: add device intake with inbound checklist
fix(billing): correct tax rounding on invoice total
docs: add ADR-0002 on multi-tenancy strategy
```

## Pull Requests (GitHub Flow adaptado)

- **`main` protegido:** todo entra por PR con los checks en verde. Sin
  aprobaciones (no puedo aprobar mi propio PR).
- **El CI es el gate:** lint, tests y build. Es lo que reemplaza al revisor humano.
- **Revisión con IA, consultiva:** cada PR pasa por **`codex`** o
  **`claude-code-action`**. Comenta, no bloquea.
- **Squash merge:** un commit limpio en `main`, con el mensaje del título del PR.
- **Borrar la rama** tras el merge.

## Flujo típico

1. Tomar un issue.
2. Rama: `feat/142-device-intake`.
3. Commits pequeños (Conventional Commits, inglés).
4. PR: título en inglés estilo commit, descripción en español.
5. CI en verde + leer la revisión de IA.
6. Squash merge y borrar la rama.
