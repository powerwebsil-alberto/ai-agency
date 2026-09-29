# CLAUDE.md — Contexto del proyecto

> Este archivo lo lee Claude Code automáticamente al abrir la carpeta. Es la fuente
> de verdad sobre qué es el proyecto y cómo se trabaja aquí. Si algo cambia, se
> actualiza este archivo **en el mismo commit** que el cambio.

---

## 1. Qué es este proyecto

**Nombre de trabajo:** Ai agency
**Estado actual:** 🟡 Fase de exploración — todavía no hay producto ni alcance definido.

Ahora mismo este repositorio es un **espacio de trabajo compartido para pensar**:
se usa para recoger ideas, referencias, decisiones y notas mientras se define qué
se va a construir.

**Objetivo de esta fase:** llegar a una decisión clara sobre qué vamos a hacer,
documentada en `decisiones/`.

<!-- RELLENAR cuando esté decidido -->
**Qué construimos:** `[PENDIENTE — sustituir por una frase de 1–2 líneas]`
**Para quién:** `[PENDIENTE — cliente o usuario objetivo]`
**Cómo se gana dinero con ello:** `[PENDIENTE]`
**Qué NO es este proyecto:** `[PENDIENTE — límites explícitos, ayuda a no dispersarse]`

### Instrucción para Claude en esta fase
Todavía no hay decisiones cerradas. Antes de proponer arquitectura, stack o
estructura de código, **consulta `decisiones/` y `notas/`**. Si una decisión
relevante no está escrita ahí, no la asumas: pregunta.

---

## 2. Quién trabaja aquí

| Persona | Rol | Se enfoca en | Contacto |
|---|---|---|---|
| Alberto | `[PENDIENTE — definir rol]` | `[PENDIENTE]` | albertomercado1702@gmail.com |
| `[NOMBRE COLABORADOR]` | `[PENDIENTE — definir rol]` | `[PENDIENTE]` | `[PENDIENTE]` |

**Reparto de trabajo:** `[PENDIENTE — sin definir todavía]`

Mientras no haya reparto definido, **cada quien avisa al otro antes de empezar algo
grande**, para no duplicar trabajo ni pisarse los mismos archivos.

---

## 3. Stack técnico y convenciones

**Stack:** `[PENDIENTE — mixto / sin decidir]`

No hay código todavía. La decisión de stack se tomará más adelante y quedará
registrada en `decisiones/` antes de escribir nada.

### Convenciones que ya aplican (a documentos)
- **Idioma:** todo en español — documentos, commits, nombres de archivo.
- **Nombres de archivo:** minúsculas, sin acentos ni espacios, separados por guiones.
  Ejemplo: `investigacion-competencia.md`, no `Investigación Competencia.md`.
- **Formato:** Markdown (`.md`) para todo lo que sea texto.
- **Fechas:** siempre formato `AAAA-MM-DD` (ej. `2026-09-29`). Nunca "ayer" o "la semana pasada".

### Convenciones de código
`[PENDIENTE — definir al elegir stack: formateador, linter, estructura de carpetas,
convención de nombres, gestión de dependencias]`

---

## 4. Reglas de trabajo

### Ramas
Trabajamos **directamente sobre `main`**. No usamos ramas por defecto mientras el
proyecto sea principalmente documentación.

Si en algún momento alguien empieza un cambio grande o que va a durar varios días,
**sí se abre rama**, con este nombre:

```
tipo/descripcion-corta
```

Tipos: `feat/`, `fix/`, `docs/`, `exp/` (experimento).
Ejemplo: `exp/prototipo-agente-soporte`

### Commits
- **Commit pequeño y frecuente.** Mejor cinco commits de una cosa cada uno que uno de cinco cosas.
- **Commit al terminar cada unidad de trabajo**, no al final del día.
- **Push inmediatamente después de cada commit.** Esta es la regla más importante:
  trabajando los dos sobre `main`, el trabajo que no está subido es trabajo que va
  a provocar un conflicto.
- **Pull antes de empezar**, siempre. Ver `ONBOARDING.md`.
- Mensaje en español, imperativo, una línea: `Añade notas de la reunión con [cliente]`

### Qué NO se toca
- ❌ **Nunca** se comitean claves, tokens, `.env`, credenciales ni datos de clientes.
  Ver `.gitignore`. Si crees que has subido una clave, **avisa inmediatamente y
  rota la clave** — borrarla en un commit posterior no la elimina del historial.
- ❌ No se reescribe el historial de `main` (`git push --force`, `git rebase` sobre
  commits ya subidos, `git reset --hard` de commits compartidos).
- ❌ No se borra ni reescribe un archivo de `decisiones/` ajeno. Una decisión que ya
  no vale se **supersede** con una nueva, no se borra.
- ❌ No se edita `CLAUDE.md` unilateralmente en lo que afecta al otro (roles, reglas,
  alcance). Eso se habla antes.
- ❌ No se suben archivos binarios pesados (vídeos, datasets, PDFs grandes). Enlázalos
  desde `context/` en su lugar.

---

## 5. Dónde vive el contexto

| Carpeta | Qué contiene |
|---|---|
| `context/` | Documentos de referencia estables: briefs, investigación, material de clientes, especificaciones. Lo que Claude debe poder consultar para entender el proyecto. |
| `decisiones/` | Un archivo por decisión tomada, con fecha y razonamiento. El **historial de por qué** el proyecto es como es. |
| `notas/` | Apuntes de trabajo y conclusiones sacadas de conversaciones. Material en crudo, se permite que esté desordenado. |

Cada carpeta tiene su propio `README.md` con el detalle y el formato esperado.

**Para Claude:** cuando necesites contexto sobre este proyecto, lee en este orden:
1. Este archivo (`CLAUDE.md`)
2. `decisiones/` — lo que ya está cerrado, empezando por lo más reciente
3. `context/` — la referencia de fondo
4. `notas/` — lo tentativo; trátalo como borrador, no como verdad establecida

Si tras leer esos cuatro sitios sigue faltando información para hacer bien la tarea,
**pregunta en vez de inventar**.
