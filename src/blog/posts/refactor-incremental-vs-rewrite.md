---
title: "Refactorización incremental vs rewrite total"
date: 2026-05-12T00:00:00.000Z
category: "Refactor vs rewrite"
excerpt: "El rewrite total es el camino más rápido al fracaso. El patrón Strangler Fig, la estrategia de módulos y cómo decidir sin paralizarse."
layout: "layouts/post.njk"
permalink: "/blog/{{ page.fileSlug }}/"
---

Cuando un sistema legacy empieza a doler, la tentación más grande es una: **reescribir todo desde cero**. Es una idea seductora porque promete empezar limpio, sin el espagueti, sin el miedo. También es la forma más rápida de matar el negocio.

## Por qué el rewrite total fracasa

El rewrite total tiene tres problemas estructurales:

1. **El sistema viejo sigue vivo.** Mientras reescribes, el negocio no se detiene. Los clientes siguen usando el sistema viejo, que sigue teniendo bugs y sigue pidiendo features. Ahora tenés dos sistemas que mantener con el mismo equipo.

2. **Nunca vas a poder replicar todo.** El sistema viejo tiene años de reglas de negocio acumuladas, la mitad de ellas invisibles, en nadie sabe qué función. En el rewrite "limpio" esas reglas no existen hasta que un cliente las reclama.

3. **El rewrite se vuelve un feature gigante sin entregas.** Nueve meses después seguís "a un 80%". El board pierde paciencia. El equipo se quema. El proyecto muere o se convierte en un costo interminable.

## El patrón Strangler Fig

La alternativa es el patrón *Strangler Fig* (o *strangler pattern*): se reemplaza un sistema viejo gradualmente, pieza por pieza, hasta que el nuevo lo "estrangula".

Funciona así:

1. **Identificá un módulo del sistema viejo** (por ejemplo, facturación).
2. **Reimplementalo en el sistema nuevo**, de forma aislada.
3. **Redirigí el tráfico del módulo viejo al nuevo** (con un proxy, feature flag o ruta nueva).
4. **Dejá el módulo viejo dormido pero vivo** — como respaldo hasta que el nuevo esté probado.
5. **Repetí con el siguiente módulo.**

Mientras tanto, el negocio sigue funcionando. Cada entrega es pequeña, testeable y revertible.

## Modular Monolith: el paso intermedio que la mayoría se saltea

Antes de saltar a microservicios, la mayoría de los sistemas chicos deberían pasar por un **Modular Monolith**: un solo deployable, pero con módulos con boundaries claros y comunicación explícita.

¿Por qué? Porque microservicios resuelven un problema de escala que la mayoría de los equipos de 2–10 devs no tiene. Agregan complejidad de red, distribución, mensajería y observabilidad. El Modular Monolith te da el orden sin la complejidad.

## Cómo decidir sin paralizarse

El framework que uso con mis clientes:

- **¿El módulo está estable y no molesta?** No lo toques. Hay deuda que no vale la pena pagar.
- **¿El módulo se va a reescribir de todos modos por una feature grande?** Refactorizalo antes de la feature.
- **¿El cuello de botella es técnico o de proceso?** Si es de proceso (deploys, tests), el problema no se arregla con otro lenguaje.

El rewrite total casi nunca es la respuesta. La modernización incremental, casi siempre lo es.

---

*¿Tu monolito te tiene en modo bomberos? [Hablemos de cómo sacarlo sin apagar el negocio](/contacto/).*
