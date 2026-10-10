# Optaller

Diseño y análisis óptico para fotografía y cine, hecho desde un taller de ópticas (Fix and Focus
Lab, Madrid). Funciona en tu ordenador, sin conexión, con la interfaz en el navegador, en
castellano o en inglés.

**[Web del proyecto](https://fixandfocus.github.io/optaller/)** · **[Descargar](../../releases/latest)** · [English](#in-english)

[![El banco de diseño de Optaller: corte con rayos, ficha y tabla de superficies](docs/img/banco-es.jpg)](https://fixandfocus.github.io/optaller/)

- Diseñar desde cero u optimizar, viendo reaccionar los rayos.
- Anamórficos en sus dos ejes.
- Ficha de foto y cine: MTF, T-stop, iluminación y cobertura de formatos.
- Validación cruzada entre motores (Optiland, RayOptics y un trazador propio).
- Fantasmas con el tratamiento de cada cara, bokeh, enfoque, respiración y leva de enfoque.
- Rehousing y mecánica: planos ISO 10110, STEP, DXF y atermalización de la carcasa.
- Recementado: qué cemento conviene en cada cara pegada, y el antes y el después.
- «Detuning»: dar la vuelta a una lente y ver lo que cambia frente a una referencia.
- Mapas de distorsión y de sombreado para VFX, y vista previa sobre una foto.
- Emparejar un juego de ópticas: T-stop, tono, distorsión y medidas.

Este repositorio tiene los programas ya compilados, la licencia, la web y estas instrucciones.
El código no es público. Hasta la versión 0.4 el programa se llamaba disenooptico.

| | |
|---|---|
| ![Un anamórfico con su ficha en dos ejes](docs/img/anamorfico-es.jpg) | ![Emparejar un juego de ópticas](docs/img/juego-es.jpg) |
| ![Fantasmas con el tratamiento de cada cara](docs/img/fantasmas-es.jpg) | ![Rehousing: ajuste a lo medido, sensibilidad y recementado](docs/img/rehousing-es.jpg) |

## Descargar

En **[Releases](../../releases/latest)**, la última versión:

- **Windows** (x64): `optaller-<versión>-windows-x64.zip`
- **macOS** (Apple Silicon, macOS 14 Sonoma o posterior): `optaller-<versión>-macos-arm64.dmg`

Los Mac con procesador Intel no están: numba, una de las librerías que usa, ya no publica
versiones para ellos.

## Abrirlo

- **Windows**: descomprime el .zip en cualquier carpeta y abre `optaller\optaller.exe`.
  Se abre una pestaña del navegador con el programa. Se queda una consola minimizada:
  cerrarla cierra el programa.
- **macOS**: abre el .dmg y arrastra `Optaller` a Aplicaciones. Para cerrarlo: Ajustes
  (el icono de arriba a la derecha) → «Cerrar el programa»; o cierra todas sus pestañas y
  se cierra solo a los dos minutos.

El idioma se elige en Ajustes → «Idioma · Language». La primera vez sigue al del sistema.

### La primera vez (no va firmado)

El programa no está firmado con un certificado de desarrollador, así que el sistema avisa
la primera vez:

- **Windows**: «Windows protegió su PC» → «Más información» → «Ejecutar de todas formas».
  Si Windows 11 tiene activado «Control inteligente de aplicaciones», lo bloquea sin dar
  esa opción.
- **macOS**: dice que no se puede comprobar. Pulsa «Listo», ve a Ajustes del Sistema →
  Privacidad y seguridad → «Abrir igualmente» y confirma con la contraseña. Desde una
  terminal también vale: `xattr -dr com.apple.quarantine /Applications/Optaller.app`.

### Dónde guarda los datos

- Windows: `%LOCALAPPDATA%\optaller`.
- macOS: `~/Library/Application Support/optaller` y `~/Library/Caches/optaller`.
- Los diseños que guardas, en `Documentos/Optaller`.

Si venías de disenooptico (hasta la 0.4), la primera vez que abras Optaller renombra esas
carpetas y conserva todo: ajustes, borrador, cajón, historial y diseños.

### Qué no lleva esta versión

El diseño «desde lentes planas» con PyTorch, y DeepLens en la validación cruzada: ahí
sale como «no está instalado en esta versión». La validación sigue con Optiland, RayOptics
y el trazador propio. Lo que se exporta a ficheros (planos, CSV, informes) sale en castellano.

### Sin interfaz, por lotes

Para una carpeta de recetas (.zmx, .seq, .json), la ficha de cada una en un CSV y, si se
pide, planos, STEP, .zmx y validación. Con `--juego`, además, las compara como un juego de
ópticas. En Windows:

```
optaller\optaller.exe lote CARPETA --todo
```

## Licencia

**Uso libre para particulares, para sí mismos.** Las empresas y el uso profesional
(también como autónomo) necesitan una licencia de pago, que se pide a través de este perfil
de GitHub: [github.com/FixAndFocus](https://github.com/FixAndFocus).

El texto que vale es [LICENCIA.md](LICENCIA.md); [LICENSE.md](LICENSE.md) es su traducción
al inglés. Los componentes de software libre que lleva dentro conservan sus licencias
(LICENCIAS_DE_TERCEROS.txt, dentro de cada descarga).

## Fallos y sugerencias

En [Issues](../../issues) de este repositorio. Para una licencia comercial, también.

---

## In English

Optaller is optical design and analysis software for photo and cinema lenses, made in a lens
workshop (Fix and Focus Lab, Madrid). It runs on your computer, offline, with its interface in
the browser, in Spanish or English (Settings → “Idioma · Language”).

**[Project page](https://fixandfocus.github.io/optaller/)** · **[Download](../../releases/latest)**

[![The Optaller design bench: cross-section with rays, data sheet and surface table](docs/img/banco-en.jpg)](https://fixandfocus.github.io/optaller/)

- Design from scratch or optimize, watching the rays react. Anamorphics in their two axes.
- Photo and cinema data sheet: MTF, T-stop, illumination, format coverage.
- Cross-validation between engines (Optiland, RayOptics and an in-house ray tracer).
- Ghosts with the coating of each surface, bokeh, focus breathing and the focus cam.
- Rehousing and mechanics: ISO 10110 drawings, STEP, DXF, athermalization; recementing,
  “detuning”, lens-set matching; distortion and shading maps for VFX.

**Download** the latest build from [Releases](../../releases/latest): on Windows (x64), unzip it
and open `optaller\optaller.exe`; on macOS (Apple Silicon, macOS 14 or later), open the .dmg and
drag Optaller to Applications. The builds are not signed, so the system warns the first time:
on Windows, “More info” → “Run anyway”; on macOS, System Settings → Privacy & Security → “Open
Anyway”. Exported files (drawings, CSV, reports) are written in Spanish.

**Free for private individuals for personal use; companies and professional use (including
self-employed) need a paid licence**: ask through
[github.com/FixAndFocus](https://github.com/FixAndFocus). The binding licence text is
[LICENCIA.md](LICENCIA.md) (Spanish); [LICENSE.md](LICENSE.md) is an informative translation.
The code is not public. Until version 0.4 the program was called disenooptico.
