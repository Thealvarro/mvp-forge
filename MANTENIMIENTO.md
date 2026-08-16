# Mantenimiento

Notas para quien edita MVP Forge. No es parte del recurso que descarga el usuario.

## Dónde vive el contenido

El prompt está duplicado a propósito: cada plataforma tiene que funcionar por sí sola, sin depender del resto del ZIP. No hay build ni script de sincronización — es texto, y se mantiene a mano.

**Si cambias las reglas base**, tienes que tocar estos 5 archivos:

```
01-CHATGPT/ARCHIVOS-PARA-SUBIR/MVP-FORGE-CHATGPT.txt        ← fuente principal
01-CHATGPT/SKILL-PARA-SUBIR/mvp-forge-starter/SKILL.md
02-CLAUDE/ARCHIVOS-PARA-SUBIR/01-REGLAS.md
03-CLAUDE-CODE/mvp-forge-claude-code/.claude/skills/crear-proyecto/SKILL.md
04-CODEX/SKILL-PARA-CODEX/mvp-forge-builder/SKILL.md
```

Los dos últimos son Builder: llevan además la tabla de los 10 archivos de salida.

**Si cambias la guía de entrevista**, el archivo fuente es:

```
01-CHATGPT/ARCHIVOS-PARA-SUBIR/MVP-FORGE-CHATGPT-INSTRUCCIONES.md
```

y se copia idéntico a:

```
01-CHATGPT/SKILL-PARA-SUBIR/mvp-forge-starter/references/entrevista.md
02-CLAUDE/ARCHIVOS-PARA-SUBIR/02-ENTREVISTA.md
03-CLAUDE-CODE/.../crear-proyecto/references/entrevista.md
04-CODEX/.../mvp-forge-builder/references/entrevista.md
```

**Si cambias el catálogo FREE-FIRST**, la fuente es:

```
01-CHATGPT/SKILL-PARA-SUBIR/mvp-forge-starter/references/free-first.md
```

y se copia a las carpetas `references/` de Claude Code y Codex.

**Si cambias la estructura de los 10 documentos**, tocas:

```
PLANTILLAS/                                          ← los 10 archivos sueltos
.../crear-proyecto/references/plantillas.md          ← versión para la Skill
.../mvp-forge-builder/references/plantillas.md       ← idem
```

## Los ZIP

Hay tres, y todos se regeneran cuando cambia el contenido:

| ZIP | Contiene |
|---|---|
| `MVP-Forge-DROP-01.zip` (raíz) | El drop completo |
| `01-CHATGPT/mvp-forge-starter-chatgpt-skill.zip` | Solo `mvp-forge-starter/` |
| `04-CODEX/mvp-forge-builder-codex-skill.zip` | Solo `mvp-forge-builder/` |

Regenerarlos desde la raíz del repo (PowerShell):

```powershell
Remove-Item MVP-Forge-DROP-01.zip -ErrorAction SilentlyContinue
Compress-Archive -Path MVP-Forge-DROP-01 -DestinationPath MVP-Forge-DROP-01.zip

$cg = "MVP-Forge-DROP-01\01-CHATGPT"
Remove-Item "$cg\mvp-forge-starter-chatgpt-skill.zip" -ErrorAction SilentlyContinue
Compress-Archive -Path "$cg\SKILL-PARA-SUBIR\mvp-forge-starter" -DestinationPath "$cg\mvp-forge-starter-chatgpt-skill.zip"

$cx = "MVP-Forge-DROP-01\04-CODEX"
Remove-Item "$cx\mvp-forge-builder-codex-skill.zip" -ErrorAction SilentlyContinue
Compress-Archive -Path "$cx\SKILL-PARA-CODEX\mvp-forge-builder" -DestinationPath "$cx\mvp-forge-builder-codex-skill.zip"
```

El nombre del ZIP de la raíz **no lleva versión**. Es a propósito: el link se comparte por WhatsApp y ManyChat, y si el nombre cambia con cada versión, los links repartidos se rompen. La versión va en `VERSION.txt` y en `CHANGELOG.md`.

`MVP-Forge-DROP-01.zip` además se sube como asset de la release. Ese es el link que se reparte:

```
https://github.com/Thealvarro/mvp-forge/releases/latest/download/MVP-Forge-DROP-01.zip
```

Apunta siempre a la última release, así que no hay que actualizarlo al publicar una versión nueva. No repartas el link a `/blob/…`: esa vista intenta previsualizar el ZIP y falla con "Error loading page".

```powershell
gh release upload v2.1.1 MVP-Forge-DROP-01.zip --clobber
```

## La portada

`assets/imagen-mvp-forge.png` es la portada oficial y la promesa pública del producto. Si cambian los nombres de archivo o los comandos de instalación, **la imagen queda mintiendo**. Revisa que sigan calzando:

- Los tres archivos de ChatGPT: `MVP-FORGE-CHATGPT.txt`, `MVP-FORGE-CHATGPT-INSTRUCCIONES.md`, `INSTRUCCIONES.md`
- Claude: `ARCHIVOS-PARA-SUBIR/` y `INSTRUCCIONES-PARA-PEGAR.txt`
- Claude Code: `cd mvp-forge-claude-code` → `claude` → `/crear-proyecto`
- Codex: `codex skill install` y `@mvp-forge…`
- La versión que muestra arriba a la derecha

## Antes de publicar una versión nueva

- [ ] Los 5 archivos de reglas dicen lo mismo
- [ ] Los 4 `entrevista.md` son idénticos
- [ ] Las 2 Skills Builder listan los 10 archivos de salida
- [ ] Los 3 ZIP regenerados
- [ ] `VERSION.txt` y `CHANGELOG.md` actualizados
- [ ] La portada sigue calzando con el contenido
- [ ] Probado de verdad en al menos una plataforma
- [ ] `MVP-Forge-DROP-01.zip` subido como asset de la release
