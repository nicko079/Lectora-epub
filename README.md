# Lectora

Lectora es una aplicación web progresiva (PWA) para teléfono y escritorio. En el celular se adapta a una sola columna, usa una barra de navegación inferior y abre el lector a pantalla completa.

## Archivos del proyecto

- `index.html`: interfaz y lector.
- `manifest.webmanifest`: nombre, color, iconos y modo de instalación.
- `sw.js`: caché de la app para volver a abrir su interfaz sin conexión después de la primera carga.
- `icon-192.png`, `icon-512.png`: iconos de la app.

## Instalar en el celular

La app debe estar publicada en una dirección HTTPS; abrir `index.html` como archivo local no permite instalarla como PWA.

- **Android:** abre la dirección HTTPS en Chrome y usa «Instalar aplicación» o «Añadir a pantalla de inicio» en el menú del navegador.
- **iPhone:** abre la dirección HTTPS en Safari, toca Compartir y elige «Añadir a pantalla de inicio».

## Funciones

- Inicio y biblioteca separados, con navegación inferior en pantallas pequeñas.
- Búsqueda y filtros por estado de lectura.
- Importación y guardado local de archivos PDF y EPUB mediante el almacenamiento del navegador; permanecen en este dispositivo después de cerrar la app.
- Muestra las portadas incluidas en EPUB y una miniatura de la primera página en PDF; si falta una portada, muestra una cubierta con el título.
- PDF en el visor del navegador.
- Lector EPUB inmersivo: oculta las barras de la app, muestra controles al tocar el centro y los oculta tras unos segundos. Permite cambiar de página tocando los bordes, elegir blanco, negro, sepia o pastel y ajustar el tamaño de letra.
- EPUB paginado con controles de tamaño de letra.
- Tema claro y oscuro.
- Caché de la interfaz para abrir la app después de la primera visita sin conexión.

## Requisitos y límites actuales

- Se necesita HTTPS para instalar la PWA y usar el service worker.
- epub.js se carga desde jsDelivr; PDF.js y JSZip, desde cdnjs. La primera carga necesita conexión a internet. Las portadas PDF pueden usar la primera página del archivo; si PDF.js no está disponible, queda una cubierta genérica.
- Los libros importados se guardan en el almacenamiento local del navegador, en este dispositivo. No se suben a un servidor ni se sincronizan entre dispositivos. Si borras los datos del navegador, se eliminan las copias locales.
- Es una PWA; todavía no se generó una aplicación nativa APK para Android o IPA para iPhone.
