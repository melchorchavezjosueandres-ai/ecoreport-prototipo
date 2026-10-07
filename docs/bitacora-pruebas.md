# Bitácora de pruebas

Pruebas con Chromium **con JavaScript desactivado** (para comprobar que todo funciona solo con HTML5 y CSS3). Capturas en `docs/capturas/`.

## Responsividad (sin desborde horizontal)

| Vista | Móvil 375 px | Tablet 768 px | Escritorio 1280 px |
|---|---|---|---|
| index, login, registro | Correcto | Correcto | Correcto |
| dashboard, nuevo-reporte, consulta, detalle | Correcto (tablas apiladas) | Correcto | Correcto |
| atencion, admin, analisis, perfil | Correcto | Correcto | Correcto |

## Funcionamiento

| Prueba | Resultado |
|---|---|
| Todos los enlaces y anclas internas apuntan a archivos/ids existentes | Correcto (0 enlaces rotos) |
| Menú hamburguesa en móvil (abrir y cerrar) | Correcto |
| Formularios: campos vacíos o inválidos bloquean el envío y muestran el mensaje | Correcto |
| Registro válido → `login.html#registrado` con alerta; la contraseña no viaja en la URL | Correcto |
| Login válido → `dashboard.html` | Correcto |
| Nuevo reporte válido → `detalle.html#er-013` | Correcto |
| Consulta: filtros por estado y tipo (solos y combinados) | Correcto |
| Detalle: se muestra el reporte según el ancla (#er-001 … #er-013) | Correcto |
| Atención: modal «Registrar acción» y alertas de resultado | Correcto |
| Administración: pestañas, modal «Nuevo usuario», interruptores | Correcto |
| Estadísticas: barras, dona y descarga del CSV | Correcto |

## Calidad del HTML (revisión local)

Un solo `h1` por vista, `meta charset` y `viewport`, `alt` en imágenes, `label` en campos, ids únicos, sin estilos en línea y sin scripts. **Pendiente:** validar cada vista en validator.w3.org (requiere conexión) y anotar el resultado aquí.
