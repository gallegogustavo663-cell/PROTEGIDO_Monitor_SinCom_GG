# Monitor de Equipos Sin Comunicación

Panel de monitoreo GPS protegido con contraseña, para seguimiento de equipos sin comunicación.

## Contenido de esta carpeta

- `PROTEGIDO_Monitor_SinCom_GG.html` — Dashboard principal (protegido con contraseña)
- `manifiesto.json` — Manifiesto PWA (permite instalar como app)
- `sw.js` — Service worker (cache offline)
- `iconos/` — Carpeta para los íconos de la app (192x192 y 512x512 px)

## Cómo subir a GitHub

### Opción 1 — Interfaz web (más fácil)
1. Entra a tu repositorio `panel-de-operaciones` en GitHub
2. Click en **Agregar archivo → Cargar archivos**
3. Arrastra TODOS los archivos de esta carpeta (incluyendo la subcarpeta `iconos`)
4. Escribe un mensaje de commit, ej: "Agregar Monitor Sin Comunicación"
5. Click en **Confirmar cambios (Commit changes)**

### Opción 2 — Terminal / Git
```bash
git clone https://github.com/TU-USUARIO/panel-de-operaciones.git
cd panel-de-operaciones
cp -r /ruta/monitor-package/* .
git add .
git commit -m "Agregar Monitor Sin Comunicación"
git push
```

## Después de subir

Tu dashboard quedará disponible en:
```
https://TU-USUARIO.github.io/panel-de-operaciones/PROTEGIDO_Monitor_SinCom_GG.html
```

## Novedad: Ver y Descargar desde "Archivos recientes"

Se agregó un bloque de código adicional (al final del HTML, sin tocar el
código original ofuscado) que hace lo siguiente:

- Cuando cargas un Excel, ahora se guarda **el snapshot completo de los
  datos** (no solo el nombre) en el navegador, para los últimos 5 archivos.
- En la pantalla de "Archivos recientes" cada archivo ahora tiene dos
  botones:
  - **👁️ Ver** — vuelve a mostrar la tabla completa, KPIs y gráficos de
    ese archivo, sin necesidad de volver a subir el Excel.
  - **⬇️ CSV** — reabre el archivo y descarga automáticamente su CSV.
  - **📄 PDF** — reabre el archivo y descarga automáticamente el reporte
    PDF completo (con KPIs y tabla), igual que el botón "Exportar PDF".
- Esto se guarda en el `localStorage` del navegador — es decir, funciona
  mientras uses el **mismo navegador y el mismo computador**. Si cambias
  de navegador, de computador, o borras el caché/datos del sitio, el
  historial se pierde (es una limitación de cómo funciona el
  almacenamiento local del navegador, no de este dashboard en sí).

## Importante

- Los archivos `manifiesto.json` y `sw.js` incluidos aquí son NUEVOS, creados solo para
  este dashboard. Si ya tienes un `manifiesto.json` y `sw.js` en tu repo (como se ve en
  tu captura de "panel de operaciones"), NO los reemplaces directamente — hay que fusionar
  el contenido para no perder las referencias a tus otros dashboards
  (OPS_Dashboard_GG_v5_secure.html, PARCHE_HTML.html, etc).
- Si me compartes el contenido actual de tu `manifiesto.json` y `sw.js`, te devuelvo
  las versiones fusionadas listas para reemplazar directamente.
- Carpeta `iconos/`: agrega ahí tus íconos (192x192 y 512x512 px) o reutiliza los que
  ya tienes en el repo si el nombre coincide.
