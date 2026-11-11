# TrackViewer (web / PWA)

Visor de rutas GPX y TCX sobre Google Maps. Funciona en Safari de iPhone y se
instala en la pantalla de inicio. No necesita Mac ni cuenta de Apple Developer.

Incluye: **ubicación en vivo** (punto azul, botón para centrar/seguir y aviso de «en la ruta» / «fuera de ruta»), carga de GPX/TCX, ruta con inicio/fin, distancia, desnivel +/−, tiempo,
perfil de elevación interactivo (al arrastrar el dedo se mueve un marcador por el mapa)
y cambio entre mapa, satélite y terreno.

## 1. API key de Google Maps
1. Google Cloud Console → crea un proyecto y activa la facturación (exige tarjeta).
2. Habilita **Maps JavaScript API**.
3. Credenciales → Crear clave de API → en "Restricciones de aplicación" elige
   *Sitios web (referentes HTTP)* y pon tu dominio, p. ej. `https://tuusuario.github.io/*`.
   Así, aunque la clave sea visible en el navegador, solo funciona desde tu web.

## 2. Publicar (necesita HTTPS; todas estas opciones son gratis)
- **GitHub Pages**: sube la carpeta a un repo → Settings → Pages → rama `main`, carpeta `/ (root)`.
- **Netlify / Cloudflare Pages**: arrastra la carpeta a su panel ("Deploy manually").

## 3. Instalar en el iPhone
1. Abre la URL en **Safari**.
2. La primera vez, pega tu API key en la pantalla de inicio (se guarda solo en ese dispositivo).
   Alternativa: escríbela en la constante `API_KEY` de `index.html`.
3. Compartir → **Añadir a pantalla de inicio**.
4. Pulsa **Abrir** y elige un `.gpx` o `.tcx` desde Archivos, iCloud, etc.

## Ubicación en vivo
- Pulsa el botón redondo (mira) abajo a la derecha: pide permiso, centra el mapa en ti y te sigue.
- Si mueves el mapa con el dedo, deja de seguirte; pulsa el botón otra vez para volver a centrar.
- Arriba verás si estás **en la ruta** (y en qué km) o **fuera de ruta** (a cuántos metros). La línea azul del perfil de elevación marca dónde estás.
- La ✕ del aviso apaga la ubicación.
- Mientras está activa, la pantalla no se apaga (para no perder el seguimiento). Gasta batería.
- iOS no permite seguir la ubicación con la pantalla bloqueada o la app en segundo plano.
- Necesita HTTPS (GitHub Pages) o localhost.

## Limitaciones de iOS
- Las PWA no aparecen en el menú "Compartir → Abrir con…"; el archivo se elige con el botón «Abrir».
  (Para recibir archivos desde otras apps haría falta una app nativa.)
- Google Maps necesita conexión: no hay mapas offline.

## Probar en el ordenador
`python3 -m http.server 8000` dentro de la carpeta y abre http://localhost:8000
(localhost cuenta como seguro; añade `http://localhost:8000/*` a los referentes de tu clave).
