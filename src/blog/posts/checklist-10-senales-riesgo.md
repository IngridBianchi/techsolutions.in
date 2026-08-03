---
title: "Checklist: 10 señales de que tu sistema ya es riesgo de negocio"
date: 2026-04-08T00:00:00.000Z
category: "Legacy & deuda técnica"
excerpt: "Desde 'el deploy lo hace una sola persona' hasta 'nadie sabe cuánto cuesta la nube'. Una checklist práctica para diagnosticar tu arquitectura hoy."
layout: "layouts/post.njk"
permalink: "/blog/{{ page.fileSlug }}/"
---

La mayoría de los equipos no se da cuenta de que su sistema es un riesgo hasta que ya es tarde (una caída en producción, un cliente grande que se va, una auditoría que sale mal). Esta checklist te ayuda a diagnosticarlo en 20 minutos.

Si marcás **3 o más**, tu sistema ya está frenando el negocio.

## Las 10 señales

1. **"Funciona… hasta que deja de funcionar."** Si nadie sabe *por qué* funciona, nadie puede arreglar *cuándo* deja de funcionar.

2. **El deploy lo hace una sola persona, de madrugada, "por las dudas".** Un pipeline de CI/CD con rollback rápido no es lujo. Es la diferencia entre dormir y no.

3. **Solo una persona entiende el código del core.** Puede ser el founder, un dev senior, o un ex dev que se fue. Si esa persona no está, el sistema no se puede mantener.

4. **No hay tests en los flujos críticos.** Sin red de seguridad, cada cambio es una apuesta. Los errores aparecen en producción, no en desarrollo.

5. **Cada feature tarda 3 veces más de lo que debería.** El sprint que se estira siempre por "cosas que se rompieron" no es un problema de estimación: es deuda técnica.

6. **Los errores en producción se repiten.** Si el mismo incidente vuelve a pasar, no hay arreglo: hay *parche*.

7. **Nadie sabe cuánto cuesta la nube.** Sin tagging, sin visibilidad, sin ownership por equipo, el gasto cloud es un misterio que se resuelve solo en el momento de pagar.

8. **La documentación no existe o está desactualizada.** El conocimiento vive en la cabeza de la gente, y la gente se va.

9. **La única forma de probar el cambio es "probarlo en producción".** Sin entorno de staging confiable, cada deploy es una lotería.

10. **El equipo está en modo bomberos.** Si el 70% del tiempo se va en estabilidad, queda el 30% para producto. No es un problema de gestión: es un síntoma de arquitectura.

## Qué hacer si marcaste más de 3

No hace falta que todo se arregle a la vez. Priorizá así:

1. **Primero la red de seguridad**: pipeline de CI/CD, tests en el flujo crítico, rollback rápido.
2. **Después la visibilidad**: métricas, logs, monitoreo, costos cloud.
3. **Después la arquitectura**: módulos con boundaries, refactor incremental, Strangler Fig.

El orden importa. Sin red de seguridad, tocar arquitectura es jugarte todo.

---

*¿Querés saber cuántas de estas señales tiene tu sistema? [Agendá una auditoría de 48 horas](/contacto/).*
