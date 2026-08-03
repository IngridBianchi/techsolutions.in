---
title: "El patrón Strangler Fig explicado para founders no técnicos"
date: 2026-01-25T00:00:00.000Z
category: "Refactor vs rewrite"
excerpt: "Si tu CTO te dice 'hay que reescribir todo', esta es la conversación que necesitás tener. Cómo modernizar sin apagar el negocio."
layout: "layouts/post.njk"
permalink: "/blog/{{ page.fileSlug }}/"
---

Si tu CTO o tech lead viene y te dice *"hay que reescribir todo desde cero"*, tu primera reacción debería ser la misma que si un contratista te dijera que hay que demoler la casa entera porque la cocina tiene una pérdida: *un momento, ¿no hay otra forma?*

La hay. Se llama patrón Strangler Fig, y es como modernizar un sistema sin apagar el negocio.

## La analogía

En la naturaleza, el *strangler fig* es una planta que germina en lo alto de un árbol. Crece alrededor del tronco, baja raíces, y con el tiempo el árbol original muere y queda solo el nuevo. El truco: **nunca hay un momento en que no haya árbol**. El árbol viejo sigue cumpliendo su función mientras el nuevo lo va reemplazando.

Tu sistema es ese árbol. Y el patrón dice: no lo derribes. Envolvelo módulo por módulo.

## Cómo se ve en la práctica

Pensá en tu sistema como piezas, no como un todo. El patrón funciona así:

1. **Elegí una pieza** — la que más te duele: la que más se cae, la que más cambios recibe, la que más cuesta mantener.
2. **Reconstruila bien** — en la nueva arquitectura, con tests, documentada.
3. **Cambiá el tráfico** — una vez que la pieza nueva está probada, que los usuarios usen la nueva. La vieja queda de respaldo, dormida.
4. **Repetí** — cuando confiás en la pieza nueva, pasás a la siguiente.

Mientras tanto, los clientes no ven nada. El sistema nunca se apaga. El negocio nunca deja de funcionar.

## Lo que eso significa para vos como founder

- **No hay fecha de "apagón".** No hay un día en que todo se corta. Cada pieza migra sola.
- **Hay entregas visibles rápido.** La primera pieza se mejora en semanas, no en meses. El equipo y el board ven progreso real.
- **El riesgo se distribuye.** Si una pieza nueva falla, se revierte y el tráfico vuelve a la vieja. Nunca perdés todo.
- **El costo es predecible.** Pagás modernización de a cuotas, no un proyecto gigante de un año que puede morir a mitad de camino.

## La conversación que necesitás tener con tu CTO

En vez de *"¿cuánto cuesta reescribir todo?"*, preguntá:

- *¿Cuál es la pieza que más nos está costando hoy?*
- *¿Qué pieza podríamos reconstruir primero para ver resultados en un mes?*
- *¿Cómo seguimos entregando features mientras modernizamos?*

Si la respuesta incluye "sin apagar el negocio", están en el camino correcto. Si la respuesta es "necesitamos 9 meses de puro desarrollo", tené cuidado: ese es el camino del rewrite suicida.

---

*¿Te está costando decidir cómo modernizar tu sistema? [Una llamada breve puede aclararlo](/contacto/).*
