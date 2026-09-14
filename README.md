# InvePos — Web pública (política de privacidad)

Sitio estático, **HTML plano sin JavaScript**. Es el que se registra como URL de
política de privacidad en Google Play.

## Estructura

```
InvePos-privacy-policy/
├── index.html          → página de inicio (portada)
├── privacidad/
│   └── index.html      → POLÍTICA DE PRIVACIDAD  →  /privacidad
├── styles.css          → estilos compartidos
└── README.md
```

La URL que registrarás en Play Console es:

```
https://TU-DOMINIO/privacidad
```

## ANTES DE PUBLICAR: reemplaza los marcadores

Busca y reemplaza en `index.html` y en `privacidad/index.html`. Aparecen en rojo en la web
para que no se te escapen:

| Marcador | Qué poner |
|---|---|
| `[NOMBRE COMPLETO O RAZON SOCIAL DEL RESPONSABLE]` | Tu nombre legal o el de tu empresa, tal como aparecerá en Play |
| `[CORREO DE CONTACTO]` | Un correo real que revises. Play y los usuarios lo usarán |
| `[CIUDAD Y PAIS]` | Tu ciudad y país |
| `[FECHA DE ENTRADA EN VIGENCIA]` | Fecha en que publicas la política, ej. `12 de septiembre de 2026` |
| `[FECHA DE ULTIMA ACTUALIZACION]` | La misma fecha la primera vez |

Comprobación rápida de que no quedó ninguno:

```powershell
Select-String -Path .\index.html, .\privacidad\index.html -Pattern "\["
```

## Publicar en GitHub Pages

1. Crea un repositorio **público** en <https://github.com/new> llamado
   `InvePos-privacy-policy` (sin README, sin `.gitignore` y sin licencia).
2. Desde esta carpeta, conecta y sube:

   ```powershell
   git remote add origin https://github.com/TU-USUARIO/InvePos-privacy-policy.git
   git push -u origin main
   ```

3. En el repositorio: **Settings → Pages** → *Source*: **Deploy from a branch** →
   rama `main`, carpeta `/ (root)` → **Save**.
4. En 1-2 minutos quedará publicado en
   `https://TU-USUARIO.github.io/InvePos-privacy-policy/` y la política en
   `https://TU-USUARIO.github.io/InvePos-privacy-policy/privacidad/`.
5. Cuando tengas dominio propio, añádelo en **Settings → Pages → Custom domain** y
   cambia la URL en Play Console.

> Cada `git push` a `main` republica el sitio automáticamente.

## Coherencia con el formulario "Seguridad de los datos" de Play

Play compara lo que declaras con lo que dice tu política. Si se contradicen, te rechazan.
Esta política fue escrita a partir del código real de InvePos. Respuestas coherentes:

| Pregunta de Play | Respuesta coherente |
|---|---|
| ¿La app recopila o comparte datos del usuario? | **No.** No hay servidor, ni cuentas, ni analítica |
| ¿Los datos se cifran en tránsito? | No aplica: la app no transmite datos a nosotros |
| ¿El usuario puede solicitar el borrado? | Sí: se borra en la app o desinstalando |
| Datos de clientes que registra el comerciante | Los controla el comerciante en su dispositivo |

**Si activas alguna vez** sincronización en la nube, analítica, cuentas de usuario o
publicidad, **esta política deja de ser correcta** y hay que actualizarla antes de publicar
esa versión.

## Qué NO tiene la web (a propósito)

- **Cero JavaScript.** Un revisor de Play o un usuario con JS bloqueado debe verla igual.
- **Cero fuentes ni recursos externos.** No hay llamadas a Google Fonts ni CDN.
- **Cero cookies**, así que no hace falta banner de cookies.
