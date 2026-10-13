# Pelota de Reflejos — SEXY FITNESS

Landing comercial en HTML, CSS y JavaScript, sin frameworks ni compilación. Precio: **$300 MXN con envío gratis por las próximas 24 horas**. Pedidos por WhatsApp: **+52 56 1605 7355**.

## Publicar en GitHub Pages

1. Descomprime `pelota-reflejos-github-actualizado.zip`.
2. Crea o abre tu repositorio de GitHub. Sube **el contenido de la carpeta `pelota-reflejos`**: `index.html`, `README.md` y `assets/`. `index.html` debe quedar en la raíz del repositorio.
3. En **Settings → Pages**, selecciona **Deploy from a branch**, rama `main`, carpeta **/(root)** y guarda.
4. GitHub mostrará la dirección de tu página cuando termine la publicación. Abre esa dirección para comprobarla.

## Imágenes y banner

| Archivo | Medidas | Uso |
|---|---|---|
| `assets/banner-desktop.webp` | 1920 × 800 px | Banner en pantallas mayores de 760 px |
| `assets/banner-mobile.webp` | 1080 × 1350 px | Banner en pantallas de hasta 760 px |
| `assets/producto-amarillo.webp` | Actual: 980 × 470 px | Producto y catálogo |
| `assets/boxeador.webp` | Actual: 1122 × 495 px | Hero provisional y entrenamiento |
| `assets/entrenamiento.mp4` | Variable | Video opcional con controles |
| `assets/og-image.webp` | 1200 × 630 px | Vista al compartir |

Los banners y el video **no se incluyen porque aún están pendientes**. No crees archivos vacíos: sube los archivos finales con sus nombres exactos. Los dos banners se seleccionan mediante `<picture>`, se muestran completos sin recorte y se activan automáticamente cuando cargan. Si falta el banner del dispositivo, se conserva el hero provisional. Mantén el texto importante dentro de las dimensiones indicadas.

El video sustituye la fotografía de entrenamiento únicamente después de cargar sus metadatos. Se reproduce por decisión del visitante, no automáticamente. Usa MP4 compatible con los navegadores habituales (H.264 y audio AAC si hay audio). Si no existe o falla, continúa la fotografía. Para comprobar la detección del video en tu computadora, usa un servidor local (`python3 -m http.server 8000` desde la carpeta) y abre `http://localhost:8000`. Al abrir directamente `index.html`, la detección mediante fetch puede estar bloqueada; el resto funciona y mantiene la fotografía.

Las imágenes actuales son recortes optimizados en WebP de tus pósteres, sin rediseñar el producto. Los pósteres completos se conservan como `poster-accion.webp` y `poster-producto.webp`.

## WhatsApp

Busca en el script de `index.html`:

```js
const WHATSAPP_NUMBER = '525616057355';
const PURCHASE_MESSAGE = 'Hola, me interesa comprar una pelota de reflejos para entrenamiento de boxeo. ¿Me puedes compartir precio y disponibilidad?';
```

Usa solo dígitos con código de país. Los botones abren WhatsApp con el mensaje precargado: el visitante decide enviarlo. No se envían mensajes automáticamente. Dejar el número vacío activa un diálogo para copiar la consulta, sin enlaces falsos. No hay cobro ni confirmación automática; disponibilidad y condiciones de la promoción se acuerdan por WhatsApp.

## Redes sociales

En `SOCIAL_LINKS`, añade tus enlaces verificados:

```js
const SOCIAL_LINKS = [
  { name: 'Instagram', url: 'https://www.instagram.com/TU_CUENTA/' },
  { name: 'Facebook', url: 'https://www.facebook.com/TU_PAGINA/' }
];
```

Mientras la lista esté vacía, no se muestran enlaces de redes.

## Compartir en WhatsApp y Facebook

Una vez publicado en GitHub Pages, reemplaza en el `<head>` la dirección de `og:url` por la URL pública de tu página y la de `og:image` por la URL absoluta de `assets/og-image.webp`. Las direcciones actuales corresponden a la vista privada de revisión, que no permite a los rastreadores acceder a la imagen. No basta con usar una ruta relativa para una vista compartida fiable. No se fija canonical a una dirección provisional.

## Modificar contenido

Todo el HTML, CSS y JavaScript principal está en `index.html`. Cambia textos, precio y fotografías allí. Para confirmar otro modelo, añade una tarjeta real y su fotografía; el espacio actual de otras versiones no declara inventario. No se incluyen testimonios, descuentos ni garantías inventadas.

## Accesibilidad y funcionamiento

Menú móvil con Escape, acordeones operables por teclado, enlace para saltar al contenido, foco visible, animaciones con soporte de movimiento reducido y barra móvil con espacio reservado en el pie. Las respuestas permanecen visibles si no se ejecuta JavaScript. Sin JavaScript, los botones conducen a la sección de contacto donde aparece el número.

## Contador de envío gratis

El contador comienza en 24 horas para cada navegador. Conserva el tiempo al recargar con almacenamiento local y se reinicia automáticamente al completar cada ciclo. No requiere servidor.
