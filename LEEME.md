# Página de links Fan Fest 2026

Reemplazo propio de Linktree: sin publicidad, sin límite de botones, con fotos, mapa y estadísticas.

## Archivos

- `index.html` es la página completa. Todo lo editable está en el bloque **CONFIGURACIÓN** (dentro del `<script>`, al final).
- `img/portada.mp4` (video del drone, sin sonido, en loop) y `img/portada.jpg` (foto que se ve mientras carga), `img/perfil.svg` (palmeras del logo), `img/logo-azul.svg` (logo en azul #15123f para la cabecera), `img/logo.svg` (versión blanca para fondos oscuros). Para cambiar una, reemplazá el archivo con el mismo nombre.

## Cómo editar

- Cambiar un link o texto: editá el valor entre comillas en CONFIGURACIÓN.
- WhatsApp: solo números con código de país, ej. `5492473123456` (sin +, sin 0, sin 15).
- Todo valor con `XXX` muestra un aviso amarillo "Falta link" en la página, para que nada salga incompleto.
- Agregar una disciplina: copiá una línea de `lista` y cambiá nombre, contacto (solo nombre) y número. Si `whatsapp` queda vacío, se muestra "Inscripciones próximamente" (así está Básquet).
- Redes: hoy solo Instagram (la única oficial). Se puede sumar una línea en `redes` (whatsapp, tiktok, mapa).
- Vista previa de Instagram: en `instagram.publicaciones` elegís qué posteos se ven y en qué orden. Para cada uno, guardá una captura vertical (4:5) en `img/ig/` y pegá el link del posteo (en Instagram: ··· > Copiar enlace). Si un posteo no tiene link, la imagen lleva al perfil, y si no tiene imagen se muestra un recuadro con el logo de Instagram. Se ven en una sola fila al final de la página (ideal: 5).
- Links directos con un desplegable abierto: `tupagina/#entradas` o `tupagina/#disciplinas` (sirve para historias del Social Run o flyers por deporte).

## Entradas: etapas y puntos de venta

- Para cambiar de etapa se edita solo `entradas.etapaActual`: `earlybird`, `preventa1`, `preventa2` o `preventa3`. El botón de entradas es un desplegable (como el de disciplinas). Al tocarlo muestra la compra online en WQRL Pass y los puntos presenciales agrupados por ciudad.
- `mostrarPrecios: true` muestra la tabla con todas las etapas: las anteriores aparecen tachadas y tenues, la actual destacada y las siguientes como "Próximamente".
- Los precios de las preventas se cargan recién el día del lanzamiento. Todo lo que esté escrito en el archivo se puede ver en el código de la página publicada, aunque no aparezca en pantalla.
- En `puntos`, `desde` indica en qué etapa aparece cada punto de venta. Si un punto no tiene `url`, se muestra como "Punto de venta a confirmar" (así están Wheelwright y Hughes).

## Publicación (GitHub + Netlify)

El código vive en el repo de GitHub `weignweb-dev/fanfest-links`. Netlify publica la página sola cada vez que el repo cambia.

Conectarlo a Netlify (una sola vez):
1. Entrar a https://app.netlify.com y crear una cuenta gratis con GitHub.
2. "Add new site" > "Import an existing project" > GitHub > elegir `fanfest-links`.
3. Dejar vacíos el comando de build y el directorio de publicación (el `netlify.toml` ya los define) y tocar "Deploy".
4. Nombre del sitio: `fanfest-info`, dirección https://fanfest-info.netlify.app
5. Poner ese link en la bio de @fanfestx.

Después de eso, cada cambio que se sube al repo queda publicado en uno o dos minutos. Un dominio propio (ej. fanfest.com.ar) es opcional y se paga aparte.

## Estadísticas (Umami Cloud, plan gratis)

La página ya tiene cada botón etiquetado (`Entradas online`, `Inscripción Social Run`, `Inscripción Tenis`, `Red: instagram`, `Ubicación Google Maps`, etc.).

1. Crear cuenta en https://cloud.umami.is (plan Hobby gratis).
2. "Add website" con el dominio de Netlify y copiar el **Website ID**.
3. En `index.html`, en el bloque ESTADÍSTICAS del `<head>`, pegar el ID y sacar `<!--` y `-->` alrededor de la línea `<script ...>`.
4. Subir el cambio al repo (Netlify lo publica solo). En Umami se ven visitas, de dónde vienen (Instagram, WhatsApp), dispositivos y clics por botón en "Events".

Tip: para medir cada pieza, usar el link con etiqueta, ej. `fanfestx.netlify.app/?utm_source=rrpp&utm_campaign=earlybird`. Umami lo muestra en "UTM".
