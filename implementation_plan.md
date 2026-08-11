# Plan de Desarrollo — Material de Lógica y Conjuntos (Proyecto Descartes & NTE-UAN-APK-001)

## Resumen del Diagnóstico y Análisis Revisitado

Tras revisar las estructuras de ambos proyectos:

1. **`E:\Desarrollo_de_APK\Proyecto_Descartes`**:
   - Contiene la plantilla **iCartesiLibri (`libro_interactivo`)** desarrollada por el **IMAT-UNAM / Red Educativa Digital Descartes** (Joel Espinosa Longi).
   - Es un motor HTML5 paginado tipo eBook con tabla de contenidos dinámica, numeración automática de capítulos/secciones, temas claro/oscuro, fórmulas matemáticas con KaTeX (`katex.min.js`) y soporte para incrustar escenas interactivas de **DescartesJS** o **GeoGebra**.

2. **`E:\Desarrollo_de_APK\Teoria_de_Conjuntos`**:
   - Aplicación interactiva ya avanzada en **React 19 + Vite + Capacitor**, alineada a la norma institucional **NTE-UAN-APK-001 v1.3** (Universidad Autónoma de Nayarit, CBIMAT-215).
   - Cuenta con una base sólida en `src/data/contenido.js`:
     - **3 Módulos:** *Lógica Proposicional*, *Teoría de Conjuntos* y *Métodos de Demostración*.
     - **16 Temas estructurados:** con definiciones, notación $\text{\LaTeX}$ KaTeX y notas clave.
     - **Simuladores Interactivos Nativo SVG:** `VennSVG.jsx` (8 operaciones entre conjuntos) y `GrafoSVG.jsx`.
     - **40 Reactivos de Evaluación (Quizzes):** Clasificados por nivel de dificultad con retroalimentación detallada e interpretación paso a paso.
     - **Accesibilidad:** 7 niveles de escalado dinámico de fuente (0.85x a 2.00x).
     - **Generación Offline / APK:** Compilado mediante Capacitor a Android APK (`Teoria_de_Conjuntos.apk`).

---

## Estrategia Propuesta: Enfoque Dual (APK Nativa + Libro Interactivo Descartes)

Proponemos aprovechar la riqueza del contenido en `Teoria_de_Conjuntos` para ofrecer una solución integral en dos formatos complementarios:

1. **Versión A — App Móvil APK & PWA Web (React 19 + Capacitor)**:
   - Mantener y compilar la APK Android nativa y PWA web bajo la norma **NTE-UAN-APK-001 v1.3**.
   - Garantizar la visualización matemática (KaTeX), accesibilidad tipográfica, quizes interactivos y simulación gráfica de Venn nativa en SVG.

2. **Versión B — Libro Digital Interactivo iCartesiLibri (Proyecto Descartes)**:
   - Exportar/adaptar la estructura curricular de `contenido.js` a la plantilla paginada `index.html` del **Proyecto Descartes**.
   - Organizar por Capítulos y Secciones HTML5 con KaTeX precargado y cuadros interactivos incrustados (ejercicios interactivos, applets GeoGebra y evaluadores DescartesJS).

---

## User Review Required

> [!IMPORTANT]
> **Decisión de Formato Principal o Dual:**
> ¿Deseas que trabajemos primariamente en la versión **APK Android / Web App React** (`Teoria_de_Conjuntos`), generemos también la versión **Libro Digital HTML5 iCartesiLibri** (`Proyecto_Descartes`), o ambas simultáneamente?

> [!NOTE]
> La versión React en `Teoria_de_Conjuntos` ya tiene el 100% de la lógica de evaluación, simulador Venn SVG y 40 quizzes programados en `contenido.js`. La versión Descartes requerirá adaptar estos datos a páginas HTML5 paginadas.

---

## Proposed Changes

### Componente 1: Aplicación React / APK (`E:\Desarrollo_de_APK\Teoria_de_Conjuntos`)

#### [MODIFY] [contenido.js](file:///E:/Desarrollo_de_APK/Teoria_de_Conjuntos/src/data/contenido.js)
- Revisar y pulir las 16 lecciones en notación KaTeX (asegurando el correcto escape `\\( ... \\)` según las normas globales).
- Verificar que las 40 preguntas del banco de quizzes cubran uniformemente Lógica Proposicional, Teoría de Conjuntos y Métodos de Demostración.

#### [MODIFY] [VennSVG.jsx](file:///E:/Desarrollo_de_APK/Teoria_de_Conjuntos/src/components/VennSVG.jsx)
- Optimizar la interactividad de la representación de regiones (Unión, Intersección, Diferencia, Complemento, Diferencia Simétrica).

#### [MODIFY] [App.jsx](file:///E:/Desarrollo_de_APK/Teoria_de_Conjuntos/src/App.jsx)
- Confirmar el renderizado con KaTeX en todas las vistas de temas, explicaciones y opciones de examen.

---

### Componente 2: Libro Interactivo Descartes (`E:\Desarrollo_de_APK\Proyecto_Descartes`)

#### [NEW] [index.html](file:///E:/Desarrollo_de_APK/Proyecto_Descartes/libro_interactivo_logica_conjuntos/index.html)
- Crear una estructura paginada `iCartesiLibri` basada en `libro_interactivo-master/ejemplos/libro_interactivo_katex`.
- Organizar el contenido en:
  - **Capítulo 1:** Lógica Proposicional (Proposiciones, Operaciones Lógicas, Argumentos, Reglas de Inferencia).
  - **Capítulo 2:** Teoría de Conjuntos (Pertenencia, Notación, Operaciones, Conjunto Vacío/Universal, Producto Cartesiano, Potencia, Contención).
  - **Capítulo 3:** Métodos de Demostración (Prueba Directa, Contrapositiva, Contradicción, Inducción).
  - **Sección Interactiva / Evaluaciones:** Escenas interactivas incrustadas.

#### [NEW] [extra/style.css](file:///E:/Desarrollo_de_APK/Proyecto_Descartes/libro_interactivo_logica_conjuntos/extra/style.css)
- Aplicar la paleta de colores institucional y tipografías para la Red Descartes.

---

## Verification Plan

### Automated Tests
- Ejecutar `npm run build` en `Teoria_de_Conjuntos` para asegurar cero errores de JSX/Vite/ESLint.
- Ejecutar scripts de validación de sintaxis KaTeX y UTF-8 no-BOM en PowerShell.

### Manual Verification
- Probar la Web App en `localhost` mediante `npm run dev` revisando:
  1. Renderizado perfecto de fórmulas KaTeX sin texto en rojo ni barras escapadas erróneas.
  2. Funcionamiento fluido del simulador de Diagramas de Venn SVG.
  3. Escalado tipográfico en los 7 niveles (0.85x a 2.00x).
  4. Flujo de evaluación en los Quizzes con retroalimentación inmediata.
- En la versión Descartes: Abrir `index.html` en el navegador para comprobar la paginación, tabla de contenidos flotante y renderizado de KaTeX.
