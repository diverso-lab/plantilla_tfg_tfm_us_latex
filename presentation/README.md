# Diapositivas para la defensa

Esqueleto Beamer sobrio (16:9) para la presentación ante el tribunal,
alineado con la estructura y el minutaje de defensa de ~15 minutos de
`docs/GUIA_DEFENSA.md` (la planificación, Cap. 3, se menciona
verbalmente o va en backup).

**Es un proyecto independiente de la memoria**: no se incluye desde
`main.tex` ni comparte ficheros con ella.

## Cómo compilar

- **Local**: desde este directorio, `pdflatex diapositivas.tex`
  (dos pasadas para que el índice y la numeración queden bien).
- **Overleaf**: sube la carpeta `presentation/` como un proyecto
  **nuevo** (separado de la memoria), con `diapositivas.tex` como
  fichero principal y compilador pdfLaTeX.
- **Logo**: copia `figures/img/logo_uni.png` de la memoria a esta
  carpeta (`cp ../figures/img/logo_uni.png .`) y descomenta la línea
  `\titlegraphic` del preámbulo.

## Antes de la defensa

- El minutaje detallado, los checklists de demo y ensayo y el banco de
  preguntas del tribunal están en `docs/GUIA_DEFENSA.md`.
- Sustituye todos los placeholders `\ph{...}` (aquí no hay modo
  borrador: lo que quede en gris se proyecta en gris).
- Exporta y lleva el **PDF** al día de la defensa (USB + nube): nunca
  dependas de compilar ni de la red del aula.
