# Plantilla TFG / TFM

Plantilla de Trabajo Fin de Grado / Trabajo Fin de Máster en LaTeX,
proporcionada por **Diverso Lab** (Universidad de Sevilla) y distribuida bajo
licencia **Creative Commons Attribution 4.0 International (CC BY 4.0)**.

Eres libre de copiarla, modificarla y redistribuirla, incluso con fines
comerciales, siempre que se mantenga la atribución a Diverso Lab.
Texto completo en [`LICENSE`](LICENSE) y en
<https://creativecommons.org/licenses/by/4.0/>.

La estructura de la plantilla está alineada con las rúbricas de evaluación
habituales de TFG/TFM en Ingeniería Informática: cada capítulo y tabla
existe porque algún criterio de evaluación lo pide. Si rellenas todas las
guías `\ph{...}` con contenido propio de calidad, la memoria cubre
estructuralmente los descriptores de la máxima calificación.

## Qué incluye

- Portada institucional (logo de la universidad incluido).
- Bloque único **DATOS DEL TRABAJO** en `main.tex`: título, autor/a,
  tutores, titulación, ciudad y fecha se rellenan una sola vez y se
  propagan a la portada, la declaración de autoría y los metadatos del PDF.
- Preliminares: declaración de autoría, agradecimientos, resumen
  (ES/EN), índices de contenidos, tablas y figuras, lista de acrónimos.
- **Guía de estilo y revisión** integrada: visible solo en modo borrador,
  desaparece automáticamente de la versión final.
- 9 capítulos de cuerpo con la estructura clásica de un TFG/TFM de
  Ingeniería Informática: introducción (con objetivos SMART y criterios de
  éxito medibles), estado del arte (con comparativa de trabajos
  relacionados), planificación y gestión del proyecto (acta de
  constitución, EDT, línea base, riesgos con seguimiento, comunicaciones,
  control de cambios, presupuesto y lecciones aprendidas), requisitos,
  diseño, implementación, pruebas (pirámide de pruebas), **resultados y
  discusión** (métricas, comparación con trabajos previos) y conclusiones
  (con limitaciones y trabajo futuro).
- Apéndices: apéndice genérico, manual de instalación/despliegue y manual
  de usuario.
- Bibliografía configurada (BibLaTeX + Biber, estilo numérico IEEE) con
  ejemplos de cada tipo de entrada en `bibliography.bib`.
- Comando `\ph{...}` para marcar contenido por rellenar y un toggle
  `\drafttrue` / `\draftfalse` para ocultar todos los placeholders en la
  versión final con un solo cambio.
- **Soporte para la defensa**: guía completa en
  [`docs/GUIA_DEFENSA.md`](docs/GUIA_DEFENSA.md) y esqueleto Beamer en
  [`presentation/`](presentation/).

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

# 2. Compila (4 pasos: pdflatex → biber → pdflatex → pdflatex)
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
| Título, autor, tutor/es, titulación, ciudad, fecha | Bloque **DATOS DEL TRABAJO** en `main.tex` (se propaga a portada, declaración y metadatos del PDF) |
| Logo de la universidad             | Reemplaza `figures/img/logo_uni.png`              |
| Resumen y abstract                 | [`sections/00_resumen.tex`](sections/00_resumen.tex) |
| Acrónimos                          | [`sections/00_acronimos.tex`](sections/00_acronimos.tex) |
| Bibliografía                       | [`bibliography.bib`](bibliography.bib)            |
| Modo borrador → final              | `\drafttrue` → `\draftfalse` en `main.tex`        |

## Modo borrador y modo final

Por defecto la plantilla está en modo borrador (`\drafttrue`):
todos los placeholders `\ph{...}` se imprimen en gris cursiva entre
corchetes, para que veas a simple vista qué queda por rellenar, y la
guía de estilo aparece tras la lista de acrónimos.

Cuando hayas terminado, abre `main.tex` y cambia:

```latex
\drafttrue
```

por:

```latex
\draftfalse
```

Recompila. Todos los `\ph{...}` y la guía de estilo desaparecerán del PDF
sin necesidad de borrarlos del fuente.

**Antes de entregar, revisa el log de compilación**: en modo final, cada
`\ph{...}` que olvidaste rellenar emite un aviso
`Placeholder sin rellenar: ...` en el log. Presta atención especial a los
**títulos de sección** que son placeholders (p. ej.
`\section{\ph{Concepto / paradigma principal}}` en el estado del arte):
si no los sustituyes por títulos reales, en la versión final quedan
secciones sin título y entradas vacías en el índice.

## Bibliografía y citas

- Estilo numérico por orden de cita (convención IEEE, estándar en
  ingeniería): `[1]`, `[2, 3]`, `[1-4]`.
- `bibliography.bib` incluye un ejemplo de cada tipo de entrada
  (`@article`, `@inproceedings`, `@book`, `@online`, `@software`,
  `@thesis`) como modelo de campos. Las citas de muestra del estado del
  arte están dentro de `\ph{...}`, así que en modo final desaparecen y
  las entradas de ejemplo no se imprimen; aun así, conviene borrarlas o
  sustituirlas por tus referencias reales al terminar.
- Orientación de cantidad: 20–40 referencias (TFG) / 30–60 (TFM),
  mayoría revisadas por pares, más de la mitad de los últimos 5 años,
  con `doi` siempre que exista y `urldate` obligatorio en recursos web.
- Regla de oro: toda afirmación que no sea tuya lleva su `\cite{...}`
  junto a la afirmación, no al final del párrafo.

## Estilo y revisión

En modo borrador, la memoria incluye una **Guía de estilo y revisión**
(registro y voz, vocabulario técnico, prosa frente a viñetas, figuras y
tablas, checklist de revisión final). Léela antes de empezar a escribir
y repasa su checklist antes de entregar. Desaparece sola de la versión
final.

## Defensa del trabajo

La defensa suele valer en torno al 30 % de la nota final y se evalúa con
rúbrica propia (material, claridad, síntesis, dominio del tema y
respuestas al tribunal). La plantilla incluye:

- [`docs/GUIA_DEFENSA.md`](docs/GUIA_DEFENSA.md) — guía completa:
  estructura de diapositivas con minutaje para 15 minutos, diseño del
  material, demo con plan B, diapositivas de respaldo, banco de preguntas
  típicas del tribunal (con la sección de la memoria donde está cada
  respuesta), plan de ensayos y checklist del día D.
- [`presentation/`](presentation/) — esqueleto Beamer sobrio listo para
  rellenar, alineado con ese minutaje, con diapositivas de respaldo tras
  el «Gracias».

Consejos mínimos si no lees nada más: ensaya **cronometrando** al menos
tres veces (pasarse de tiempo penaliza directamente); dedica las mejores
diapositivas a **resultados con cifras** (capítulo 8 de la memoria), no a
la implementación; lleva la demo grabada en vídeo como plan B; y prepara
diapositivas de respaldo para las preguntas previsibles del tribunal.

## Estructura de directorios

```
.
├── main.tex                  # Documento principal (datos del trabajo + preámbulo)
├── bibliography.bib          # Referencias (con ejemplos de cada tipo)
├── LICENSE                   # CC BY 4.0
├── README.md                 # Este archivo
├── docs/
│   └── GUIA_DEFENSA.md       # Guía para preparar la defensa
├── presentation/
│   ├── diapositivas.tex      # Esqueleto Beamer de la defensa
│   └── README.md
├── figures/img/              # Imágenes (solo el logo por defecto)
└── sections/                 # Capítulos y preliminares
    ├── 00_cover.tex
    ├── 00_declaracion.tex
    ├── 00_agradecimientos.tex
    ├── 00_resumen.tex
    ├── 00_acronimos.tex
    ├── 00_guia_estilo.tex    # Solo visible en modo borrador
    ├── 01_introducción.tex
    ├── 02_estado_del_arte.tex
    ├── 03_planificación.tex
    ├── 04_requisitos.tex
    ├── 05_diseño.tex
    ├── 06_implementación.tex
    ├── 07_pruebas.tex
    ├── 08_resultados.tex
    ├── 09_conclusiones.tex
    ├── A_apendice.tex
    ├── B_manual_instalacion.tex
    └── C_manual_usuario.tex
```

## Atribución sugerida

Si reutilizas la plantilla, basta con incluir en algún sitio del proyecto
(README, agradecimientos o pie de página):

> Plantilla TFG/TFM proporcionada por **Diverso Lab** (Universidad de Sevilla),
> distribuida bajo licencia [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
