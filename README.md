# disenooptico · descargas

Programa de diseño y análisis óptico para fotografía y cine, de Fix and Focus Lab. Funciona en
tu ordenador, sin conexión, con la interfaz en el navegador.

- Diseñar desde cero u optimizar, viendo reaccionar los rayos.
- Anamórficos en dos ejes.
- Ficha foto y cine: MTF, T-stop, iluminación y cobertura de formatos.
- Validación cruzada con varios motores.
- Fantasmas con el tratamiento de cada cara, bokeh, enfoque y respiración, y la leva de
  enfoque.
- Rehousing y mecánica: planos ISO 10110, STEP, DXF y atermalización de la carcasa.
- Mapas de distorsión y de sombreado para VFX.

Este repositorio solo tiene los programas ya compilados, la licencia y estas instrucciones.
El código no es público.

## Descargar

En **[Releases](../../releases/latest)**, la última versión:

- **Windows** (x64): `disenooptico-<versión>-windows-x64.zip`
- **macOS** (Apple Silicon, macOS 14 Sonoma o posterior): `disenooptico-<versión>-macos-arm64.dmg`

Los Mac con procesador Intel no están: numba, una de las librerías que usa, ya no publica
versiones para ellos.

## Abrirlo

- **Windows**: descomprime el .zip en cualquier carpeta y abre `disenooptico\disenooptico.exe`.
  Se abre una pestaña del navegador con el programa. Se queda una consola minimizada:
  cerrarla cierra el programa.
- **macOS**: abre el .dmg y arrastra `disenooptico` a Aplicaciones. Para cerrarlo: Ajustes
  (el icono de arriba a la derecha) → «Cerrar el programa»; o cierra todas sus pestañas y
  se cierra solo a los dos minutos.

### La primera vez (no va firmado)

El programa no está firmado con un certificado de desarrollador, así que el sistema avisa
la primera vez:

- **Windows**: «Windows protegió su PC» → «Más información» → «Ejecutar de todas formas».
  Si Windows 11 tiene activado «Control inteligente de aplicaciones», lo bloquea sin dar
  esa opción.
- **macOS**: dice que no se puede comprobar. Pulsa «Listo», ve a Ajustes del Sistema →
  Privacidad y seguridad → «Abrir igualmente» y confirma con la contraseña. Desde una
  terminal también vale: `xattr -dr com.apple.quarantine /Applications/disenooptico.app`.

### Dónde guarda los datos

- Windows: `%LOCALAPPDATA%\disenooptico`.
- macOS: `~/Library/Application Support/disenooptico` y `~/Library/Caches/disenooptico`.
- Los diseños que guardas, en `Documentos`.

### Qué no lleva esta versión

El diseño «desde lentes planas» con PyTorch, y DeepLens en la validación cruzada: ahí
sale como «no está instalado en esta versión». La validación sigue con Optiland, RayOptics
y el trazador propio.

### Sin interfaz, por lotes

Para una carpeta de recetas (.zmx, .seq, .json), la ficha de cada una en un CSV y, si se
pide, planos, STEP, .zmx y validación. En Windows:

```
disenooptico\disenooptico.exe lote CARPETA --todo
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

disenooptico is optical design and analysis software for photography and cinema by Fix and
Focus Lab. It runs locally, offline, with its interface in the browser; the interface is in
Spanish. Download it from [Releases](../../releases/latest) (Windows x64 and macOS Apple
Silicon). **Free for private individuals for personal use; companies and professional use
(including self-employed) need a paid licence**: ask through
[github.com/FixAndFocus](https://github.com/FixAndFocus). Binding licence text:
[LICENCIA.md](LICENCIA.md) (Spanish); [LICENSE.md](LICENSE.md) is an informative
translation.
