# FREE-FIRST — catálogo de referencia

Este catálogo te dice **qué existe y cuándo encaja cada cosa**. No fija números.

Los planes gratuitos cambian todo el tiempo: cuotas, límites y precios se mueven sin aviso. Por eso acá no hay cifras. Cuando recomiendes una herramienta, di qué límite hay que mirar y manda a confirmarlo en el sitio oficial antes de decidir. Nunca inventes una cifra para sonar preciso.

---

## Regla cero: ¿de verdad hay que construir algo?

Antes de armar cualquier stack, pregúntate si el V1 se puede validar sin escribir código.

Muchos MVPs reales parten así:
- Un formulario (Google Forms, Tally) + una planilla + WhatsApp.
- Una landing simple que explique la promesa y junte correos.
- El servicio hecho a mano, atendiendo tú a los primeros 10 usuarios.

Si el proyecto se puede probar sin software, dilo. Es la recomendación más FREE-FIRST que existe, y muchas veces es la correcta.

---

## Formato de ficha

Cada herramienta que recomiendes va con estos 7 puntos, sin saltarse ninguno:

```
**[Nombre]**
1. Qué es: [una línea, sin jerga]
2. Para qué sirve acá: [su rol en ESTE proyecto]
3. Por qué encaja: [por qué esta y no otra]
4. Costo para empezar: [normalmente $0]
5. Límite que te va a importar: [qué mirar — verificar en el sitio oficial]
6. Cuándo tendrías que pagar: [la señal concreta]
7. Alternativa: [gratuita o más barata]
```

---

## Publicar el sitio (hosting)

| Herramienta | Cuándo encaja | Qué mirar del plan gratis |
|---|---|---|
| **Vercel** | Proyectos con React, Next.js, Astro. Deploy automático desde GitHub | Uso mensual y si el proyecto es comercial |
| **Netlify** | Muy parecido a Vercel, sitios estáticos y funciones | Minutos de build y ancho de banda |
| **Cloudflare Pages** | Sitios estáticos con mucho tráfico | Builds por mes |
| **GitHub Pages** | Una landing o documentación, sin backend | Solo sitios estáticos |
| **Render** | Cuando necesitas un servidor de verdad corriendo | Si el servicio se duerme por inactividad |

Para una landing sin backend, GitHub Pages o Cloudflare Pages sobran. No mandes a alguien a montar infraestructura para publicar una página.

## Guardar información (base de datos)

| Herramienta | Cuándo encaja | Qué mirar del plan gratis |
|---|---|---|
| **Supabase** | Base de datos + cuentas de usuario + archivos, todo junto. La opción más completa para partir | Proyectos pausados por inactividad, espacio |
| **Neon** | Solo base de datos, si ya tienes auth resuelto | Horas de cómputo, ramas |
| **Firebase** | Apps móviles, datos en tiempo real | El modelo de cobro por lecturas |
| **Turso / PocketBase** | Proyectos chicos o que corren en un solo servidor | Simplicidad a cambio de menos servicios |

## Cuentas de usuario (autenticación)

Si ya usas Supabase o Firebase, **ya tienes auth incluido**. No agregues otra herramienta.

Si necesitas algo aparte: **Clerk** o **Auth0**. Mira cuántos usuarios activos permite el plan gratis.

Sea cual sea: reglas de acceso en la base de datos, validación en el servidor y protección anti-bots en el registro. Sin excepción.

## Enviar correos

**Resend** para correos del sistema (confirmar cuenta, recuperar contraseña). **Brevo** si además necesitas campañas. Mira el límite de correos por día y si exige verificar tu dominio.

## Guardar archivos e imágenes

**Supabase Storage** si ya usas Supabase. **Cloudflare R2** si vas a mover mucho volumen. **Vercel Blob** si ya estás en Vercel. Mira el espacio y la transferencia mensual.

## Cobrar

Depende del país, no hay una respuesta universal.

- **Chile:** Mercado Pago, Flow, o Transbank / Webpay.
- **Latinoamérica:** Mercado Pago.
- **Internacional:** Stripe, Paddle o Lemon Squeezy.

Casi todas cobran comisión por transacción sin costo fijo mensual, así que empezar sale $0.

**Antes de recomendar cualquiera, pregunta si el V1 realmente cobra.** Muchos MVPs no necesitan pagos: se cobra por transferencia con los primeros usuarios y se automatiza después. Eso es válido y ahorra semanas.

## Usar IA dentro del producto

**Google AI Studio** y **Groq** tienen capa gratuita para probar. **OpenRouter** sirve para comparar modelos sin casarse con uno. Las APIs de **OpenAI** y **Anthropic** se pagan por uso desde el primer llamado.

Ojo: acá el costo escala con los usuarios. Si el producto usa IA en cada acción, dilo derecho y calculen juntos un costo aproximado por usuario antes de seguir.

**La clave está en no exponer nunca la clave de la API en el frontend.** Va en el servidor, siempre.

## Automatizar procesos

**n8n** (puedes instalarlo tú y sale $0), **Make** o **Zapier**. Mira cuántas ejecuciones mensuales permite el plan gratis.

## Otras piezas

- **Código:** GitHub, gratis para repos públicos y privados.
- **Errores:** Sentry, para saber qué se rompió en producción.
- **Visitas:** Umami o Vercel Analytics.
- **Protección anti-bots:** Cloudflare Turnstile, gratis.

---

## Cuándo decir "acá hay que pagar"

FREE-FIRST no es "gratis a toda costa". Di derechamente que hay que pagar cuando:

- El plan gratuito pausa o apaga el proyecto por inactividad y es un producto en uso real.
- Se manejan datos sensibles y el plan gratis no da respaldos.
- El costo de armarlo gratis es mayor, en horas, que pagar unos dólares al mes.
- Es un producto que ya factura. Ahí la infraestructura es un costo del negocio, no un gasto.

Ser honesto acá vale más que forzar una solución gratis que va a fallar en tres semanas.

---
MVP Forge · DROP #01 — Álvaro Labs
