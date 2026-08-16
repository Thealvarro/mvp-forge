# Ejemplo real — "una app para reservar en peluquerías"

Un caso completo de principio a fin: cómo se ve la entrevista y qué documentos salen.

Es un ejemplo, no una plantilla. Tu proyecto va a llevar otras preguntas, porque cada respuesta cambia la siguiente.

---

# Parte 1 — Cómo se ve la entrevista

## Etapa 1 — Idea y problema

**MVP Forge:** Cuéntame qué quieres crear, como si se lo explicaras a un amigo.

**Persona:** Una app para reservar horas en peluquerías.

**MVP Forge:** Eso es la solución. Devolvámonos un paso: ¿qué te llevó a pensar en esto? ¿Viste algo que no funcionaba?

**Persona:** Mi hermana tiene una peluquería y pierde como media hora al día contestando WhatsApps para agendar. Y a veces se le pasan y pierde clientas.

> Ojo lo que acaba de pasar: la persona llegó con una solución y el agente la devolvió al problema. Esa segunda respuesta vale mil veces más que la primera, y es la que define todo el proyecto.

**MVP Forge:** Ahí está el problema real: se le va tiempo contestando y se le escapan clientas. ¿Cómo lo maneja hoy exactamente? ¿Tiene un cuaderno, una agenda en el celular, algo?

**Persona:** Un cuaderno. Y el WhatsApp.

**MVP Forge:** Entendido. Antes de seguir, para calibrar cómo te explico las cosas: ¿nunca has creado software, has hecho cosas con IA o no-code, o desarrollas habitualmente?

**Persona:** Nunca he creado nada.

> A partir de acá el agente explica cada término técnico al usarlo por primera vez.

## Etapa 2 — Usuarios

**MVP Forge:** ¿Quién va a usar esto en el día a día?

**Persona:** Mi hermana y las clientas.

**MVP Forge:** Son dos usuarios distintos con necesidades distintas. ¿Cuál sufre más el problema hoy: tu hermana perdiendo tiempo, o las clientas que no logran agendar?

**Persona:** Mi hermana. Las clientas igual la ubican por WhatsApp.

**MVP Forge:** Entonces el V1 se diseña para ella. Las clientas son usuarias, pero la que tiene el dolor es tu hermana. Eso cambia todo: no necesitamos que las clientas se creen una cuenta.

## Etapa 3 — MVP, y el momento del control de alcance

**Persona:** También quiero que mande recordatorios automáticos, que tenga sistema de puntos para clientas frecuentes, que muestre fotos de los cortes, que acepte pagos online, y estaría bueno que otras peluquerías puedan usarla también.

**MVP Forge:** Ojo, vamos sumando funciones. Te muestro lo que llevamos:

1. Agendar hora
2. Ver la agenda del día
3. Recordatorios automáticos
4. Sistema de puntos
5. Galería de fotos
6. Pagos online
7. Multi-peluquería

Si solo pudieras lanzar una de estas la próxima semana, y tu hermana dejara de perder media hora al día, ¿cuál sería?

**Persona:** Que las clientas puedan agendar solas y ella vea la agenda.

**MVP Forge:** Perfecto. Eso es tu V1. El resto queda ordenado, no botado:

**V1 imprescindible**
- Clienta reserva sin crear cuenta
- Tu hermana ve la agenda del día
- Tu hermana bloquea horarios

**Después de validar**
- Recordatorios automáticos — cuando haya reservas reales
- Pagos online — cuando exista el problema de las que no llegan

**Futuro**
- Sistema de puntos, galería, multi-peluquería

Ojo con la última: multi-peluquería no es una función, es otro producto. Cambia el modelo de datos completo. Si eso es lo que quieres construir de verdad, mejor lo decidimos ahora y no en tres meses.

**Persona:** No, partamos con la de mi hermana.

## Etapa 5 — Stack, con FREE-FIRST

**MVP Forge:** Antes de elegir herramientas: esto se puede probar sin programar nada. Un formulario de Google conectado a una planilla te resuelve el 70% en una tarde, gratis.

**Persona:** Ya, pero quiero hacerlo bien, tipo app.

**MVP Forge:** Dale. Te lo digo igual porque a veces es la respuesta correcta y nadie la dice.

Necesitas un lugar donde guardar las reservas. Te recomiendo **Supabase**:

1. **Qué es:** un servicio que te da base de datos, cuentas de usuario y almacenamiento, sin que tengas que instalar ni administrar un servidor. Una base de datos es donde queda guardada la información para que no se pierda al cerrar la página.
2. **Para qué sirve acá:** guarda las reservas y los horarios bloqueados.
3. **Por qué encaja:** trae la parte de cuentas incluida, así que no sumas otra herramienta para el login de tu hermana.
4. **Costo para empezar:** $0.
5. **Límite que te va a importar:** los proyectos del plan gratuito se pausan si nadie los usa por un tiempo. Para una peluquería con reservas diarias no debería pasar, pero confírmalo en supabase.com antes de decidir.
6. **Cuándo tendrías que pagar:** cuando la agenda sea el sistema real del negocio y no puedas arriesgarte a una pausa.
7. **Alternativa:** Google Sheets con Apps Script. Feo, pero gratis para siempre y sirve para el primer mes.

Y una cosa que no es opcional: las clientas van a dejar nombre y teléfono. Eso son datos personales de terceros. Las reglas de acceso van en la base de datos, no en la pantalla, para que nadie pueda sacar el listado completo de clientas de tu hermana escribiendo la dirección correcta en el navegador.

---

# Parte 2 — Los 10 documentos que salieron

## 01-resumen.md

> **Qué es:** una agenda online para una peluquería, donde las clientas reservan solas y la dueña ve su día.
> **El problema:** la dueña pierde ~30 min diarios coordinando por WhatsApp y se le escapan clientas cuando no alcanza a responder.
> **Para quién:** dueña de peluquería de un local, que hoy agenda con cuaderno y WhatsApp.
> **En qué se diferencia:** no le pide cuenta a la clienta. Los sistemas existentes obligan a registrarse y por eso la gente vuelve al WhatsApp.

## 02-usuarios.md

> **Usuario principal:** la dueña. Atiende, agenda y cobra. No es técnica.
> **Usuario secundario:** la clienta. Solo reserva.
> **Quién paga:** la dueña.
> **Roles:** dueña (ve todo, bloquea horarios) · clienta (solo crea su reserva, sin cuenta).
> **Recorrido:** la clienta entra al link → elige día y hora libre → deja nombre y teléfono → recibe confirmación en pantalla.

## 03-mvp.md

> **V1:** reservar sin cuenta · ver agenda del día · bloquear horarios.
> **Después de validar:** recordatorios, pagos online.
> **Futuro:** puntos, galería, multi-peluquería.
> **Qué NO hace:** no cobra, no manda recordatorios, no maneja varias peluquerías, no tiene app de celular.

## 04-funcionalidades.md

> **Reservar una hora — P0**
> Objetivo: que la clienta agende sin escribirle a nadie.
> Terminado cuando: una clienta reserva desde el celular en menos de un minuto y la reserva aparece en la agenda de la dueña.
>
> **Ver la agenda del día — P0**
> Terminado cuando: la dueña abre el link y ve las horas del día ordenadas, sin filtrar nada.
>
> **Bloquear horarios — P0**
> Terminado cuando: la dueña marca un bloque y ese horario deja de aparecer disponible.

## 05-stack.md

> | Pieza | Herramienta | Costo |
> |---|---|---|
> | Frontend | HTML + JavaScript | $0 |
> | Base de datos | Supabase | $0 |
> | Hosting | Vercel | $0 |
>
> **Costo total para empezar: $0**
> No usamos: pasarela de pago (el V1 no cobra) · servicio de correo (no hay recordatorios en V1).

## 06-arquitectura.md

> Celular de la clienta → página web → Supabase → agenda de la dueña.
> Recorrido: la clienta aprieta "reservar" → se valida en el servidor que la hora siga libre → se guarda → se muestra la confirmación.
> La validación va en el servidor porque si dos clientas reservan el mismo minuto, la pantalla no alcanza a darse cuenta.

## 07-base-de-datos.md

> **reservas:** id · nombre · teléfono · fecha_hora · estado
> **bloqueos:** id · fecha_hora_inicio · fecha_hora_fin · motivo
>
> **Reglas de acceso:**
> - Cualquiera puede crear una reserva.
> - Nadie puede leer el listado de reservas, salvo la dueña autenticada.
> - Los horarios disponibles se calculan en el servidor, sin exponer los datos de las clientas.
>
> **Datos sensibles:** nombre y teléfono de terceros. Se guarda solo eso, nada más.

## 08-roadmap.md

> **Fase 1:** la clienta reserva y la dueña ve la agenda. *Listo cuando una clienta real reserva.*
> **Fase 2:** bloqueo de horarios.
> **Fase 3:** recordatorios, solo si las clientas efectivamente están reservando.
>
> **PRÓXIMA FASE: Fase 1.**

## PRD.md

> Junta todo lo anterior. **Riesgo principal:** que las clientas prefieran el WhatsApp igual. **Cómo sabremos que funcionó:** 10 reservas hechas por clientas solas en las primeras dos semanas, sin que la dueña tenga que explicarles cómo.

## INICIAR-DESARROLLO.md

> Un prompt listo para pegar en Claude Code con el stack, la Fase 1 y las reglas de seguridad, que termina con "parte proponiéndome la estructura de carpetas".

---

## Lo que hay que mirar de este ejemplo

- La primera respuesta de la persona era una solución. La buena vino después de repreguntar.
- De 7 funciones, quedaron 3. Y ninguna se botó: quedaron ordenadas.
- "Multi-peluquería" se detectó como otro producto, no como una función más.
- El costo inicial es $0 y el agente igual dijo que se podía validar sin código.
- La seguridad de los datos de las clientas apareció durante la definición, no después.

---
MVP Forge · DROP #01 — Álvaro Labs
