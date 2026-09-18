# Mi Dashboard — V3

Esta versión conserva el diseño aprobado y elimina correo, YouTube, recordatorios y Apple Watch.

## Datos automáticos
- Clima: Open-Meteo.
- MLB: MLB Stats API.
- Mercados: GitHub Actions consulta datos de Yahoo Finance del lado del servidor y actualiza `market.json` cada 15 minutos. Yahoo Finance no ofrece CORS para llamadas directas desde Safari, por eso se hace en Actions. Esta fuente es no oficial y debe considerarse una referencia, no una fuente de trading.

## Calendario y música
Safari no puede leer automáticamente tu calendario privado de iCloud ni el estado de reproducción de Apple Music/Spotify solo por ser una página web. V3 deja el calendario visual y accesos a Música. Para sincronizar tu calendario privado habría que añadir una integración con OAuth o una fuente de calendario compartida.

## Publicación
Sube TODO el contenido de esta carpeta al repositorio de GitHub, incluyendo `.github/workflows/update-markets.yml`.
Activa GitHub Pages desde Settings → Pages → Deploy from a branch → main → / (root).
Después de la primera ejecución de Actions, `market.json` empezará a recibir datos.

La API de Open-Meteo documenta el endpoint Forecast y no requiere API key. La API de MLB expone `/api/v1/schedule`. Yahoo Finance Chart requiere una llamada desde servidor porque no ofrece CORS en navegador.
