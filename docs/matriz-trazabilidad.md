# Matriz de trazabilidad (requerimientos → vistas)

Prototipo con **HTML5 + CSS3** (sin JavaScript, sin Bootstrap). Las interacciones se resuelven con atributos HTML5 (`required`, `pattern`, `type`, `minlength`) y selectores CSS (`:target`, `:checked`, `:has()`, `:user-invalid`).

| Requerimiento | Vista (archivo) | Componentes HTML5 / CSS3 | Evidencia de verificación |
|---|---|---|---|
| **RF-01** Registrar usuarios | `registro.html` | Formulario con `fieldset`/`legend`, `label`, validación nativa (`required`, `pattern`, `type="email"`) y mensajes con `:user-invalid` | Con campos vacíos o inválidos el navegador bloquea el envío; con datos válidos pasa a `login.html#registrado` |
| **RF-02** Iniciar sesión | `login.html` → `dashboard.html` (y perfiles) | Formulario, alerta con `:target`, tarjetas de acceso por perfil | El formulario válido lleva al dashboard; los botones «Entrar como…» llevan a cada panel |
| **RF-03** Registrar reportes ambientales | `nuevo-reporte.html` | Formulario en `fieldset`, `select`, `textarea`, radios de urgencia | Enviar con datos válidos abre `detalle.html#er-013` |
| **RF-04** Agregar ubicación | `nuevo-reporte.html` | Colonia (`select`), referencia y coordenadas (`pattern`) | El detalle muestra colonia, referencia y coordenadas |
| **RF-05** Adjuntar evidencia | `nuevo-reporte.html`, `detalle.html` | `input type="file" accept="image/*" multiple`; tarjetas de evidencia | El detalle lista los archivos adjuntos |
| **RF-06** Consultar reportes | `consulta.html`, `dashboard.html` | Tabla responsiva (se apila en móvil) y filtros por estado y tipo con radios + `:has()` | Cada filtro oculta las filas que no coinciden |
| **RF-07** Consultar el estado de un reporte | `detalle.html`, `dashboard.html` | Insignias de estado, línea de tiempo (`ol`), contadores | Cada reporte muestra su historial con fecha y responsable |
| **RF-08** Administrar reportes y estados | `atencion.html`, `admin.html` | Tarjetas de acción, modal con `:target`, pestañas con radios, interruptores | Los botones muestran el resultado simulado y los modales abren y cierran |
| Cuenta propia (todos los perfiles) | `perfil.html` | Dos formularios con validación nativa | Datos y contraseña validan antes de enviar |
| Perfil Supervisor / Analista | `analisis.html` | Indicadores, barras y dona hechas con CSS, descarga CSV con `download` | Las barras y la dona reflejan los 12 reportes de ejemplo |
| **RNF-01** Seguridad | `login.html`, `registro.html` | Campos de contraseña `type="password"` que no se envían en la URL | En un prototipo sin backend la autenticación real queda pendiente |
| **RNF-02** Usabilidad | Todas | Etiquetas claras, mensajes de error con instrucciones, flujo corto | Un usuario nuevo registra un reporte sin capacitación |
| **RNF-03** Responsividad | Todas | Mobile-first, `grid`/`flex`, tablas apiladas, menú hamburguesa con `checkbox` | Capturas en móvil, tablet y escritorio (`docs/capturas/`) |
| **RNF-04** Rendimiento | Todas | Un solo CSS, sin scripts ni librerías, íconos SVG | Carga inmediata |
| **RNF-05** Disponibilidad | Todas | Sitio estático, funciona sin servidor ni conexión (salvo las fuentes, con respaldo) | Se abre desde el archivo local o GitHub Pages |
