# ADR-0001: Usar ADRs y un flujo de trabajo basado en GitHub

- **Estado:** Aceptada
- **Fecha:** 2026-07-27

## Contexto

Reparify lo desarrolla una sola persona por ahora, pero quiero trabajar con
prácticas modernas desde el inicio y no atarme a un flujo que estorbe cuando
entren colaboradores o clientes.

Dos problemas concretos que quiero evitar:

1. **Herramientas dispersas.** Si el código está en un sitio, las tareas en
   otro y las notas de diseño en un tercero (por ejemplo Notion), pierdo tiempo
   saltando entre ellos y la información se desincroniza.
2. **Decisiones sin memoria.** Algunas decisiones de Reparify son caras de
   revertir (por ejemplo, cómo aislar los datos de cada negocio en el modelo
   multi-tenant). En unos meses no voy a recordar por qué elegí una opción y no
   otra y corro el riesgo de deshacerla sin entender qué la motivó.

## Decisión

- Todo el desarrollo vive en **GitHub**, bajo una **organización**: Issues para el
  backlog, Projects para el tablero, Pull Requests para integrar cambios, Actions para
  CI/CD y Discussions como diario de diseño y, más adelante, soporte.
- **No** se usan herramientas externas de notas o gestión (Notion y similares)
  salvo que una necesidad futura lo justifique en su propio ADR.
- La documentación técnica se trata **como código** (*docs-as-code*): vive en la
  carpeta `/docs` del repo, en Markdown, y se revisa en el mismo Pull Request
  que el cambio que la motiva.
- Las decisiones importantes se registran como **ADRs** en `/docs/adr`, con el
  formato de la plantilla de esta carpeta.
- El **Wiki de GitHub no se usa** para documentación técnica. Queda disponible
  solo para contenido de referencia estable o de cara a usuarios finales más
  adelante.

## Alternativas consideradas

- **Notion (u otra herramienta de notas) para documentación y tareas.** Se
  descarta porque queda desconectada del repositorio: la documentación no se
  versiona junto al código ni pasa por los Pull Requests, así que tiende a
  quedar desactualizada.
- **Wiki de GitHub para la documentación técnica.** Se descarta como opción
  principal porque el Wiki es un repositorio git aparte: no pasa por los Pull
  Requests ni se versiona con el código, y nada obliga a actualizarlo cuando la
  implementación cambia. Por eso se desincroniza con facilidad.

## Consecuencias

**A favor:**

- Una sola fuente de verdad: código, tareas, decisiones y CI en el mismo lugar.
- La documentación no puede divergir del código, porque se cambia en el mismo PR.
- El "por qué" de las decisiones caras queda registrado y consultable.
- Empezar bajo una organización evita una migración incómoda al sumar gente.

**En contra (aceptado a sabiendas):**

- Escribir ADRs y abrir PRs añade algo de fricción trabajando en solitario. Lo
  acepto como precio de tener historial y de estrenar bien el flujo.
- Existe el riesgo de caer en *ceremonia* (más estructura que producto). Se
  mitiga manteniendo los ADRs cortos (media página) y solo para decisiones que
  de verdad lo merezcan.
- Quedar centralizado en GitHub implica cierta dependencia de la plataforma.
