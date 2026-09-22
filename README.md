# MAT4141 - Trabajo Práctico de Estadística Aplicada

Repositorio oficial para el desarrollo del Trabajo Práctico de la asignatura de Estadística Aplicada (**MAT4141-006D**).  
El objetivo del proyecto es realizar un análisis exploratorio, descriptivo e inferencial sobre la base de datos oficial de matrículas de educación superior de la **Región de Coquimbo (Año 2021)**, aplicando herramientas en Python y sintetizando los hallazgos en un informe, cuadernos ejecutables y presentación final.

---

## 📁 Estructura del Repositorio

```text
├── data/
│   └── 05_MATRICULAS_ED_SUPERIOR_COQUIMBO_2021.xlsx   <- Base de datos asignada (Coquimbo 2021)
├── laboratorios_profe/                                <- Cuadernos modelo con soluciones del profesor
│   ├── Soluciones_Laboratorio 0_Introducción a Pandas.ipynb
│   ├── Soluciones_Laboratorio 1_Conceptos básicos de estadística.ipynb
│   ├── Soluciones_Laboratorio 2_Tablas de frecuencia.ipynb
│   └── Soluciones_Laboratorio 3_Gráficos.ipynb
├── notebooks/                                         <- Cuadernos Jupyter del trabajo (.ipynb)
├── AGENTS.md                                          <- Reglas permanentes y configuración del asistente
├── ESTILO_DOCENTE.md                                  <- Estándares y sintaxis del código del profesor
├── PAUTA_TRABAJO.md                                   <- Pauta completa de evaluación y rúbrica oficial (100 pts)
└── README.md                                          <- Descripción general del proyecto
```

---

## 📌 Etapas del Trabajo

1. **Etapa 1:** Desarrollo de los **Ítems 1 y 2** en Google Colab / Jupyter Notebook (`.ipynb`).
2. **Etapa 2:** Diseño de presentación en PowerPoint (PPT) o Infografía síntesis.
3. **Etapa 3:** Entrega formal del archivo `.ipynb` dentro del plazo establecido.
4. **Etapa 4:** Exposición grupal de los resultados con defensa individual de preguntas del docente.

---

## 🔍 Contenido de los Ítems

### Ítem 1: Análisis Descriptivo General
* Selección de variables clave (aranceles, tipos de institución, áreas de conocimiento, edades, etc.).
* Gráficos estadísticos rotulados con la API orientada a objetos de Matplotlib (`fig, ax = plt.subplots()`).
* Tablas de frecuencia con `pd.DataFrame`, frecuencias absolutas, relativas (%) y acumuladas.
* Agrupación por intervalos continuos con `pd.cut()` y `observed=True`.
* Medidas de tendencia central (media, mediana, moda), posición (cuartiles, percentiles) y dispersión (desviación estándar, IQR, varianza, CV).
* Interpretación escrita y fundamentada de cada gráfico y tabla.

### Ítem 2: Preguntas de Investigación
1. **¿Hay áreas del conocimiento donde las carreras sean más caras?**
   * Diseño y justificación del criterio estadístico de comparación (evaluando asimetría, medianas y dispersión).
2. **¿Qué influencia tiene la edad en el tipo de institución a la que ingresan los estudiantes?**
   * Análisis comparativo de perfiles de edad según tipo de institución (Universidades, IP, CFT).
3. **¿Hay carreras cuyo arancel sea sustantivamente más caro que la mayoría?**
   * Detección de valores atípicos (outliers) extremos, apoyado en variables auxiliares y el contexto socioeconómico y productivo de la Región de Coquimbo.

---

## 💻 Convención de Código (Estilo del Docente)
Todo código desarrollado en el proyecto sigue estrictamente el estilo pedagógico demostrado en clases (ver [ESTILO_DOCENTE.md](file:///c:/Users/maxip/Desktop/Proyectos/MATEMATICAS/ESTILO_DOCENTE.md)):
* Estructura por bloques comentados (`# Bibliotecas`, `# Variables`, `# Gráfico`, `# Personalización`).
* Uso de `groupby().size()`, `pd.cut()` y `.bar_label()`.
* Redondeo formal con `round(tabla, 1)`.

---

## 📊 Rúbrica de Calificación (100 Puntos / Exigencia 60%)
* **Entrega de archivo `.ipynb`:** 5 pts
* **Exposición de los resultados:** 20 pts
* **Interpretación de resultados estadísticos:** 25 pts
* **Selección y cálculo de herramientas estadísticas:** 25 pts
* **Evaluación del desempeño individual:** 25 pts
