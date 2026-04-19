# Natillera Familia Pulgarín (PWA)

Esta aplicación está preparada como **Progressive Web App (PWA)**, por lo que puede abrirse desde un link e instalarse como app en celular o escritorio.

## Requisitos para que se pueda instalar

- Servirse por **HTTPS** (o `http://localhost` en pruebas).
- Tener `manifest.webmanifest` válido.
- Tener `service worker` activo.
- Íconos PWA (`icon-192.png` y `icon-512.png`).

## Estructura clave

- `index.html`: UI principal y registro del service worker.
- `manifest.webmanifest`: metadata de instalación.
- `sw.js`: caché offline básico.
- `logo.jpeg`, `favicon.png`, `icon-192.png`, `icon-512.png`: branding e íconos.

## Publicar y compartir link (opciones rápidas)

### Opción A: GitHub Pages
1. Subir estos archivos a un repositorio.
2. Activar **Pages** en la rama principal.
3. Compartir el link HTTPS generado.

### Opción B: Netlify / Vercel
1. Arrastrar esta carpeta al panel de despliegue.
2. Obtener URL HTTPS automática.
3. Compartir ese link.

## Instalar en celular/escritorio

- Android/Chrome: menú `⋮` → **Instalar app** / **Agregar a pantalla principal**.
- iPhone/Safari: botón compartir → **Agregar a pantalla de inicio**.
- Escritorio Chrome/Edge: ícono de instalación en la barra de direcciones.

## Nota

Si actualizas archivos y no ves cambios, borra caché del sitio o incrementa la versión en `sw.js` (`CACHE_NAME`).
