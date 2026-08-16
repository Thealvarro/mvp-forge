# MVP Forge en Codex — Builder Edition

Para desarrolladores. Se instala una vez y queda disponible en todos tus proyectos.

Empaquetado como Agent Skill.

---

## 1. Instala la Skill

Desde la carpeta `04-CODEX/`:

```bash
codex skill install ./SKILL-PARA-CODEX/mvp-forge-builder
```

Si tu versión de Codex no reconoce ese comando, usa la instalación manual de abajo. Hace exactamente lo mismo.

### Instalación manual

1. Copia la carpeta `SKILL-PARA-CODEX/mvp-forge-builder/` completa.
2. Pégala en tu carpeta de Skills de Codex, normalmente `~/.codex/skills/`.
3. Tiene que quedar así:

```
~/.codex/skills/mvp-forge-builder/
├── SKILL.md
└── references/
    ├── entrevista.md
    ├── free-first.md
    └── plantillas.md
```

4. Reinicia Codex para que la detecte.

En esta carpeta también está `mvp-forge-builder-codex-skill.zip` con el mismo contenido, por si prefieres descomprimirlo directamente en `~/.codex/skills/`.

## 2. Verifica que quedó instalada

```bash
codex skill list
```

Tiene que aparecer `mvp-forge-builder`.

## 3. Úsala

Abre Codex en la carpeta donde quieras crear el proyecto e invócala:

```
@mvp-forge-builder Quiero crear un proyecto
```

Escribiendo `@mvp-forge` debería autocompletar.

También funciona pidiéndolo en lenguaje natural:

```
Usa MVP Forge para ayudarme a definir un nuevo proyecto
```

## 4. Responde la entrevista

Pregunta de a una, y la siguiente pregunta depende de lo que respondas. Son 9 etapas.

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

`INICIAR-DESARROLLO.md` trae un prompt listo para pegar y construir la primera fase.

MVP Forge define primero. No empieza a programar hasta que tú se lo pidas.

---

## Instalar desde GitHub

Con el proyecto ya publicado, también puedes pedirle a la Skill `skill-installer` de Codex que instale MVP Forge desde el repositorio:

```
https://github.com/Thealvarro/mvp-forge
```

La ruta de la Skill dentro del repo es `MVP-Forge-DROP-01/04-CODEX/SKILL-PARA-CODEX/mvp-forge-builder`.

---

## Si algo no resulta

**No aparece en `codex skill list`.**
Revisa que `SKILL.md` esté directamente dentro de `~/.codex/skills/mvp-forge-builder/` y no un nivel más abajo. Es el error más común al descomprimir.

**Se salta la entrevista y empieza a escribir código.**
Escríbele: `Para. Primero terminemos la definición según la Skill.`

**Hace varias preguntas juntas.**
Escríbele: `Una sola pregunta por turno.`

---
MVP Forge · DROP #01 — Álvaro Labs
