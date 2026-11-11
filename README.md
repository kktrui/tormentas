# Tormentas Mallorca

Radar de precipitación en tiempo real con estimación del rumbo de la tormenta y hora de llegada
a tu posición. Una sola página HTML, sin servidor ni claves.

- Radar: RainViewer (fotogramas cada 10 min, últimas 2 h). Teselas gratuitas hasta zoom 7.
- Mapa base: Esri World Dark Gray.
- Intensidad: dBZ exactos (formato en bruto de RainViewer, que además da la cobertura real del radar; si falla, paleta 2 descodificada). Umbrales 20/40/50 dBZ.
- Rumbo: correlación entre fotogramas separados 20 y 30 min (últimos 7), afinada a décimas de píxel, en una ventana de ~950 km alrededor de la posición. El desacuerdo entre parejas da la incertidumbre; con menos de 3 parejas coherentes no se da rumbo.
- ETA: extrapolación del último fotograma con 17 rumbos posibles alrededor del medido. Te alcanza en ≥60 % → aviso firme; 20-60 % → «puede llover» (y «?» en las casillas); el margen de hora sale de esos mismos rumbos. No se extrapola más allá de la cobertura del radar.
- Célula principal: rumbo propio por correlación centrada en ella (σ 90 km) y cono de incertidumbre (≈ la mitad de los casos medidos a 20-30 min).
- Fiabilidad: parecido entre fotogramas a 30 min una vez desplazados (alta ≥ 0,7).
- Viento en altura: media de cinco modelos a 700 hPa (≈3000 m, Open-Meteo). Si el radar no da rumbo se usa ese viento (abanico ancho, fiabilidad baja, nunca aviso firme); si el rumbo medido se aparta 30° o más del viento, la fiabilidad baja un escalón.
- Probabilidad de lluvia a 3 h: seis tramos de 30 min que mezclan el abanico del radar (¾; 0,6 a partir de 2 h) con los cinco modelos (cuántos dan ≥0,1 mm en el tramo, pasado a frecuencia real medida). El titular sigue saliendo solo del radar.
- Constantes ajustadas con radar real archivado (9 zonas, una mañana de nov-2026): sirve hasta ~60 min; la lluvia fuerte a más de 30 min es poco predecible con cualquier método.
- Rayos: flujo en tiempo real de Blitzortung.org (protocolo no oficial; cruces que se desvanecen en 30 min).
- Células eléctricas: agrupación de los rayos de los últimos 15 min, ritmo, tendencia, rumbo y ETA (el rumbo necesita unos 8 min de página abierta).
- Sparkline: intensidad máxima sobre la posición en cada fotograma de las últimas 2 h.
- Próximas 12 h: probabilidad de lluvia, CAPE y código de tiempo de Open-Meteo (gratis, sin clave).
- Satélite: Meteosat vía EUMETSAT View (WMS gratuito): RGB de convección de día, infrarrojo MTG de noche, y contornos RDT (células en desarrollo).
- Previsión: modo con la precipitación horaria de ICON-EU (valores numéricos del WCS del DWD en GeoTIFF, leídos con geotiff.js y pintados con una rampa continua propia; zona de ±8° × ±5° alrededor de la posición, 48 h) y tabla de cinco modelos para la posición (AROME HD, ICON-EU, ECMWF IFS, GFS, UKMO vía Open-Meteo) con fila de acuerdo.
- Compartir: resumen en texto por la hoja de compartir del móvil.
- Modo mesa (`#mesa`): letras grandes y pantalla encendida (Wake Lock).
- La posición se guarda en el navegador (GPS o toque en el mapa).

Uso personal. Las fuentes tienen cuotas pensadas para uso no comercial.
