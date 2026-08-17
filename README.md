# 📘 Lógica y Conjuntos — Libro Digital Interactivo

[![Ver Libro Interactivo en Vivo](https://img.shields.io/badge/Ver-Libro%20Interactivo%20en%20Vivo-blue?style=for-the-badge&logo=githubpages)](https://PabloeCancino.github.io/uan-logica-conjuntos-descartes/)
[![Norma](https://img.shields.io/badge/Norma-NTE--UAN--APK--001%20v1.3-purple?style=for-the-badge)](https://github.com/PabloeCancino)
[![Red Descartes](https://img.shields.io/badge/Red-Descartes-green?style=for-the-badge)](https://proyectodescartes.org/)
[![Licencia](https://img.shields.io/badge/Licencia-CC%20BY--NC--SA%204.0-orange?style=for-the-badge)](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.es)

Libro Digital Interactivo y conjunto de **Escenas HTML5 / DescartesJS / GeoGebra** para la enseñanza y aprendizaje autónomo de la asignatura **Lógica y Conjuntos (CBIMAT-215)** de la Licenciatura en Matemáticas en la **Universidad Autónoma de Nayarit**.

Desarrollado bajo el motor **iCartesiLibri** de la **Red Educativa Digital Descartes** e **IMAT - UNAM** en conformidad con la norma institucional **NTE-UAN-APK-001 v1.3**.

---

## 🎯 Características Principales

- 📖 **Estructura Paginada eBook:** Maquetación HTML5 responsiva tipo libro con tabla de contenidos dinámica, temas claro/oscuro y numeración automática.
- 📐 **Renderizado Matemático KaTeX:** Expresiones LaTeX en línea \(\( ... \)\) y en bloque \(\$\$ ... \$\$\) ultrarrápidas y accesibles.
- 🧪 **Escenas e Interactivos HTML5 (Evolución de Applets Java):**
  - **Simulador de Demostraciones Paso a Paso (`interactivos/simulador_demostraciones.html`):** Visualizador formal de deducción matemática con 12 teoremas, justificaciones axiomáticas, reproducción automática (Auto/Pausa) y notación KaTeX.
  - **Simulador SVG de Diagramas de Venn (`interactivos/simulador_venn.html`):** Motor avanzado de 19 operaciones para 2 y 3 conjuntos (\(A, B, C\)) con máscaras booleanas exactas (`#maskExterior2`, `#maskExterior3`) y exploración manual atómica.
  - **Evaluador de Tablas de Verdad (`interactivos/tablas_verdad.html`):** Construcción interactiva celda a celda con detección automática de Tautologías y Contradicciones.
  - **Evaluador Autocorregible DescartesJS (`interactivos/evaluador_descartes.html`):** Banco ampliado de 24 reactivos clasificados en 4 módulos curriculares, con retroalimentación paso a paso.
  - **GeoGebra Web API (`interactivos/geogebra_logica.html`):** Applet dinámico de geometría de conjuntos y circuitos lógicos.
- ♿ **Accesibilidad Tipográfica:** Controles integrados de escalado dinámico de fuente (7 niveles, desde `0.85x` hasta `2.00x`).
- 📶 **100% Offline & Multiplataforma:** No requiere plugins de Java ni conexión activa a internet tras abrir la página.

---

## 📁 Estructura del Repositorio

```
.
├── index.html                       # Libro Interactivo Paginado Principal
├── book-min.js                      # Motor iCartesiLibri (Joel Espinosa Longi / UNAM)
├── README.md                        # Documentación del Proyecto
├── extra/                           # Fuentes web, estilos CSS y biblioteca KaTeX
│   ├── katex/
│   │   ├── katex.min.js
│   │   ├── katex.min.css
│   │   └── contrib/auto-render.min.js
│   └── fonts.css
├── interactivos/                    # Escenas HTML5 e Interactivos Incrustados
│   ├── simulador_demostraciones.html# Simulador de Demostraciones Paso a Paso
│   ├── simulador_venn.html          # Simulador SVG de Diagramas de Venn (19 operaciones)
│   ├── tablas_verdad.html           # Evaluador de Tablas de Verdad
│   ├── evaluador_descartes.html     # Quiz Autocorregible DescartesJS (24 reactivos)
│   └── geogebra_logica.html         # Applet GeoGebra HTML5
└── images/                          # Logotipos e imágenes vectoriales
```

---

## 🚀 Ejecución y Visualización

### 🌐 Ver en Vivo (GitHub Pages)
Ingresa al enlace de producción: **[https://PabloeCancino.github.io/uan-logica-conjuntos-descartes/](https://PabloeCancino.github.io/uan-logica-conjuntos-descartes/)**

### 💻 Ejecución Local
Simplemente descarga o clona el repositorio y abre `index.html` en cualquier navegador web moderno (Chrome, Firefox, Edge, Safari):

```bash
git clone https://github.com/PabloeCancino/uan-logica-conjuntos-descartes.git
cd uan-logica-conjuntos-descartes
```

---

## 📄 Créditos e Investigación Docente

### Universidad Autónoma de Nayarit (UAN)
- **Unidad Académica de Ciencias Básicas e Ingenierías**
- **Licenciatura en Matemáticas**
- **Dr. Pablo Eduardo Cancino Marentes** — *Investigador Responsable / Desarrollo APK y Libro Interactivo*
- **Dr. Sergio Enrique Yarza Acuña** — *Investigador Colaborador / Diseño Curricular*
- **Ayrton Ortega Hernández** — *Colaboración Estudiantil*
- **Luis Angel Caro Madera** — *Colaboración Estudiantil*

### Red Educativa Digital Descartes
- **Motor iCartesiLibri:** Joel Espinosa Longi (Instituto de Matemáticas UNAM).

---

## 📜 Licencia

Obra publicada bajo la licencia **Creative Commons Atribución-NoComercial-CompartirIgual 4.0 Internacional (CC BY-NC-SA 4.0)**.
