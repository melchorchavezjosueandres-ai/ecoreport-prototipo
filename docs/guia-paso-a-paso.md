# Guía paso a paso (entrega: miércoles 7 de octubre de 2026, 1:00 pm)

Tiempo estimado: 3 a 4 horas entre los cuatro.

## Parte A · Preparar el proyecto en Visual Studio Code (todos, 15 min)
1. Descomprime `ecoreport-prototipo.zip` en una carpeta, por ejemplo en el Escritorio.
2. Abre Visual Studio Code → **File → Open Folder** → elige la carpeta `ecoreport`.
3. Instala la extensión **Live Server** (Ritwick Dey). Clic derecho en `index.html` → **Open with Live Server**.
4. Recorre el flujo: Inicio → Crear cuenta → Iniciar sesión → Dashboard → Nuevo reporte → Mis reportes → Detalle → Mi perfil. Luego entra como cada perfil desde `login.html`.
5. Lee tu parte del código (tabla del Paso 3 de la Parte B) y haz **al menos un cambio propio** (un texto, un color en `:root`), para poder explicarlo.

## Parte B · GitHub (control de versiones)

### Paso 1 · Reunión de 15 minutos
- [ ] Asignar los 4 roles y anotarlos en el README (sección 1).
- [ ] Crear el grupo de chat y una reunión diaria de 10 minutos.

### Paso 2 · Repositorio (Rol 1)
- [ ] GitHub → **New repository** → nombre `ecoreport`, público, sin README ni `.gitignore`.
- [ ] Settings → Collaborators: agregar a los otros 3 integrantes y al docente.
- [ ] Projects → New → Board con las columnas Por hacer, En proceso, En revisión y Terminado; cargar las tareas de `docs/tablero-kanban.md`.
- [ ] Subir la base a `main` (dentro de la carpeta del proyecto):
  ```bash
  git init -b main
  git add README.md .gitignore docs/
  git commit -m "Agrega README, documentación y mapa de navegación"
  git remote add origin https://github.com/USUARIO/ecoreport.git
  git push -u origin main
  ```

### Paso 3 · Cada integrante sube lo suyo en su rama (con su cuenta)
```bash
git clone https://github.com/USUARIO/ecoreport.git
cd ecoreport
git checkout -b feature/NOMBRE-DE-RAMA
# copia aquí SOLO los archivos de tu rol
```

| Rol | Rama | Archivos |
|---|---|---|
| 2 · Diseñador UX/UI | `feature/estilos` | `css/styles.css`, `img/`, `docs/guia-estilo.html`, `docs/wireframes.html` |
| 3 · Front-End 1 (acceso) | `feature/acceso` | `index.html`, `login.html`, `registro.html` |
| 4 · Front-End 2 (módulos) | `feature/modulos` | `dashboard.html`, `nuevo-reporte.html`, `consulta.html`, `detalle.html`, `atencion.html`, `admin.html`, `analisis.html`, `perfil.html`, `docs/reportes.csv`, `docs/capturas/` |
| 1 · Coordinador | `main` | README, resto de `docs/` y la integración final |

Haz varios commits pequeños con mensajes descriptivos, por ejemplo (Rol 3):
```bash
git add index.html
git commit -m "Agrega la vista de inicio con hero y secciones"
git add login.html
git commit -m "Agrega login con validación HTML5 y accesos por perfil"
git add registro.html
git commit -m "Agrega registro con validación nativa de campos"
git push -u origin feature/acceso
```
Después abre el *Pull Request* en GitHub, pide la revisión a otra persona y mueve la tarjeta a «En revisión».

Nota: en la actividad original el Rol 3 también aparece con `js/validaciones.js`. En esta versión no hay JavaScript: la validación está en los atributos HTML5 de los formularios (`required`, `pattern`, `type`), así que sus commits son en los `.html`.

### Paso 4 · Revisión cruzada y fusión
- [ ] Cada PR lo revisa y aprueba otra persona.
- [ ] Orden de fusión: 1) `feature/estilos`, 2) `feature/acceso`, 3) `feature/modulos`.

### Paso 5 · Probar lo integrado (todos, 20 min)
- [ ] `git checkout main && git pull` y recorrer el flujo completo con Live Server.
- [ ] F12 → modo dispositivo (móvil, tablet, escritorio) y navegación con Tab.

### Paso 6 · Validador de W3C (Roles 3 y 4, 15 min)
- [ ] Ir a https://validator.w3.org/#validate_by_upload y subir **cada** `.html` (11 archivos). Los avisos (warnings) no cuentan; los errores sí. Un commit por corrección.
- [ ] Anotar el resultado en `docs/bitacora-pruebas.md`.

### Paso 7 · Publicar (Rol 1, 5 min)
- [ ] Settings → Pages → *Deploy from branch* → `main` / `/ (root)` → Save.
- [ ] A los 2 minutos copia la URL (`https://USUARIO.github.io/ecoreport/`) y pégala en el README.

## Parte C · Qué entregar en Teams

El Word no menciona la plataforma, pero la tarea «AW26 ACT9 PROTOTIPO FRAMEWORK COLABORATIVA» vence el 7 de octubre a las 13:00 y permite varios envíos. Estos son los entregables de la sección 9 del Word y cómo subirlos:

| # | Entregable del Word | Qué subes a Teams |
|---|---|---|
| 1 | Repositorio en GitHub con commits de todos | El **enlace** del repositorio (va en el documento de entrega y en el comentario de la tarea) |
| 2 | Prototipo en ejecución | El **enlace de GitHub Pages** y, además, `ecoreport-prototipo.zip` por si el enlace falla |
| 3 | README.md | Ya va dentro del ZIP y del repositorio; también como `EcoReport_Documentacion_Entrega.docx` |
| 4 | Mapa de navegación (PDF o imagen) | Va en `docs/` del ZIP y en el documento de entrega (sección 5) |
| 5 | Matriz de trazabilidad | Documento de entrega (sección 6) y `docs/matriz-trazabilidad.md` |
| 6 | Capturas en móvil, tablet y escritorio + bitácora | Documento de entrega (secciones 7 y 8) y `docs/capturas/` |
| 7 | Demostración 10 + 5 min | Se presenta en la fecha acordada (no se sube); ensayen con `docs/guion-demostracion.md` |
| 8 | Formato de coevaluación individual y confidencial | `EcoReport_Coevaluacion.docx` llenado por **cada integrante**, entregado por separado |

Pasos en Teams:
1. Abre Teams → **Equipos** → tu grupo de Aplicaciones Web → pestaña **Tareas** (o *Assignments*).
2. Abre «AW26 ACT9 PROTOTIPO FRAMEWORK COLABORATIVA» y revisa las instrucciones.
3. En **Mi trabajo** pulsa **+ Agregar trabajo** → **Cargar del dispositivo**, y adjunta: `ecoreport-prototipo.zip` y `EcoReport_Documentacion_Entrega.docx`.
4. Escribe en el comentario: el enlace del repositorio y el de GitHub Pages.
5. Pulsa **Entregar** y confirma que el estado cambie a «Entregado». Si necesitas corregir algo, usa **Deshacer entrega**, modifica y vuelve a entregar antes de la 1:00 pm.
6. Cada integrante entrega **su propia coevaluación**. Si Teams solo permite una entrega por equipo, mándasela al docente por mensaje privado, porque el Word pide que sea confidencial y por separado.
7. Verifica con la lista de `docs/lista-verificacion.md` antes de las 12:30.

## Parte D · Ensayo (todos, 30 min)
Sigan `docs/guion-demostracion.md` cronometrando: 10 minutos más 5 de preguntas, y todos participan.
