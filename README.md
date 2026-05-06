# Plantilla TFG / TFM

Plantilla de Trabajo Fin de Grado / Trabajo Fin de Máster en LaTeX,
proporcionada por **Diverso Lab** (Universidad de Sevilla) y distribuida bajo
licencia **Creative Commons Attribution 4.0 International (CC BY 4.0)**.

Eres libre de copiarla, modificarla y redistribuirla, incluso con fines
comerciales, siempre que se mantenga la atribución a Diverso Lab.
Texto completo en [`LICENSE`](LICENSE) y en
<https://creativecommons.org/licenses/by/4.0/>.

## Qué incluye

- Portada institucional (logo de la universidad incluido).
- Preliminares: declaración de autoría, agradecimientos, resumen
  (ES/EN), índices de contenidos, tablas y figuras, lista de acrónimos.
- 8 capítulos de cuerpo con la estructura clásica de un TFG/TFM de
  Ingeniería Informática:
  introducción, estado del arte, planificación, requisitos, diseño,
  implementación, pruebas (siguiendo la pirámide de pruebas) y conclusiones.
- Apéndices: apéndice genérico, manual de instalación/despliegue y manual
  de usuario.
- Bibliografía configurada (BibLaTeX + Biber) y vacía, lista para añadir
  entradas.
- Comando `\ph{...}` para marcar contenido por rellenar y un toggle
  `\drafttrue` / `\draftfalse` para ocultar todos los placeholders en la
  versión final con un solo cambio.

## Cómo usarla

Tienes dos formas de trabajar con la plantilla. Elige la que mejor te
encaje.

### Opción A — Overleaf (recomendado si no quieres instalar nada)

1. Descarga este repositorio como ZIP (botón **Code → Download ZIP** en
   GitHub) o haz un fork.
2. Entra en <https://www.overleaf.com>, crea cuenta si no la tienes y
   pulsa **New Project → Upload Project**.
3. Sube el ZIP. Overleaf detectará automáticamente `main.tex` como
   documento principal.
4. En **Menu → Compiler** asegúrate de que está seleccionado **pdfLaTeX**
   y en **Menu → Bibliography** elige **Biber**.
5. Pulsa **Recompile**. Ya puedes empezar a editar.

Overleaf compila la bibliografía automáticamente, así que no tienes que
ejecutar `biber` a mano.

### Opción B — Fork y compilación en local

Requisitos previos:

- Una distribución de TeX completa: **TeX Live** (Linux/macOS/Windows)
  o **MacTeX** (macOS). MiKTeX también vale.
- `biber` (suele venir incluido en TeX Live / MacTeX).

Pasos:

```bash
# 1. Haz fork del repositorio en GitHub y clónalo
git clone https://github.com/<tu-usuario>/<nombre-repo>.git
cd <nombre-repo>

# 2. Compila (3 pasadas: pdflatex → biber → pdflatex → pdflatex)
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

El PDF resultante es `main.pdf`.

Si trabajas en VS Code, la extensión **LaTeX Workshop** detecta
automáticamente el `main.tex` y compila al guardar.

## Personalización rápida

| Qué quieres cambiar                | Dónde se cambia                                   |
| ---------------------------------- | ------------------------------------------------- |
| Título, autor, tutor/es, fecha     | [`sections/00_cover.tex`](sections/00_cover.tex)  |
| Logo de la universidad             | Reemplaza `figures/img/logo_uni.png`              |
| Resumen y abstract                 | [`sections/00_resumen.tex`](sections/00_resumen.tex) |
| Acrónimos                          | [`sections/00_acronimos.tex`](sections/00_acronimos.tex) |
| Bibliografía                       | [`bibliography.bib`](bibliography.bib)            |
| Modo borrador → final              | `\drafttrue` → `\draftfalse` en `main.tex`        |
| Metadatos del PDF                  | Bloque `\hypersetup{...}` en `main.tex`           |

## Modo borrador y modo final

Por defecto la plantilla está en modo borrador (`\drafttrue`):
todos los placeholders `\ph{...}` se imprimen en gris cursiva entre
corchetes, para que veas a simple vista qué queda por rellenar.

Cuando hayas terminado, abre `main.tex` y cambia:

```latex
\drafttrue
```

por:

```latex
\draftfalse
```

Recompila. Todos los `\ph{...}` desaparecerán del PDF sin necesidad de
borrarlos del fuente.

## Estructura de directorios

```
.
├── main.tex                  # Documento principal
├── bibliography.bib          # Referencias (vacío de inicio)
├── LICENSE                   # CC BY 4.0
├── README.md                 # Este archivo
├── figures/img/              # Imágenes (solo el logo por defecto)
└── sections/                 # Capítulos y preliminares
    ├── 00_cover.tex
    ├── 00_declaracion.tex
    ├── 00_agradecimientos.tex
    ├── 00_resumen.tex
    ├── 00_acronimos.tex
    ├── 01_introducción.tex
    ├── 02_estado_del_arte.tex
    ├── 03_planificación.tex
    ├── 04_requisitos.tex
    ├── 05_diseño.tex
    ├── 06_implementación.tex
    ├── 07_pruebas.tex
    ├── 08_conclusiones.tex
    ├── A_apendice.tex
    ├── B_manual_instalacion.tex
    └── C_manual_usuario.tex
```

## Atribución sugerida

Si reutilizas la plantilla, basta con incluir en algún sitio del proyecto
(README, agradecimientos o pie de página):

> Plantilla TFG/TFM proporcionada por **Diverso Lab** (Universidad de Sevilla),
> distribuida bajo licencia [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
