# Usar un repositorio Git como espacio de trabajo compartido

- **Fecha:** 2026-09-29
- **Decidido por:** Alberto
- **Estado:** Vigente

## Contexto

El proyecto arranca con dos personas y sin nada construido todavía: estamos en fase
de explorar qué hacer. Hacía falta un sitio común donde vivieran las ideas, las
referencias y las decisiones, con dos requisitos:

1. Que ambos pudiéramos trabajar en asíncrono sin pisarnos.
2. Que **Claude Code pudiera leer ese contexto** al trabajar cualquiera de los dos,
   para no tener que reexplicarle el proyecto en cada sesión.

## Opciones consideradas

1. **Notion / Google Docs**
   - A favor: fácil, edición simultánea, cero fricción para empezar.
   - En contra: Claude Code no lo lee desde el repo; el contexto quedaría separado
     del código futuro; sin historial de por qué cambió algo.

2. **Repositorio Git con documentos en Markdown**
   - A favor: Claude lo lee directamente; historial completo de cambios; el contexto
     y el código acaban en el mismo sitio; funciona en asíncrono.
   - En contra: curva de aprendizaje de Git; riesgo de conflictos de merge; editar
     Markdown es menos cómodo que un editor visual.

3. **Las dos cosas a la vez**
   - Descartada: dos fuentes de verdad acaban contradiciéndose, y nadie sabe cuál manda.

## Decisión

Repositorio Git, alojado en GitHub, con todo el contexto en Markdown.

Estructura: `context/` para referencia estable, `decisiones/` para lo cerrado,
`notas/` para apuntes en crudo. `CLAUDE.md` en la raíz como contexto que Claude lee
automáticamente.

**Flujo:** ambos comiteamos **directamente sobre `main`**, sin ramas ni Pull Requests.

## Razonamiento

Que Claude pueda leer el contexto es el motivo principal, y es lo que inclina la
balanza: convierte el repo en memoria compartida entre las dos sesiones de Claude,
no solo entre las dos personas.

Se eligen commits directos a `main` en vez de Pull Requests porque en esta fase el
contenido es casi todo documentación, donde los conflictos reales son raros si cada
uno escribe en sus propios archivos. Los PR añadirían una ceremonia que no compensa
todavía.

## Consecuencias

- Hace falta disciplina de Git: `git pull` antes de empezar y `git push` justo
  después de cada commit. Sin eso, el flujo directo a `main` genera conflictos.
- Cada uno escribe en archivos propios (fechados y con su tema) para minimizar choques.
- Los archivos compartidos (`CLAUDE.md`, los `README.md`) se avisan antes de editar.
- Secretos y credenciales **nunca** entran al repo. Cubierto por `.gitignore`.
- **A revisar cuando empiece a haber código**: con dos personas tocando código sobre
  `main` sin PR, los conflictos dejan de ser raros. En ese momento hay que decidir de
  nuevo si pasamos a ramas + Pull Request, y registrarlo como decisión nueva que
  supersede a esta.
