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

## Modo en línea con Firebase 🔥

La app ya está preparada para sincronizar datos en tiempo real con **Cloud Firestore**.

### 1) Crear proyecto Firebase

1. Entra a Firebase Console y crea un proyecto.
2. Agrega una **Web App**.
3. Copia la configuración (`apiKey`, `authDomain`, `projectId`, etc).

### 2) Habilitar Firestore

1. En Firebase, abre **Firestore Database**.
2. Crea la base en modo producción o pruebas.
3. Crea reglas según tu seguridad (en desarrollo puedes permitir lectura/escritura temporalmente).

### 3) Pegar configuración en la app

En `index.html`, busca el objeto `FIREBASE_CONFIG` y reemplaza:

- `REEMPLAZAR_API_KEY`
- `REEMPLAZAR_AUTH_DOMAIN`
- `REEMPLAZAR_PROJECT_ID`
- `REEMPLAZAR_STORAGE_BUCKET`
- `REEMPLAZAR_MESSAGING_SENDER_ID`
- `REEMPLAZAR_APP_ID`

### 4) Estructura de datos usada en Firestore

Colección: `natillera`  
Documento: `coreData`

Campos:
- `users`: arreglo de usuarios
- `loans`: arreglo de préstamos
- `requests`: arreglo de solicitudes
- `updatedAt`: fecha de última actualización

### 5) Comportamiento de sincronización

- Si Firebase está configurado correctamente: usa Firestore (modo en línea).
- Si falta configuración o falla conexión: la app sigue en local (fallback).
- Al activarse Firebase, los datos locales iniciales se suben a Firestore si el documento no existe.

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
