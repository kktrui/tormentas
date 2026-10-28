# Tormentas Mallorca

Radar de precipitación en tiempo real con estimación del rumbo de la tormenta y hora de llegada
a tu posición. Una sola página HTML, sin servidor ni claves.

- Radar: RainViewer (fotogramas cada 10 min, últimas 2 h). Teselas gratuitas hasta zoom 7.
- Mapa base: Esri World Dark Gray.
- Rumbo: correlación entre los últimos 5 fotogramas en una ventana de ~950 km alrededor de la posición.
- ETA: extrapolación lineal del último fotograma a lo largo del vector; umbrales 15/35/45 dBZ aproximados.
- Rayos: flujo en tiempo real de Blitzortung.org (protocolo no oficial; cruces que se desvanecen en 30 min).
- Células eléctricas: agrupación de los rayos de los últimos 15 min, ritmo, tendencia, rumbo y ETA (el rumbo necesita unos 8 min de página abierta).
- Sparkline: intensidad máxima sobre la posición en cada fotograma de las últimas 2 h.
- Próximas 12 h: probabilidad de lluvia, CAPE y código de tiempo de Open-Meteo (gratis, sin clave).
- Satélite: Meteosat vía EUMETSAT View (WMS gratuito): RGB de convección de día, infrarrojo MTG de noche, y contornos RDT (células en desarrollo).
- Previsión: modo con la precipitación horaria de ICON-EU (WMS del DWD, 48 h) y tabla de cinco modelos para la posición (AROME HD, ICON-EU, ECMWF IFS, GFS, UKMO vía Open-Meteo) con fila de acuerdo.
- Compartir: resumen en texto por la hoja de compartir del móvil.
- Modo mesa (`#mesa`): letras grandes y pantalla encendida (Wake Lock).
- La posición se guarda en el navegador (GPS o toque en el mapa).

Uso personal. Las fuentes tienen cuotas pensadas para uso no comercial.
