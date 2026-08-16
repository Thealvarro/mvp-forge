# Iniciar desarrollo

## Cómo usar este archivo

Copia el bloque de abajo y pégalo en Claude Code, Codex o Cursor. Es el prompt para construir la primera fase.

---

## Prompt

```
Voy a construir [proyecto]: [una línea de qué es].

La documentación completa está en `proyecto/`. Lee `PRD.md` antes de empezar.

Stack definido:
- [pieza]: [herramienta]

Fase 1: [entregable]

Funciones de esta fase:
- [función] — listo cuando [criterio]

Reglas:
- Construye solo la Fase 1. Nada de lo que está en "Después de validar" o "Futuro".
- Reglas de acceso en la base de datos desde el principio, no después.
- Toda validación también en el servidor.
- Secretos en variables de entorno, nunca en el frontend.
- Antes de crear archivos, muéstrame el plan y espera que lo apruebe.

Parte proponiéndome la estructura de carpetas.
```

---

## Antes de empezar

- [ ] Cuentas creadas en las herramientas del stack
- [ ] Repositorio creado
- [ ] Variables de entorno definidas
- [ ] Leíste `03-mvp.md` una última vez para recordar qué queda fuera

## Mientras construyes

Si aparece la tentación de agregar "una cosita más", vuelve a `03-mvp.md`. Para eso está la lista de lo que NO hace este MVP.
