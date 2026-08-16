# MVP Forge en Claude Code — Builder Edition

Para desarrolladores. Corre en tu computador y deja la documentación escrita en archivos.

Necesitas Claude Code instalado.

---

## 1. Copia la carpeta

Copia `mvp-forge-claude-code/` **completa** al lugar donde quieras trabajar.

Puedes renombrarla como tu proyecto. Da lo mismo el nombre.

> **Ojo con esto.** Dentro va una carpeta oculta `.claude/`, y ahí vive la Skill. En Windows y en macOS el explorador de archivos no la muestra por defecto, y si copias "lo que se ve" te la dejas fuera. Si después `/crear-proyecto` no aparece, es casi siempre por esto.
>
> - **Windows:** en el Explorador, pestaña Vista → marca *Elementos ocultos*.
> - **macOS:** en Finder, `Cmd + Shift + .`
> - **Terminal (lo más seguro):** `cp -r mvp-forge-claude-code /ruta/destino`

## 2. Abre la carpeta en tu terminal

```bash
cd mvp-forge-claude-code
claude
```

## 3. Ejecuta la Skill

```
/crear-proyecto
```

Si escribes `/cr` debería autocompletar. Si el comando no aparece en la lista, salta a "Si algo no resulta".

## 4. Responde la entrevista

MVP Forge pregunta de a una, y la siguiente pregunta depende de lo que respondas. Son 9 etapas.

No te apures: mientras mejor respondas la parte del problema y los usuarios, mejor queda el stack.

---

## Qué genera

Al cerrar la entrevista, escribe en `proyecto/`:

```
proyecto/
├── 01-resumen.md
├── 02-usuarios.md
├── 03-mvp.md
├── 04-funcionalidades.md
├── 05-stack.md
├── 06-arquitectura.md
├── 07-base-de-datos.md
├── 08-roadmap.md
├── PRD.md
└── INICIAR-DESARROLLO.md
```

`INICIAR-DESARROLLO.md` trae un prompt listo para pegar y empezar a construir la primera fase.

MVP Forge define primero. No empieza a programar durante la entrevista, ni después, hasta que se lo pidas.

---

## Dónde está la Skill

```
mvp-forge-claude-code/
├── CLAUDE.md
└── .claude/
    └── skills/
        └── crear-proyecto/
            ├── SKILL.md
            └── references/
                ├── entrevista.md
                ├── free-first.md
                └── plantillas.md
```

Si quieres MVP Forge disponible en **todos** tus proyectos y no solo en esta carpeta, copia `crear-proyecto/` completa a `~/.claude/skills/`.

---

## Si algo no resulta

**`/crear-proyecto` no aparece.**
Casi siempre es la carpeta `.claude/` perdida al copiar. Verifica desde la terminal, dentro de la carpeta:

```bash
ls -la .claude/skills/crear-proyecto/
```

Tienes que ver `SKILL.md`. Si no está, vuelve al paso 1 y copia con `cp -r`.

**Aparece pero no arranca la entrevista.**
Confirma que estás ejecutando `claude` desde dentro de `mvp-forge-claude-code`, no desde la carpeta de más arriba.

**Empieza a programar en vez de entrevistar.**
Escríbele: `Para. Primero terminemos la definición según la Skill.`

**Hace varias preguntas juntas.**
Escríbele: `Una sola pregunta por turno.`

---
MVP Forge · DROP #01 — Álvaro Labs
