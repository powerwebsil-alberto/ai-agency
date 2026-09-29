# ONBOARDING — Cómo empezar a trabajar aquí

Guía para el colaborador que se incorpora. Sigue los pasos en orden.

---

## 0. Antes de nada

Necesitas:
- **Git** instalado → https://git-scm.com/downloads
- Una **cuenta de GitHub**, y que Alberto te haya añadido como colaborador del
  repositorio (Settings → Collaborators en GitHub)
- **Claude Code** instalado, si vas a trabajar con Claude en este repo

Comprueba que Git funciona:
```bash
git --version
```

---

## 1. Configura tu identidad en Git

Solo se hace una vez por ordenador. Sirve para que los commits aparezcan a tu nombre:

```bash
git config --global user.name "Tu Nombre"
```

```bash
git config --global user.email "tu@email.com"
```

Usa **el mismo email que tienes en GitHub**, o tus commits no se asociarán a tu cuenta.

---

## 2. Clona el repositorio

```bash
git clone [URL-DEL-REPO-EN-GITHUB]
```

> ⚠️ `[URL-DEL-REPO-EN-GITHUB]` es un placeholder. Alberto te pasará la URL real,
> con este aspecto: `https://github.com/usuario/ai-agency.git`

Entra en la carpeta:

```bash
cd ai-agency
```

---

## 3. Orientación: lee esto, en este orden

1. **`CLAUDE.md`** — qué es el proyecto, quién hace qué, reglas de trabajo
2. **`decisiones/`** — lo que ya está cerrado y por qué (empieza por la fecha más reciente)
3. **`context/`** — documentos de referencia
4. **`notas/`** — apuntes en crudo; es borrador, no verdad establecida

Cada carpeta tiene su propio `README.md` que explica qué va dentro y en qué formato.

El proyecto está **en fase de exploración**: todavía no hay stack ni alcance
decidido. Muchos campos de `CLAUDE.md` son placeholders `[PENDIENTE]` a propósito.
Rellenarlos es parte del trabajo.

---

## 4. El ciclo de trabajo diario

Trabajamos **los dos directamente sobre `main`**, sin ramas. Eso es simple pero
frágil: funciona solo si los dos respetamos el ciclo. Son cuatro pasos.

### Paso 1 — SIEMPRE, antes de tocar nada: baja los cambios

```bash
git pull
```

Este es el paso que más conflictos evita. Hazlo cada vez que te sientas a trabajar,
aunque creas que no ha cambiado nada.

### Paso 2 — Trabaja

Edita, escribe, crea archivos.

### Paso 3 — Comitea lo que hiciste

```bash
git add .
```

```bash
git commit -m "Añade notas de la sesión sobre nichos"
```

Commits **pequeños y frecuentes**: uno por unidad de trabajo terminada, no uno gigante al final del día.

### Paso 4 — Sube inmediatamente

```bash
git push
```

**No dejes commits sin subir.** Un commit local que nadie ve es un conflicto futuro.

---

## 5. Cómo evitar conflictos de merge

Un conflicto ocurre cuando los dos editamos **el mismo trozo del mismo archivo**
sin habernos sincronizado. Estas seis reglas lo hacen casi imposible:

1. **`git pull` antes de empezar. Siempre.** Sin excepción.
2. **`git push` justo después de cada commit.** No acumules trabajo local.
3. **Archivos separados por persona.** En `notas/` y `decisiones/`, un archivo por
   tema y por sesión, con tu fecha en el nombre. Dos archivos distintos nunca chocan.
4. **Avisa antes de tocar un archivo compartido.** `CLAUDE.md` y los `README.md`
   son de los dos: manda un mensaje antes de editarlos, y cuando termines, sube
   el cambio de inmediato.
5. **Si vas a estar horas en algo grande, abre una rama** (ver `CLAUDE.md`, sección 4).
6. **Si vas a estar desconectado un rato, haz `git pull` al volver** antes de
   seguir escribiendo sobre lo que tenías a medias.

### Si aun así pasa un conflicto

Git te avisa al hacer `pull` o `push` con un mensaje tipo `CONFLICT (content):`.
No hay que entrar en pánico ni nada se ha perdido.

Mira qué archivos están en conflicto:
```bash
git status
```

Abre cada archivo marcado. Verás algo así:

```
<<<<<<< HEAD
tu versión
=======
la versión del otro
>>>>>>> main
```

Edita el archivo dejando el texto final que quieres (normalmente: **las dos partes**,
combinadas con sentido) y **borra las líneas `<<<<<<<`, `=======` y `>>>>>>>`**.

Luego:
```bash
git add .
```
```bash
git commit -m "Resuelve conflicto en [archivo]"
```
```bash
git push
```

Si el conflicto toca algo que no escribiste tú, **pregunta al otro antes de resolver**.
No borres su trabajo para que compile.

---

## 6. Comandos que vas a necesitar

```bash
git status
```
Qué has cambiado y qué está sin comitear. Ante cualquier duda, empieza por aquí.

```bash
git log --oneline -10
```
Los últimos 10 commits, para ver en qué ha estado trabajando el otro.

```bash
git diff
```
Qué has cambiado exactamente, línea a línea, antes de comitear.

```bash
git restore [archivo]
```
Deshace tus cambios sin comitear en un archivo. **Ojo: no se recupera.**

---

## 7. Lo que nunca debes hacer

- ❌ **Subir claves, tokens, `.env` o credenciales.** El `.gitignore` cubre lo
  habitual, pero revisa con `git status` antes de `git add .`. Si subes una clave
  por error: **avisa y rota la clave inmediatamente** — borrarla en un commit
  posterior no la elimina del historial.
- ❌ **`git push --force`.** Puede borrar el trabajo del otro. Nunca sobre `main`.
- ❌ **`git reset --hard`** sobre commits ya subidos.
- ❌ **Borrar o reescribir un archivo de `decisiones/` ajeno.** Una decisión que
  ya no vale se supersede con una nueva, no se borra.
- ❌ **Subir binarios pesados** (vídeos, datasets, PDFs grandes). Súbelos a Drive
  y pon el enlace en `context/`.

---

## 8. Primera tarea sugerida

Para romper el hielo y comprobar que todo el ciclo funciona:

1. `git pull`
2. Crea `notas/AAAA-MM-DD-primeras-impresiones.md` con lo que te parece el proyecto
   y las dudas que te han quedado tras leer el repo
3. Rellena tu fila en la tabla de la sección 2 de `CLAUDE.md`
4. `git add .` → `git commit -m "Añade primeras impresiones y mis datos"` → `git push`

Si eso llega a GitHub sin errores, estás dentro.

---

## Dudas

Abre una issue en el repo o menciona a [@powerwebsil-alberto](https://github.com/powerwebsil-alberto).
