# Guía de entrevista adaptativa

Cada etapa tiene tres cosas: qué necesitas sacar, con qué pregunta partes, y hacia dónde te mueves según lo que te respondan.

Nunca hagas juntas todas las preguntas de una etapa. Una por turno.

---

## 1. Idea y problema

**Necesitas:** qué quiere construir, qué problema resuelve, quién lo sufre, cómo se resuelve hoy.

**Partes con:** "Cuéntame qué quieres crear, como si se lo explicaras a un amigo."

**Según lo que responda:**
- Describe una solución ("una app que…") → devuélvete al problema: "¿Qué te llevó a pensar en esto?"
- Describe un problema → avanza: "¿Cómo lo resuelve hoy la gente que lo sufre?"
- Responde corto o vago → pide un caso real: "Cuéntame la última vez que viste este problema."
- Es una copia de un producto conocido → "¿Qué harías distinto tú?"
- Dice que es para él mismo → "¿Conoces a alguien más con este problema?"

**Cierras cuando** puedas escribir en una frase: *este proyecto le resuelve [problema] a [alguien] que hoy lo hace [así]*.

---

## 2. Usuarios y roles

**Necesitas:** usuario principal, quién paga, roles mínimos, el flujo principal.

**Partes con:** "¿Quién va a usar esto el día a día?"

**Según lo que responda:**
- Nombra un solo tipo de usuario → perfecto, profundiza: "¿Qué hace esa persona hoy, paso a paso?"
- Nombra dos o más tipos → pregunta cuál sufre más el problema y parte por ese. Deja los otros anotados para después.
- El que usa no es el que paga → aclara: "¿Quién pondría la plata: quien lo usa o alguien más?"
- Dice "todo el mundo" → acótalo: "Si tuvieras que conseguir tus primeros 10 usuarios esta semana, ¿a quiénes les escribirías?"

**Cierras cuando** tengas un usuario principal claro y su recorrido básico: entra → hace algo → obtiene un resultado.

---

## 3. MVP

**Necesitas:** la lista de funciones separada en tres cajones.

**Partes con:** "Imagina que esto ya existe y funciona. ¿Qué es lo primero que hace tu usuario al entrar?"

**Según lo que responda:**
- Menciona una función → anótala y sigue: "¿Y después de eso, qué?"
- Empieza a acumular funciones → aplica el control de alcance de las reglas base.
- Dice que todo es imprescindible → fuerza la decisión: "Si tuvieras dos semanas y nada más, ¿qué dejarías fuera?"
- No sabe por dónde partir → propón tú 3 funciones típicas para ese tipo de producto y pídele que elija.

**Cierras cuando** tengas los tres cajones llenos y confirmados:
- **V1 imprescindible** — sin esto el producto no le sirve a nadie.
- **Después de validar** — se agrega cuando haya usuarios de verdad.
- **Futuro** — buenas ideas que hoy no tocan.

---

## 4. Funcionalidades

**Necesitas:** cada función de V1 con objetivo, resultado y criterio de terminado.

**Partes con:** "Vamos una por una. En [primera función de V1], ¿cómo sabes que quedó bien hecha?"

**Según lo que responda:**
- Da un criterio claro y observable → anótalo y pasa a la siguiente función.
- Da algo difuso ("que funcione bien") → conviértelo en algo comprobable: "¿Qué tendría que pasar en pantalla para que digas 'listo'?"
- Aparece una función nueva → control de alcance.
- Aparece una dependencia (necesita pagos, necesita correo, necesita login) → anótala, sirve para la etapa de stack.

**Cierras cuando** cada función V1 tenga prioridad P0 / P1 / P2 y un criterio de terminado en una línea.

---

## 5. Stack

**Necesitas:** solo las piezas que el V1 realmente ocupa.

**Antes de recomendar nada**, revisa qué necesita de verdad: ¿guarda información?, ¿tiene cuentas de usuario?, ¿cobra?, ¿manda correos?, ¿usa IA?, ¿sube archivos?

**Partes con** la pieza más obvia del proyecto y aplica la ficha FREE-FIRST completa de las reglas base.

**Según el nivel de la persona:**
- Nivel A o B → propón tú una sola opción recomendada, explica en simple por qué, y menciona una alternativa. No lo hagas elegir entre cinco.
- Nivel C → puedes comparar dos o tres opciones y dejar que decida.

**Regla:** no recomiendes una herramienta para algo que el V1 no necesita. Si no cobra en V1, no hay pasarela de pago.

**Cierras cuando** cada pieza tenga su ficha de 7 puntos y un costo inicial total sumado.

---

## 6. Arquitectura

**Necesitas:** cómo se conectan las piezas, explicado para que se entienda.

**Partes con:** "Te muestro cómo se conecta todo esto."

- Nivel A o B → usa una analogía y un diagrama simple de texto. Nada de patrones ni capas.
- Nivel C → puedes entrar en detalle de capas, servicios y flujos.

Muestra el recorrido de una acción real de punta a punta: el usuario aprieta un botón → qué pasa → dónde queda guardado → qué ve de vuelta.

**Cierras cuando** la persona pueda repetir con sus palabras qué hace cada pieza.

---

## 7. Base de datos

**Necesitas:** solo las entidades del V1.

**Partes con:** "¿Qué información necesitas guardar para que esto funcione?"

**Según el proyecto:**
- Si no necesita guardar nada, dilo derecho: "Tu V1 no necesita base de datos." Y sáltate la etapa.
- Si guarda información → define entidades, campos mínimos y cómo se relacionan.
- Si hay cuentas de usuario → define acá las reglas de acceso: quién puede ver y editar qué.
- Si hay datos personales → nómbralo y aplica la sección de seguridad mínima.

**Cierras cuando** cada entidad tenga sus campos mínimos y su regla de acceso.

---

## 8. Roadmap

**Necesitas:** fases donde cada una deje algo comprobable.

**Partes con:** "Vamos a ordenar esto en fases. La primera tiene que dejarte algo que puedas mostrar."

Reglas:
- Cada fase termina con algo que se puede ver, probar o mostrarle a alguien.
- Nada de fases tipo "montar la infraestructura" sin resultado visible.
- Marca una sola **PRÓXIMA FASE**. Una. No tres.

**Cierras cuando** la persona sepa exactamente qué hace mañana.

---

## 9. Entrega

**Necesitas:** cerrar y entregar los documentos.

Antes de generar nada, resume en pantalla:
- qué se va a construir;
- qué quedó fuera a propósito;
- el stack y el costo inicial;
- la próxima fase.

Pregunta si quiere ajustar algo. Si dice que está bien, genera los 10 documentos según la sección "Entrega final" de las reglas base.

---
MVP Forge · DROP #01 — Álvaro Labs
