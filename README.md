# Super Star Wars — Traducción al español

[![Invítame a un café en Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/johanderohan)

Traducción al **español de España** de *Super Star Wars* (Super Nintendo, 1992), el
juego de acción y plataformas de LucasArts y Sculptured Software basado en la primera
película de la saga, que nunca salió en español.

La traducción se reparte como **parche**: no incluye el juego. Necesitas tu propia
copia para aplicarlo. Se hace **desde el inglés** de la versión estadounidense.

## Estado

Última versión: **v1.0**. Estado: **en revisión**.

| Parte | Estado |
|---|---|
| Menús, opciones, mando, HUD, bonificaciones y tarjetas de nivel | Traducidos |
| Avisos de recogida, armas y nombres de jefes y enemigos | Traducidos |
| Pantalla de selección de héroe (rótulos dentro de la imagen) | Traducida |
| Frase «Hace mucho tiempo…» y crawl de apertura | Redibujados en castellano |
| Diálogos de las escenas de historia, mensaje final y créditos | Traducidos |
| Caracteres españoles | **á é í ó ú ñ Á É Í Ó Ú Ñ ¡** (ver «Limitaciones») |
| Revisión durante una partida | Parcial |

El texto del juego va casi todo en **mayúsculas** (la fuente original solo las tiene). El parche
rehace los gráficos de texto con los recursos del propio juego y añade los signos que faltaban.

### Qué se conserva a propósito

Los **logotipos y rótulos de marca** se dejan como en el original: el logo STAR WARS (título,
tarjeta de nivel y crawl), el logo de LucasArts y «IN STEREO», el rótulo rojo GAME OVER y el
póster del título. Para entender la historia y jugar no hacen falta.

### Limitaciones conocidas

- **Tildes en mayúsculas**: la fuente mide 7 píxeles de alto y la tilde se dibuja en la fila de
  arriba; donde no hay una fila libre encima (nombres de fase, HUD, avisos y nombres de jefe, que
  son una sola línea) las mayúsculas van **sin tilde**, como en el original.
- La fuente no tiene `?` ni `¿`: no se usan (el crawl y los diálogos no los necesitan).
- Por anchura se usan «TIRO» y «SEGUIR» (en vez de «DISPARO» y «CONTINUAR»), «SABLE DE SALUD»,
  «BANDA SONORA» y «QUE LA FUERZA SEA CONTIGO».
- Algunas líneas de crawl y de diálogos quedan **justificadas con huecos** grandes, como en el original.
- «GUERRAS CLÓNICAS» (escena de Leia) está escrito de memoria del doblaje español de 1977 y no se
  ha podido contrastar con una fuente; el rótulo «TURBO» sustituye a «JETS» (la barra de la fase
  del deslizador) por contexto.

### Qué se ha comprobado

Todo en **emulador** (snes9x mediante libretro; arranque, título, crawl y primer nivel también en
bsnes). Con la ROM final se ha jugado desde un arranque en frío: logos, título, opciones y mando,
frase de apertura, crawl, tarjeta de nivel, el nivel 1 hasta la zona de pozos, la muerte, «SEGUIR 03»
y «FIN DEL JUEGO». Las escenas de historia, la selección de héroe y las fases siguientes se han visto
ejecutando el **código real del juego** para pasar de nivel desde un estado de partida (no jugándolas):
la secuencia de escenas es idéntica a la del original en todas las fases válidas y no hay pantallas
negras ni gráficos corruptos.

**No se ha probado**: una partida completa, la pantalla de bonificaciones de fin de nivel, el mensaje
«¡BUEN DISPARO, CHICO!» y el final real (solo revisión estática de sus pantallas), guardar/cargar (el
juego no guarda partidas), consola real ni flashcart. La redacción y las revisiones están hechas con
asistencia de IA, **sin revisión humana independiente**. No se han probado las ediciones Rev 1, europea
ni japonesa.

## Cómo aplicar el parche

1. Descarga el parche `.xdelta` de la sección **[Releases](../../releases)**.
2. Consigue tu copia del juego en versión **USA** (la original, no «Rev 1» ni la europea). El parche solo
   funciona con esa versión exacta.
3. **Comprueba que tu copia es la correcta** antes de nada:

   | | |
   |---|---|
   | Archivo | `Super Star Wars (USA).sfc` |
   | Tamaño | 1.048.576 bytes (8 Mbit), sin cabecera de copiador |
   | MD5 | `ea840d3722f90dee824f5064e171e510` |
   | SHA-1 | `dbff9bbb155f09376c4c7fe3d68e77c4a444ae3c` |

   ```bash
   md5sum "Super Star Wars (USA).sfc"     # Linux
   md5 "Super Star Wars (USA).sfc"        # macOS
   CertUtil -hashfile "Super Star Wars (USA).sfc" MD5   # Windows
   ```

   Si tu archivo mide 1.049.088 bytes, tiene cabecera de 512 bytes: quítasela antes. Si no coincide,
   el parche fallará o dará un resultado corrupto.
4. Aplica el parche con una de estas herramientas:
   - **Windows**: [Delta Patcher](https://github.com/marco-calautti/DeltaPatcher/releases)
   - **Linux / macOS**: `xdelta3 -d -s "Super Star Wars (USA).sfc" super-star-wars-snes-es-v1.0.xdelta "Super Star Wars (Castellano).sfc"`
5. Comprueba que la ROM resultante mide **2.097.152 bytes** (2 MiB) y que su MD5 es
   **`09949b13bf028774aa52393a1fdb0618`**.
6. Carga la ROM resultante en tu emulador o flashcart. **Necesitas un emulador o flashcart que admita
   ROM de 16 Mbit**: el parche amplía la ROM de 1 a 2 MiB para alojar los gráficos y textos nuevos.

Aplica cada versión sobre la **ROM USA original**, no sobre una ROM ya traducida.

## Cambios por versión

### v1.0 — primera versión

Traducción completa de menús, HUD, avisos, jefes, selección de héroe, diálogos, créditos, frase de
apertura y crawl. Primera publicación: en revisión.

## Créditos

- Traducción y herramientas: johanderohan, con asistencia de modelos de IA para la ingeniería
  inversa, la redacción y las revisiones.
- La frase «Hace mucho tiempo, en una galaxia muy, muy lejana….» se ha dibujado a partir de
  **Open Sans Condensed Bold** (Steve Matteson, licencia SIL Open Font License 1.1).
- Pruebas: snes9x y bsnes mediante libretro. Parches: xdelta3.

## Aviso

Este proyecto es una traducción hecha por afición, sin ánimo de lucro y sin relación alguna con
LucasArts, Lucasfilm, Disney, Sculptured Software, JVC ni Nintendo. *Star Wars* y todos los nombres,
personajes y marcas asociados pertenecen a sus titulares. Aquí no se distribuye el juego ni ninguna
parte de él: solo un parche que modifica una copia que ya tengas.

Si eres el titular de los derechos y quieres que retire esto, abre una incidencia y lo hago.
