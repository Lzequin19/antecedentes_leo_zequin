# Bitácora — antecedentes_leo_zequin

Memoria viva del proyecto. Entradas más recientes arriba.
La destila el cerebro con `/destilar`.

> Nota: las dos primeras entradas (30 jun – 1 jul 2026) son un **backfill reconstruido
> desde el historial de git**, no capturadas en vivo. De acá en adelante se anotan por sesión.

---

## 2026-11-17 — Firma de correo minimalista (Gmail + Outlook)

**Qué se hizo**
- Nueva firma de correo personal para lzequin@gmail.com y lzequin@outlook.com, que reemplaza a la vieja (nombre, título, celular, "Más información...").
- Página `firma/firma-email.html` con las dos versiones (cambia solo el mail), botón "Copiar firma" (HTML enriquecido con fallback por selección) y los pasos para pegarla en cada cliente.
- Contenido final, línea por línea: Leonardo Zequin / Magíster en Docencia Universitaria / Ingeniero Industrial / +54 9 342 537-7879 · mail / LinkedIn · Antecedentes · Somos Zeta.
- Revisada renderizada en Chrome (con `server.js`). No se probó pegándola en Gmail ni en Outlook.

**Decisiones**
- Minimalista y solo con texto, sin íconos ni imágenes: las imágenes en firmas se bloquean o llegan como adjunto, y en Gmail tienen que estar alojadas en la web.
- Compatible con clientes de correo: tablas anidadas, estilos en línea, Arial. Paleta de la página: barra izquierda violeta `#7030a0`, separadores dorados `#d9a400`.
- Teléfono en formato internacional (`+54 9 342 537-7879`): con +54 se saca el 0 y el 15 y se agrega el 9. El número abre WhatsApp (`wa.me/5493425377879`).
- El link "Antecedentes" apunta a GitHub Pages: `https://lzequin19.github.io/antecedentes_leo_zequin/` (verificado online, 200).
- Ajustes de Leo: cada título en su propia línea, primero el Magíster y después Ingeniero Industrial, sin espacio extra antes de la línea de contacto (`padding:2px`). El primer intento de sacar el espacio lo pisó un cambio externo en el archivo; al reaplicarlo quedó guardado.
- Ojo: el WhatsApp de la página (`build.js`, 3496 460513) no coincide con el celular de la firma (342 537-7879).

**Pendientes / próximo paso**
- Leo: pegar la firma en Gmail y en Outlook y fijarla como predeterminada.
- Decidir si `firma/` se commitea: si se sube, queda publicada en GitHub Pages junto a la página.
- Revisar si el WhatsApp de la página tiene que pasar a ser el 342 537-7879.

**Archivos / áreas tocadas:** `firma/firma-email.html` (nuevo, sin commitear).

## 2026-07-19 — Sesión sin actividad de desarrollo

**Qué se hizo**
- No hubo trabajo de desarrollo sobre el proyecto en esta sesión (`/capturar`
  masivo sobre `D:\zeta\proyectos`).
- Repo git en `main`, último commit `8b6fa51` (botón de exportación a PDF). El
  único cambio sin trackear es `bitacora.md` (este archivo). No usa `node_modules`.

**Decisiones**
- —

**Pendientes / próximo paso**
- Sin pendientes nuevos.

**Archivos / áreas tocadas:** — (solo esta bitácora).

## 2026-07-01 — Botón de exportación a PDF

**Qué se hizo**
- Se agregó un botón para exportar la página de antecedentes a PDF.
- El PDF sale en **modo claro** y **sin menús ni redes de contacto** (versión limpia para imprimir/compartir formalmente).

**Decisiones**
- El export prioriza una salida sobria para instituciones: se ocultan navegación y bloque de redes.

**Pendientes / próximo paso**
- —

**Archivos / áreas tocadas:** `index.html` (commit 8b6fa51).

---

## 2026-06-30 — Scaffolding del generador + bundle tema oscuro

**Qué se hizo**
- Se armó el generador estático propio del proyecto: `build.js` (con `CONFIG`) + `clean.json` como fuente de datos, `server.js` para previsualizar y `README.md`.
- Se incorporaron los assets base: `BD_CV_Leonardo_Zequin.xlsx` (fuente de datos), `Foto Leo Zequin.jpeg` (embebida en base64 en el HTML) y la paleta cromática de Somos Zeta.
- Primera versión editorial clara ("v2") con foto embebida, redes de contacto y README.
- Se reemplazó `index.html` por la **versión bundle** con tema oscuro violeta + dorado y portada con constelaciones animadas (gran reducción de tamaño del HTML: -732/+162 líneas).
- Se agregó `.nojekyll` para que GitHub Pages sirva el sitio como estático puro.

**Decisiones**
- El contenido **nunca se edita a mano en el HTML**: se edita la fuente (`clean.json` / xlsx) y se regenera con `node build.js`.
- HTML **autónomo** con foto en base64 → un solo archivo publicable por GitHub Pages.
- Identidad co-branded con Somos Zeta: violeta institucional + acento dorado.

**Pendientes / próximo paso**
- —

**Archivos / áreas tocadas:** `build.js`, `clean.json`, `server.js`, `index.html`, `README.md`, `.nojekyll`, `.gitignore`, `.claude/launch.json`, assets (foto, xlsx, paleta) — commits f35cffc, d6fdd39, 1923a6d.
