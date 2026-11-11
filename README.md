# TrackViewer (web / PWA)

Visor de rutas GPX y TCX sobre Google Maps. Funciona en Safari de iPhone y se
instala en la pantalla de inicio. No necesita Mac ni cuenta de Apple Developer.

Incluye: carga de GPX/TCX, ruta con inicio/fin, distancia, desnivel +/−, tiempo,
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

## Limitaciones de iOS
- Las PWA no aparecen en el menú "Compartir → Abrir con…"; el archivo se elige con el botón «Abrir».
  (Para recibir archivos desde otras apps haría falta una app nativa.)
- Google Maps necesita conexión: no hay mapas offline.

## Probar en el ordenador
`python3 -m http.server 8000` dentro de la carpeta y abre http://localhost:8000
(localhost cuenta como seguro; añade `http://localhost:8000/*` a los referentes de tu clave).
