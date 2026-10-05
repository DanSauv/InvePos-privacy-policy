# InvePos — Web pública

Sitio estático del proyecto **InvePos** (gestión de inventario, ventas y facturación para
pequeños negocios). Es el sitio que se registra como **URL de política de privacidad** en
Google Play y en la pantalla de consentimiento de Google Cloud.

**Sin JavaScript de terceros, sin cookies, sin CDN y sin fuentes externas.** Solo HTML, un
archivo CSS y dos imágenes propias.

## Estructura

```
InvePos-privacy-policy/
├── index.html                    → portada
├── 404.html                      → página no encontrada
├── politica-de-privacidad/
│   └── index.html                → POLÍTICA DE PRIVACIDAD
├── privacidad/
│   └── index.html                → puente: redirige a /politica-de-privacidad/
├── terminos/index.html           → Términos y Condiciones
├── soporte/index.html            → Soporte y preguntas frecuentes
├── eliminar-datos/index.html     → Eliminación de datos
├── assets/
│   ├── estilos.css               → estilos compartidos
│   ├── icono.png                 → logo / favicon
│   └── mascota.png               → mascota de la portada
├── robots.txt
├── sitemap.xml
├── CNAME.ejemplo                 → plantilla para cuando se conecte el dominio propio
└── README.md
```

## URLs

| Página | Dirección |
|---|---|
| Portada | `/` |
| Política de privacidad | `/politica-de-privacidad/` |
| Términos y condiciones | `/terminos/` |
| Soporte | `/soporte/` |
| Eliminación de datos | `/eliminar-datos/` |

**Todas las rutas internas son relativas**, así que el sitio funciona igual en GitHub Pages
(`dansauv.github.io/InvePos-privacy-policy/`) y en el dominio propio, que es el oficial:

```
https://invepos.com/                      → el sitio de InvePos
https://invepos.com/politica-de-privacidad/   → la política que se registra en Play
```

> `/privacidad/` se conserva como **puente** (redirección) para no romper enlaces ya
> registrados en Google Cloud o Play Console. Cuando ambas URLs estén actualizadas, ese
> puente puede quedarse: no molesta.

## Cómo actualizar el sitio

1. Editar los archivos.
2. `git add -A && git commit -m "..." && git push`
3. GitHub Pages republica solo, en 1-2 minutos.

> **Dominio oficial: `invepos.com`** (en Cloudflare). El archivo `CNAME.ejemplo` queda solo
> como referencia del antiguo plan de GitHub Pages; el sitio se publica en Cloudflare.

## Contenido de la versión 1.1 (5 de octubre de 2026)

Esta versión refleja los cambios de la app: **respaldo en Google Drive**.

- Sección nueva en la política: qué permiso pide la app (`drive.file`), qué hace con la
  cuenta de Google, dónde se guardan las copias y cómo revocar el acceso.
- Cláusula de **Uso Limitado** exigida por la Política de datos de usuario de los servicios
  API de Google.
- Se corrigió la afirmación anterior *"no creamos cuentas ni pedimos inicio de sesión"*, que
  dejó de ser cierta al añadirse la conexión opcional con Google.
- Páginas nuevas: Términos y Condiciones, Soporte (FAQ) y Eliminación de datos.
- La política pasó de `/privacidad/` a `/politica-de-privacidad/`.

## Pendientes del lado de Google / Play

Cuando el sitio esté publicado con el dominio definitivo, actualizar:

- **Google Cloud → Información de la marca**: URL de la política de privacidad.
- **Google Cloud → Información de la marca → Dominios autorizados**: añadir el dominio
  (debe verificarse la propiedad en Search Console; `github.io` no es verificable).
- **Play Console**: URL de la política de privacidad.
- **Play Console → Seguridad de los datos**: revisar la declaración. La app no envía datos a
  servidores de SauvDev, pero **sí transmite el respaldo a la cuenta de Google del propio
  usuario**; conviene declararlo de forma coherente con la sección 5 de la política.

## Registro de cambios

| Fecha | Cambio |
|---|---|
| 2026-10-05 | v1.1: respaldo en Google Drive, 3 páginas nuevas, política en `/politica-de-privacidad/`, dominio propio `invepos.com` |
| 2026-09-14 | Versión inicial (portada + política de privacidad) |