# Estructura de los 10 documentos

Genera los 10 archivos con estos nombres exactos dentro de `proyecto/`. Cada uno abre con el nombre del proyecto y la fecha.

No dejes secciones vacías: si algo no se conversó, escribe **Pendiente:** y qué falta definir.

---

## 01-resumen.md

```
# [Proyecto] — Resumen

## Qué es
Una o dos frases. Sin jerga.

## El problema
Qué duele hoy y a quién.

## Cómo lo resuelve
La solución en tres o cuatro líneas.

## Para quién
El usuario principal, en una línea.

## En qué se diferencia
Qué hace distinto a lo que ya existe.

## Estado
Definido con MVP Forge el [fecha]. Sin código todavía.
```

## 02-usuarios.md

```
# Usuarios y roles

## Usuario principal
Quién es, qué hace hoy, qué problema tiene.

## Usuarios secundarios
Los que existen pero no son el foco del V1.

## Quién paga
Puede ser el mismo usuario u otra persona.

## Roles del sistema
Rol / qué puede hacer / qué no puede hacer.

## Recorrido principal
1. Entra
2. Hace [acción]
3. Obtiene [resultado]
```

## 03-mvp.md

```
# Alcance del MVP

## Criterio de corte
Una función entra a V1 solo si, sin ella, el producto no le sirve a nadie.

## V1 imprescindible
- [ ] Función — por qué es imprescindible

## Después de validar
- Función — qué habría que comprobar primero

## Futuro
- Función — por qué hoy no toca

## Qué NO hace este MVP
Lista explícita, para no discutirlo de nuevo en dos semanas.
```

## 04-funcionalidades.md

```
# Funcionalidades del V1

## [Nombre de la función] — P0
- **Objetivo:** qué logra
- **Usuario:** quién la usa
- **Resultado:** qué pasa cuando funciona
- **Dependencias:** qué necesita para existir
- **Terminado cuando:** criterio observable, en una línea

(repetir por cada función, ordenadas P0 → P1 → P2)
```

## 05-stack.md

```
# Stack

## Resumen
Tabla: pieza / herramienta elegida / costo inicial.

**Costo total para empezar: $X**

## [Cada herramienta]
1. Qué es
2. Para qué sirve acá
3. Por qué encaja
4. Costo para empezar
5. Límite del plan gratuito que importa — verificar en el sitio oficial
6. Cuándo habría que pagar
7. Alternativa

## Lo que NO usamos y por qué
Herramientas descartadas y la razón. Evita rediscutirlo después.
```

## 06-arquitectura.md

```
# Arquitectura

## Diagrama
Diagrama de texto simple con las piezas y las flechas entre ellas.

## Las piezas
Qué hace cada una, en una línea.

## Recorrido de una acción real
El usuario aprieta [botón] → qué pasa → dónde se guarda → qué ve de vuelta.

## Decisiones
Qué se decidió, por qué, y qué se descartó.
```

## 07-base-de-datos.md

```
# Base de datos

Si el V1 no necesita base de datos, dilo acá y explica por qué. El resto del archivo se omite.

## Entidades
### [entidad]
| Campo | Tipo | Notas |

## Relaciones
Cómo se conectan las entidades.

## Reglas de acceso
Quién puede ver, crear, editar y borrar cada entidad.
Cada usuario accede solo a lo suyo. Esto se aplica en la base de datos, no solo en la pantalla.

## Datos sensibles
Qué se guarda, por qué es necesario y cómo se protege.
```

## 08-roadmap.md

```
# Roadmap

## Fase 1 — [nombre]
- **Entregable:** qué vas a poder ver o mostrar al terminar
- **Incluye:** funciones
- **Listo cuando:** criterio comprobable

(repetir por fase)

## PRÓXIMA FASE
Solo una. La que empieza mañana.

## Primeros pasos concretos
1.
2.
3.
```

## PRD.md

```
# PRD — [Proyecto]

Documento completo, para leer de corrido o compartir.

1. Resumen ejecutivo
2. Problema y oportunidad
3. Usuarios y roles
4. Alcance del V1 y qué queda fuera
5. Funcionalidades detalladas
6. Stack y costos
7. Arquitectura
8. Modelo de datos y reglas de acceso
9. Seguridad
10. Roadmap
11. Riesgos y supuestos
12. Cómo sabremos que funcionó
```

Es el único documento que se repite con los otros. Está bien: sirve para compartir el proyecto completo de una sola vez.

## INICIAR-DESARROLLO.md

```
# Iniciar desarrollo

## Cómo usar este archivo
Pega el bloque de abajo en Claude Code, Codex o Cursor para construir la primera fase.

## Prompt

---
Voy a construir [proyecto]: [una línea].

Documentación completa en `proyecto/`. Lee `PRD.md` antes de empezar.

**Stack:** [lista]

**Fase 1:** [entregable]

Funciones de esta fase:
- [función] — listo cuando [criterio]

Reglas:
- Solo la Fase 1. Nada de lo que está en "Después de validar" o "Futuro".
- Reglas de acceso en la base de datos desde el principio.
- Validación en el servidor.
- Secretos en variables de entorno, nunca en el frontend.
- Antes de crear archivos, muéstrame el plan.

Parte proponiéndome la estructura de carpetas.
---

## Antes de empezar
- [ ] Cuentas creadas en las herramientas del stack
- [ ] Repositorio creado
- [ ] Variables de entorno definidas
```
