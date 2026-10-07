# Guion de la demostración (10 min + 5 de preguntas)

Antes de empezar: abre la demo (GitHub Pages o `index.html`), con F12 listo en modo dispositivo.

| Min | Parte | Quién | Qué decir / hacer |
|---|---|---|---|
| 0:00–1:00 | **Contexto** | Rol 1 | El problema (no hay un medio organizado para reportar desperdicio de agua y basura), el objetivo de EcoReport y que el prototipo es solo HTML5 + CSS3, sin backend ni JavaScript. Presentar al equipo. |
| 1:00–2:30 | **Acceso** | Rol 3 | Inicio, registro con un error a propósito (validación nativa), registro correcto → aviso en login → entrar. |
| 2:30–4:00 | **Ciudadano** | Rol 4 | Dashboard, **Nuevo reporte** (campos, ubicación, evidencia), detalle del reporte, Mis reportes con filtros. |
| 4:00–5:00 | **Otros perfiles** | Rol 4 | Atención (modal «Registrar acción»), Administración (pestañas y modal), Estadísticas y descarga del CSV. |
| 5:00–7:00 | **Prueba responsiva** | Rol 2 | F12 → modo dispositivo: 375, 768 y 1280 px; menú hamburguesa, tablas apiladas, navegación con Tab. Mostrar la guía de estilo. |
| 7:00–10:00 | **Retos y aprendizajes** | Todos | Un reto técnico, algo aprendido de Git/PR y qué mejorarían con backend. |
| 10:00–15:00 | **Preguntas** | Todos | Ver la tabla de abajo. |

## Qué debe poder explicar cada quien

| Rol | Archivos | Preguntas probables |
|---|---|---|
| Rol 1 | README, matriz, ramas y PR | ¿Cómo trabajaron en equipo? ¿Qué RF cubre cada vista? ¿Cómo se publicó? |
| Rol 2 | `css/styles.css`, guía de estilo | ¿Qué son las variables `:root`? ¿Cómo logran lo responsivo (`grid`, media queries)? ¿Por qué esos colores? |
| Rol 3 | `index`, `login`, `registro` | ¿Cómo validan sin JavaScript (`required`, `pattern`, `type`)? ¿Qué es HTML semántico? ¿Para qué sirve `label for`? |
| Rol 4 | módulos y vistas internas | ¿Cómo funcionan sin JavaScript las pestañas (`radio` + `:checked`), el modal (`:target`) y los filtros (`:has()`)? |

Preguntas que pueden hacerles: «¿Por qué no usaron JavaScript?» (porque la actividad pide HTML5 y CSS3) y «¿qué le faltaría para ser una aplicación real?» (backend y base de datos para guardar reportes, sesiones y búsqueda).
