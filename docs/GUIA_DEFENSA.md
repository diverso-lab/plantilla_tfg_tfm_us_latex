# Guía de preparación de la defensa

> La defensa pesa típicamente un **30 % de la nota final**. Una memoria de
> Sobresaliente con una defensa floja no llega al 9,5. Lee esta guía cuando la
> memoria esté cerrada: las diapositivas **salen de la memoria**, no se
> inventan. Calcula al menos **una semana** de preparación.

## 1. Qué evalúa el tribunal

| Subcriterio | Peso (de la defensa) | Qué significa en la práctica |
|---|---|---|
| 2.1 Material de presentación | 20 % | Diapositivas limpias y profesionales, recursos visuales propios, demo en vivo si procede |
| 2.2 Claridad expositiva | 20 % | Discurso ordenado, sin leer las diapositivas, voz y ritmo controlados |
| 2.3 Capacidad de síntesis | 10 % | Contar lo esencial **dentro del tiempo asignado**; pasarse de tiempo penaliza siempre |
| 2.4 Dominio del tema | 30 % | Hablar con soltura de decisiones, alternativas y resultados, sin recitar de memoria |
| 2.5 Respuesta a preguntas | 20 % | Responder con datos de tu propia memoria; reconocer límites sin bloquearte |

Fíjate: el subcriterio que más pesa es el **dominio del tema** (30 %). Se
entrena releyendo tus propias tablas de decisiones (alternativas tecnológicas,
riesgos, requisitos, resultados) los días previos: el tribunal pregunta casi
siempre sobre **decisiones**, no sobre código.

## 2. Estructura de la presentación (defensa de ~15 min)

Regla de oro: **~1 diapositiva por minuto**. Para 15 minutos, 12–14
diapositivas de contenido como máximo. Cada bloque sale de un capítulo
concreto de la memoria:

| # | Diapositiva | Sale de | Tiempo |
|---|---|---|---|
| 1 | Portada: título, autor, tutor/es, titulación | Portada | 0:30 |
| 2 | Índice (opcional: una frase y avanzas; es lo primero que cae si vas justo) | — | 0:30 |
| 3 | Contexto y motivación (una figura, casi sin texto) | Cap. 1, Contexto y Motivación | 1:00 |
| 4 | El problema en una frase destacada + 2–3 evidencias | Cap. 1, Problema | 1:00 |
| 5 | Objetivos O1…On (literales de la memoria: los retomas al final) | Cap. 1, Objetivos | 1:00 |
| 6 | Estado del arte **breve**: tabla comparativa reducida + hueco que cubre tu trabajo | Cap. 2, tabla comparativa | 1:00 |
| 7–8 | Solución: arquitectura (diagrama) + implementación destacada, con 2–3 decisiones de diseño clave | Caps. 4–6 | 3:00 |
| 9 | Demo en vivo o vídeo (diapositiva ancla con los 2–3 pasos que vas a enseñar) | Apéndice C como guion | 2:30 |
| 10–11 | **Resultados con métricas**: cumplimiento de los criterios de éxito + discusión y comparación con otros trabajos | Cap. 8, Resultados y discusión | 2:30 |
| 12 | Conclusiones: tabla objetivo ↔ grado de cumplimiento + limitaciones honestas | Cap. 9 | 1:30 |
| 13 | Trabajo futuro + frase de cierre memorizada + «Gracias» | Cap. 9 | 0:30 |
| 14+ | **Backup** (tras el «Gracias», ver sección 5) | — | solo si preguntan |

Total: ~15:00 con el índice opcional (~14:30 sin él). Llega al ensayo final
con **un minuto de margen por debajo** del límite: si te alargas en los
ensayos, el índice es el primer recorte.

**Capítulos que NO merecen diapositiva propia:**

- **Planificación y presupuesto (Cap. 3):** una mención verbal de una frase
  («el proyecto se desarrolló en N fases a lo largo de X meses, con un coste
  estimado de Y €») al presentar la solución o las conclusiones. Ten la tabla
  de presupuesto en backup por si preguntan.
- **Requisitos (Cap. 4):** no enumeres requisitos; intégralos en la solución
  («el sistema debía soportar X, por eso la arquitectura es Y»).

**Ajuste a otros tiempos:**

- **10 min:** estado del arte pasa a una frase, la demo se sustituye por un
  vídeo de 60–90 s, una sola diapositiva de resultados. ~9 diapositivas.
- **20 min (típico en TFM):** amplía solución (4–5 diapositivas), demo de
  3–4 min y resultados en 3 diapositivas. No estires introducción ni estado
  del arte: el tiempo extra va a **solución y resultados**.

## 3. Diseño de las diapositivas

- **Una idea por diapositiva.** Si necesitas dos frases para titularla, son
  dos diapositivas.
- **Poco texto:** regla 6×6 como tope (máx. 6 líneas, máx. 6 palabras por
  línea). Las diapositivas son apoyo visual; el discurso es tuyo.
- **Reutiliza las figuras y tablas de la memoria** (mismo estilo visual =
  coherencia profesional, y ya las tienes hechas). Simplifica las tablas: en
  pantalla, 3–4 filas y 3–4 columnas como máximo.
- **Numera las diapositivas** (n.º visible en una esquina): el tribunal las
  cita al preguntar («en la 7 decías que…»).
- Tipografía legible desde el fondo del aula (≥ 20 pt en cuerpo), fondo
  claro, 1–2 colores, la misma fuente en todo el conjunto.
- En el directorio [`presentation/`](../presentation/) del repositorio tienes
  un **esqueleto Beamer** que sigue exactamente el minutaje de la tabla
  anterior. Es un proyecto independiente de la memoria: súbelo como proyecto
  nuevo a Overleaf si lo usas.

## 4. Demo en vivo

**¿Cuándo compensa?** Si tu trabajo tiene una interfaz o un comportamiento
observable y la demo cabe en 2–3 minutos, compensa: es lo que más sube la
percepción de material excelente (2.1) y de dominio (2.4). Si la demo
necesita más de 3 acciones, depende de servicios externos inestables o tu
resultado es esencialmente numérico (un modelo, un análisis), **mejor un
vídeo o las gráficas del Capítulo 8**.

Checklist de la demo:

- [ ] Guion escrito de **2–3 acciones** concretas (usa los pasos del
      Apéndice C, Manual de usuario, como base). Nada de improvisar rutas.
- [ ] Datos de ejemplo **precargados**: nunca crees cuentas ni rellenes
      formularios largos en directo.
- [ ] Entorno **probado ese mismo día**, en el portátil con el que vas a
      defender, y que no dependa de la red del aula (todo en local).
- [ ] **Plan B obligatorio:** vídeo de la demo grabado y descargado en local.
- [ ] **Plan C:** capturas de pantalla de cada paso en diapositivas de
      emergencia (en el bloque de backup).

Si la demo falla en directo: una frase tranquila («os lo muestro en el vídeo
de respaldo») y al plan B sin disculparte dos veces. Una demo caída con plan
B ejecutado con calma apenas penaliza; quedarse bloqueado, sí.

## 5. Diapositivas de respaldo (backup)

Después de la diapositiva de «Gracias», añade **5–10 diapositivas que no
presentas** pero que te dejan responder preguntas con material preparado:

| Backup sugerido | Sale de |
|---|---|
| Diagrama de arquitectura detallado / modelo de datos | Cap. 5 |
| Tabla de análisis de alternativas tecnológicas | Cap. 6 |
| Tabla resumen de la suite de pruebas y cobertura | Cap. 7 |
| Comparativa completa con trabajos relacionados | Cap. 2 |
| Presupuesto y desviación de horas estimadas vs. reales | Cap. 3 |
| Tecnologías o diseños **descartados** y por qué | Caps. 5–6 |
| Resultados ampliados (todas las métricas, no solo las del cuerpo) | Cap. 8 |

Responder a una pregunta saltando a una diapositiva de backup preparada es
de las señales de dominio (2.4) más claras que puedes dar al tribunal.

## 6. Banco de preguntas típicas (y dónde está ya tu respuesta)

Prepara estas preguntas **antes** de la defensa. La respuesta está en tu
propia memoria; relee esas secciones la víspera:

| # | Pregunta del tribunal | Tu respuesta está en |
|---|---|---|
| 1 | ¿Por qué elegiste la tecnología X y no Y? | Cap. 6, análisis de alternativas tecnológicas |
| 2 | ¿Cómo sabes que tu sistema funciona? | Cap. 7 (pruebas y cobertura) + Cap. 8 (resultados frente a criterios de éxito) |
| 3 | ¿Qué limitaciones tiene tu trabajo? | Cap. 9, sección Limitaciones |
| 4 | ¿Cuánto costaría desarrollar esto en el mercado? | Cap. 3, Presupuesto |
| 5 | ¿Qué harías distinto si empezaras hoy? | Cap. 3, Lecciones aprendidas + Cap. 9 |
| 6 | ¿En qué se diferencia de los trabajos relacionados? | Cap. 2, tabla comparativa + Cap. 8, comparación con otros trabajos |
| 7 | ¿Por qué tu trabajo no cubre la funcionalidad Z? | Cap. 1, Alcance (exclusiones justificadas) |
| 8 | ¿Cómo escala con más usuarios o más datos? | Cap. 4, RNF de rendimiento + Cap. 5, arquitectura |
| 9 | ¿Se cumplieron los objetivos? ¿Cómo lo mides? | Cap. 1, criterios de éxito + Cap. 8, resultados por objetivo + Cap. 9, tabla de cumplimiento |
| 10 | ¿Hubo desviaciones en la planificación? ¿Por qué? | Cap. 3, horas estimadas vs. reales y seguimiento de riesgos |
| 11 | ¿Qué medidas de seguridad / protección de datos aplicaste? | Cap. 4, RNF + Cap. 5, decisiones de diseño |
| 12 | ¿Cómo garantizaste la calidad durante el desarrollo? | Cap. 3, plan de calidad + Cap. 7, estrategia de pruebas |
| 13 | ¿Qué riesgos identificaste y cuáles se materializaron? | Cap. 3, tabla de riesgos y su seguimiento |
| 14 | ¿Cómo continuarías este trabajo? | Cap. 9, Trabajo futuro |
| 15 | ¿Cómo se instala o despliega el sistema? | Apéndice B, Manual de instalación + Cap. 6 |

Si no sabes una respuesta: **reconócelo y razona en voz alta** cómo lo
abordarías («no lo he medido, pero lo plantearía así…»). Nunca inventes: el
tribunal suele preguntar cosas cuya respuesta intuye.

## 7. Ensayo y gestión del tiempo

- **Mínimo 3 ensayos completos cronometrados**, y al menos uno ante público
  (tutor/a, compañeros, familia). El primer ensayo siempre se va de tiempo:
  por eso se ensaya.
- Grábate una vez (el móvil basta) y detecta muletillas, diapositivas donde
  te atascas y momentos en que lees la pantalla.
- Apunta **marcas de tiempo intermedias** y compruébalas en cada ensayo. Para
  15 minutos: en el minuto 5 debes estar empezando la solución (diapositiva
  7), y en el minuto 10, terminando la demo (diapositiva 9) para entrar en
  resultados (diapositiva 10) sobre el minuto 10:30. Si vas tarde en una
  marca, recorta sobre la marcha.
- **Qué recortar si te alargas** (en este orden): estado del arte, detalles
  de implementación, demo (corta al plan B en vídeo acelerado). **Nunca**
  recortes resultados ni conclusiones: son lo que el tribunal puntúa.
- Memoriza la **primera y la última frase**: son los dos momentos de más
  nervios y los que fijan la impresión general.

## 8. Checklist del día D

- [ ] Confirmado con el tribunal/secretaría el **formato pedido** (a menudo
      hay que enviar las diapositivas antes) y el tiempo exacto de exposición.
- [ ] Presentación en **PDF** (formato a prueba de fuentes y versiones) + una
      copia en PowerPoint/Keynote de respaldo. En USB **y** en la nube.
- [ ] Adaptadores **HDMI y USB-C** propios: no cuentes con que el aula tenga.
- [ ] Vídeo de la demo **descargado en local**: no dependas del wifi del aula.
- [ ] Portátil cargado, cargador en la mochila, modo «no molestar» activado.
- [ ] Llegar con **al menos 20 minutos de antelación** y probar proyector,
      sonido (si el vídeo lo lleva) y mando de diapositivas.
- [ ] Botella de agua a mano.
- [ ] Una copia impresa de la memoria (tuya, anotada) para consultar páginas
      concretas si el tribunal cita algo.

Última recomendación: el tribunal no busca pillarte; busca comprobar que el
trabajo es tuyo y que entiendes lo que has hecho. Todo lo que necesitas para
demostrarlo ya está escrito en tu memoria. Suerte — aunque con esta
preparación hará falta poca.
