# kmer-labs.com.ar

Sitio de K-mer Labs. HTML y CSS a mano, sin frameworks ni build: lo que está en
esta carpeta es lo que se publica. La base de código es la de
[alangomezforero.com.ar](https://alangomezforero.com.ar) (tokens en `:root`, tema
claro/oscuro, menú móvil); la identidad sale de la tarjeta de presentación.

## Identidad

| Pieza        | Valor                                                                  |
| ------------ | ---------------------------------------------------------------------- |
| Rojo         | `#8E1322` (logo, botón principal, fondo de contacto)                   |
| Tinta        | `#231F20` (texto y eje del logo)                                       |
| Títulos      | Source Serif 4, en lugar de Sitka Heading                              |
| Texto        | Barlow, en lugar de Bahnschrift                                        |
| Logo         | `img/logo.svg`, reconstruido en vector desde `Tarjeta de presentacion.pdf` |

Sitka Heading y Bahnschrift vienen con Windows y no tienen licencia para web; las
dos reemplazantes son libres (OFL) y se sirven desde `fonts/`, sin Google Fonts.

## Archivos

```
index.html               la página
styles.css               toda la hoja de estilos
privacidad.html          política de privacidad (Ley 25.326): describe lo que el sitio hace de verdad
404.html                 GitHub Pages la sirve para cualquier ruta inexistente
favicon.svg              logo con trazos gruesos, para 16-32 px
apple-touch-icon.png     180×180, también es el logo del JSON-LD
og.png                   1200×630, la vista previa al compartir el enlace
alan-gomez-forero.vcf    el botón «Guardá mi contacto»
img/logo.svg             el logo con las proporciones exactas de la tarjeta
fonts/                   Source Serif 4 y Barlow, sólo el subconjunto latino
CNAME, robots.txt, sitemap.xml
```

## Verlo en local

```sh
python3 -m http.server 8765
```

y abrir <http://127.0.0.1:8765>. Con `file://` las tipografías no cargan en Firefox.

## Publicar en GitHub Pages

1. Repositorio nuevo con el contenido de esta carpeta en `main`.
2. *Settings → Pages*: rama `main`, carpeta `/ (root)`. El dominio ya está en `CNAME`.
3. Cuando GitHub emita el certificado, tildar *Enforce HTTPS*.

El DNS ya está hecho en Cloudflare: los A y AAAA de GitHub Pages, `www` →
`forero94.github.io` y el TXT de verificación del dominio en GitHub (no borrarlo).
Todo en gris («DNS only»): con la nube naranja GitHub no puede emitir ni renovar
el certificado. El correo (`alan@` por Email Routing, envío por Brevo) usa el mismo
DNS; cualquier servicio nuevo que mande mails como `@kmer-labs.com.ar` tiene que
autenticarse ahí antes, o cae en spam.

GitHub Pages deja que el navegador guarde CSS y JS 10 minutos: al cambiar
`styles.css`, subir el `?v=` en `index.html` y `404.html`.
