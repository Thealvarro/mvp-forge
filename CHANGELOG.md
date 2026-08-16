# Changelog

## 2.1.1

MVP Forge ahora tiene voz propia.

Se agregó una sección **Tono** a las reglas base: español neutro, entendible en cualquier país hispanohablante, sin modismos locales. El agente mantiene ese tono aunque el entorno de trabajo tenga otro estilo configurado, salvo que la persona pida expresamente algo distinto.

Sin este cambio, en Claude Code y Codex el agente heredaba el estilo personal del usuario (por ejemplo, un `CLAUDE.md` global con modismos de un país), y la experiencia dejaba de ser consistente entre plataformas.

## 2.1.0

Primera versión pública de MVP Forge — DROP #01 de Álvaro Labs.

**Contenido**
- Entrevista adaptativa de 9 etapas, con árbol de decisión por etapa: cada pregunta depende de la respuesta anterior.
- Control de alcance: MVP Forge detecta cuando se acumulan funciones, muestra la lista y obliga a reclasificar en V1 / Después de validar / Futuro.
- FREE-FIRST con catálogo de referencia y ficha obligatoria de 7 puntos por herramienta. Sin cifras inventadas: los límites se entregan como referencia y se mandan a verificar en el sitio oficial.
- Seguridad mínima obligatoria cuando el proyecto toca cuentas, datos personales o pagos.
- Starter y Builder diferenciados de verdad: Starter explica términos técnicos y entrega los documentos como texto; Builder los escribe en `proyecto/`.
- Las dos Skills Builder listan los 10 archivos de salida con nombre exacto y contenido esperado.

**Plataformas**
- ChatGPT — Starter, vía Proyecto o Skill.
- Claude — Starter, vía Proyecto.
- Claude Code — Builder, Skill `/crear-proyecto`.
- Codex — Builder, Agent Skill `mvp-forge-builder`.

**Material nuevo**
- `PLANTILLAS/` — los 10 documentos en blanco.
- `EJEMPLOS/` — un caso completo, de la primera pregunta al último documento.

**Estructura**
- README landing con portada.
- ZIP con nombre estable, sin versión, para que los links compartidos no se rompan entre releases.
- Licencia MIT.
