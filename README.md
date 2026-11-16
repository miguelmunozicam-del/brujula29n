# Brújula 29N

Test de 20 afirmaciones que te sitúa en un mapa político de dos ejes y te muestra en qué temas coincides o discrepas con los programas electorales de las elecciones generales del 29 de noviembre de 2026. Sin registro, sin analítica, sin servidor.

**Pruébala aquí:** `https://<tu-cuenta>.github.io/brujula29n/`

## Qué hace
- Te sitúa en dos ejes: **económico** (intervencionista − / liberal +) y **social** (progresista − / conservador +), con la zona de centro marcada.
- Explica tu perfil eje por eje en lenguaje claro.
- Compara cada respuesta con las posturas de los programas de **Frente Amplio, PP, PSOE y VOX** (orden alfabético), con la cita que justifica cada una.
- Da más peso a lo que más te importa sin preguntártelo: tus respuestas firmes («muy de acuerdo» o «muy en desacuerdo») cuentan el doble en el recuento.
- Avisa cuando coincidir en la dirección no implica coincidir en el grado, y cuando un programa no se pronuncia en muchos temas.
- Guarda tus tandas solo en tu dispositivo y muestra la anterior en gris.
- Genera un informe en PDF con el gráfico, el perfil, la tabla de coincidencias, el detalle por programa y la metodología.

## Cómo se usa
1. Pulsa «Empezar» y responde las 20 afirmaciones (una por pantalla, escala de 5 grados; economía y sociedad se alternan).
2. Consulta tu posición y el comentario, las coincidencias por programa y el detalle de cada afirmación con sus citas.
3. Pulsa «Descargar el informe en PDF» y elige «Guardar como PDF».

## Metodología
- **Test.** 20 afirmaciones, 10 por eje. En cada eje, 5 empujan hacia cada polo para neutralizar el sesgo de quien tiende a asentir (si respondes «muy de acuerdo» a todo, quedas en 0,0).
- **Puntuación.** Cada respuesta vale de −2 a +2 y se multiplica por la dirección de la afirmación (+1/−1). La suma de cada eje se divide entre 2: escala de −10 a +10. Entre −2 y +2 se considera centro.
- **Codificación de los programas.** Se leyeron completos los cuatro programas. Para cada afirmación y partido: `+1` a favor, `−1` en contra, `0` sin postura.
  - **literal**: el programa lo dice.
  - **deducida**: deducción directa; la medida implica la postura sin interpretación de afinidad (p. ej., «derogar la Ley de Vivienda» implica rechazar el tope al alquiler que esa ley habilita).
  - **mixta**: medidas en ambos sentidos; no cuenta ni como coincidencia ni como discrepancia.
  - Ante la duda, `0`.
- **Coincidencia.** Tu respuesta y la postura del programa van en el mismo sentido. Las respuestas neutrales no cuentan; las firmes («muy de acuerdo» / «muy en desacuerdo») cuentan el doble. Así el peso de cada tema sale de tus propias respuestas, sin un paso adicional.
- **Avisos.** «Grado»: respondes de forma moderada (±1) y coincides con una propuesta marcada como de máxima intensidad. «Sin postura»: el programa no se pronuncia en 5 o más temas (configurable en el JSON).

### Límites
- Solo se comparan 4 programas; otros partidos no están incluidos.
- Un programa no recoge todas las posiciones de un partido y la codificación es interpretable. Todas las citas son verificables y corregibles.
- Coincidir en la dirección no mide la intensidad de las propuestas.
- Los partidos **no se sitúan en el mapa**, a propósito.
- No es una encuesta ni una recomendación de voto.

## Datos editables
Todas las afirmaciones, posturas, citas, referencias y umbrales están en [`data/posturas.json`](data/posturas.json), separados del código. Para corregir una codificación, edita el JSON o abre un *issue* (enlace «Proponer una corrección» en cada afirmación, si `repo_url` está configurado).

## Instalación
**Versión web:** no requiere instalación.

**En local:** el navegador no deja leer `data/posturas.json` si abres `index.html` con doble clic. En la carpeta del proyecto:
```bash
python3 -m http.server 8000
```
y abre `http://localhost:8000`.

## Privacidad
- **Tus respuestas no salen de tu dispositivo.** Revelan opiniones políticas (categoría especial, art. 9 RGPD), por eso todo se calcula en tu navegador. No hay servidor, cuenta de usuario ni base de datos.
- **Sin terceros.** No hay analítica, cookies de seguimiento, publicidad ni fuentes o librerías externas.
- **Tú controlas el borrado.** Nada se borra solo. Puedes borrar el historial en «Historial y datos» o limpiando los datos del sitio en tu navegador.
- **El PDF** se genera con la función de impresión del navegador; no se envía a ningún sitio.
- **Alojamiento:** GitHub Pages puede registrar datos técnicos de acceso (como la IP) según su propia política de privacidad.

## Independencia
Proyecto independiente, sin relación con ningún partido político, candidatura o medio. Sin financiación.

## Hoja de ruta
- [ ] Enlaces a la página exacta de cada programa original (`programa_url` y número de página).
- [ ] Añadir más programas si se publican en formato analizable.
- [ ] Revisión cruzada de la codificación por personas de distintas sensibilidades.
- [ ] Versión en otras lenguas cooficiales.
- [ ] Compartir el resultado como imagen sin datos personales.

## Licencia
MIT. Consulta el archivo `LICENSE`.
