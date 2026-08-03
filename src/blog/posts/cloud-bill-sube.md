---
title: "Por qué tu cloud bill sube (y no es culpa de AWS)"
date: 2026-02-20T00:00:00.000Z
category: "Cloud & performance"
excerpt: "Servicios huérfanos, consultas ineficientes, falta de tagging: los culpables más comunes del gasto cloud descontrolado en equipos chicos."
layout: "layouts/post.njk"
permalink: "/blog/{{ page.fileSlug }}/"
---

Cuando un cliente me dice *"el cloud bill sube y no sé por qué"*, espero encontrar uno de estos cuatro culpables. En la práctica, casi siempre aparecen varios a la vez.

## 1. Servicios huérfanos

Instancias que ya no sirven a nadie pero siguen corriendo (y facturando). Suceden cuando:

- Un proyecto piloto quedó montado "por si acaso".
- Un entorno de staging quedó encendido después de una demo.
- Un dev levantó algo para probar y nadie lo apagó.

**El arreglo:** inventario de todo lo que corre, con owner y propósito. Todo lo que no tenga dueño, se apaga.

## 2. Instancias sobredimensionadas

El proveedor de cloud te deja elegir el tamaño, pero nadie vuelve a mirarlo. La base de datos que necesitaba 16 GB de RAM para el lanzamiento tal vez use 2 GB de media. Y la seguís pagando como si fuera un pico permanente.

**El arreglo:** mirar las métricas de utilización del último mes, no del día del lanzamiento. La mayoría de las cargas de trabajo de un equipo chico pueden bajar de tamaño sin tocar nada más.

## 3. Consultas ineficientes

Este es el más silencioso: el sistema funciona, pero cada consulta hace un *full scan* de una tabla gigante. Resultado: más CPU, más disco, más transferencia de datos. Y con un solo "feature que anda medio lento" multiplicás el costo de todo el clúster.

**El arreglo:** monitorear las consultas lentas, agregar índices, revisar los `N+1`. La optimización de queries es la optimización de costos más barata que existe.

## 4. Sin visibilidad ni ownership

Sin tagging por equipo/proyecto y sin alertas de gasto, nadie sabe quién gasta qué. El bill llega, nadie lo quiere abrir, y el mes siguiente repite.

**El arreglo:** tagging obligatorio desde el día uno, presupuestos con alertas, y un dueño por cada servicio. La accountability es el 50% del problema.

## La arquitectura de costos

Reducir el bill no es solo apagar cosas. Es hacer que el gasto sea **explicable**:

- Cada servicio responde a un propósito y tiene un dueño.
- Cada costo se puede atribuir a un equipo o proyecto.
- Cada dólar gastado tiene una alerta si se sale de rango.

Con eso, el cloud bill deja de ser un misterio y vuelve a ser una decisión de negocio.

---

*¿Tu cloud bill sube y nadie quiere abrirlo? [Revisemos qué estás pagando de más](/contacto/).*
