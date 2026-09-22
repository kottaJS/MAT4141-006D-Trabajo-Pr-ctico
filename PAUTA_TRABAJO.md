# Pauta y Rúbrica del Trabajo de Estadística Aplicada

## 1. Descripción General del Trabajo
El objetivo de este trabajo es aplicar los conceptos y herramientas aprendidos en la asignatura para **explorar y analizar una base de datos obtenida del mundo real** a través de gráficos, tablas y medidas resúmenes.

* **Modalidad:** Equipos de 3 o 4 personas (o grupos de 3 estudiantes según la indicación del docente).
* **Base de Datos Oficial:** `data/05_MATRICULAS_ED_SUPERIOR_COQUIMBO_2021.xlsx` (Región de Coquimbo, año 2021).
* **Herramienta de análisis:** Google Colab / Jupyter Notebook (`.ipynb`) en Python.
* **Estilo de Programación Obligatorio:** Debe seguir el formato pedagógico del profesor visto en los Laboratorios 0 a 3 (ver [ESTILO_DOCENTE.md](file:///c:/Users/maxip/Desktop/Proyectos/MATEMATICAS/ESTILO_DOCENTE.md)).
* **Herramienta de síntesis:** Presentación en diapositivas (PPT) o Infografía.
* **Evaluación:** Rúbrica analítica de 100 puntos totales, escala 1.0 a 7.0 con 60% de exigencia.

---

## 2. Etapas del Proyecto

| Etapa | Descripción |
| :--- | :--- |
| **Etapa 1** | Desarrollar los **Ítems 1 y 2** en Google Colab (`.ipynb`), utilizando la base de datos entregada por el docente. |
| **Etapa 2** | Diseñar un **PowerPoint (PPT) o Infografía** que sintetice con claridad los análisis estadísticos más relevantes. |
| **Etapa 3** | **Entregar el archivo `.ipynb`** con el desarrollo completo de los ítems 1 y 2 dentro del plazo establecido. |
| **Etapa 4** | **Exponer los resultados** y análisis obtenidos ante el docente utilizando el PPT o infografía como apoyo visual. |

---

## 3. Instrucciones y Requerimientos Específicos

### Ítem 1: Análisis Descriptivo General
Describir de modo general el conjunto de datos a partir de un **análisis descriptivo de cada una de las variables más relevantes** para este fin. Deberá comentar cada resultado, gráfico o tabla según los aspectos que considere más interesantes o relevantes, registrando por escrito dichos comentarios.

El análisis descriptivo debe incluir obligatoriamente:
1. **Gráficos:** Gráficos pertinentes para cada tipo de variable (histogramas, diagramas de caja/boxplot, gráficos de barras, diagramas de dispersión, etc.).
2. **Tablas de frecuencia:** Tablas unidimensionales y/o tablas cruzadas (bivariadas) con una o más variables.
3. **Medidas de tendencia central:** Media aritmética, mediana, moda.
4. **Percentiles:** Cuartiles ($Q_1, Q_2, Q_3$), percentiles relevantes para detectar concentración y distribución.
5. **Medidas de dispersión:** Desviación estándar, varianza, rango intercuartílico (IQR), rango total, coeficiente de variación ($CV$).
6. **Otros resúmenes:** Asimetría, curtosis o resúmenes agrupados según corresponda.
7. **Comentarios e interpretaciones escritas:** Cada salida estadística debe estar explicada formalmente en el notebook.

---

### Ítem 2: Preguntas de Investigación y Justificación
Investigar y responder con fundamento cuantitativo y justificación clara las siguientes interrogantes:

1. **¿Hay áreas del conocimiento donde las carreras sean más caras?**
   * *Requerimiento:* Explicar con claridad qué criterio estadístico y metodológico se diseñó para responder la pregunta (ej. comparación de medianas/medias por área, análisis de variabilidad, boxplots comparativos).
2. **¿Qué influencia tiene la edad en el tipo de institución a la que ingresan los estudiantes?**
   * *Requerimiento:* Analizar la distribución etaria según tipo de institución (Universidades Estatales/Privadas, Institutos Profesionales, Centros de Formación Técnica), evaluando patrones de edad, dispersión y perfiles de ingreso.
3. **¿Hay carreras cuyo arancel sea sustantivamente más caro que la mayoría de los aranceles? ¿Qué explicación pueden encontrar?**
   * *Requerimiento:* Identificar valores atípicos (outliers) o carreras en los percentiles superiores extremos. Considerar variables auxiliares de la base de datos (duración, campo laboral, equipamiento, acreditación) y el contexto de la región que tocó trabajar.

---

## 4. Escala de Calificación
* **Escala:** 1.0 a 7.0
* **Puntaje Total:** 100 puntos
* **Nivel de Exigencia:** 60% (60 puntos equivalen a la nota de aprobación 4.0).

---

## 5. Rúbrica de Evaluación

| Indicadores de Logro | Excelente | Bueno | Regular | Insuficiente | No logrado |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Entrega de archivo en formato .ipynb** | Se entrega el archivo en formato `.ipynb` asociado al trabajo de forma oportuna y de la forma indicada por el docente.<br><br>**5 puntos** | Se entrega el archivo en formato `.ipynb` asociado al trabajo con un día de retraso o menos y de la forma indicada por el docente.<br><br>**4 puntos** | Se entrega el archivo en formato `.ipynb` asociado al trabajo con más de un día de retraso y no cumple con la forma solicitada por el docente.<br><br>**2,6 puntos** | No entrega el archivo.<br><br><br><br>**0 puntos** | **0 puntos** |
| **Exposición de los resultados** | Los resultados se presentan siempre de manera lógica y coherente y se utiliza un lenguaje técnico y formal.<br><br>**20 puntos** | Los resultados se presentan generalmente de manera lógica y coherente y se utiliza un lenguaje técnico, pero no formal.<br><br>**16 puntos** | Los resultados se presentan escasamente de manera lógica y coherente, y no utiliza ni lenguaje técnico ni formal.<br><br>**10,4 puntos** | Los resultados no se presentan de manera lógica y coherente, y no utiliza ni lenguaje técnico ni formal.<br><br>**4,8 puntos** | **0 puntos** |
| **Interpretación de resultados estadísticos** | Los resultados se interpretan correctamente a la luz del análisis presentado, sin errores.<br><br>**25 puntos** | Los resultados se interpretan adecuadamente a la luz del análisis presentado, cometiendo uno o dos errores.<br><br>**20 puntos** | Los resultados se interpretan parcialmente a la luz del análisis presentado, cometiendo tres o más errores.<br><br>**13 puntos** | No se evidencia una interpretación correcta de los resultados obtenidos del análisis de los datos.<br><br>**6 puntos** | No evidencia desarrollo alguno con relación a lo solicitado.<br><br>**0 puntos** |
| **Selección y cálculo de herramientas estadísticas** | Selecciona adecuadamente las herramientas de estadística y realiza el cálculo correcto de todas.<br><br>**25 puntos** | Selecciona parcialmente herramientas de estadística adecuadas y realiza el cálculo correcto de éstas.<br><br>**20 puntos** | Selecciona algunas herramientas de estadística adecuadas, presentando errores de cálculo de éstas.<br><br>**13 puntos** | No selecciona ni herramientas de estadística ni realiza cálculos correctos.<br><br>**6 puntos** | No evidencia desarrollo alguno con relación a lo solicitado.<br><br>**0 puntos** |
| **Evaluación del desempeño individual** | El estudiante evidencia un conocimiento total de la temática del trabajo, respondiendo la pregunta claramente y sin errores.<br><br>**25 puntos** | El estudiante evidencia un conocimiento general de la temática del trabajo, respondiendo la pregunta con un error.<br><br>**20 puntos** | El estudiante evidencia un conocimiento escaso de la temática del trabajo, respondiendo la pregunta con 2 errores.<br><br>**13 puntos** | El estudiante no responde las preguntas planteadas o bien, las responde de forma completamente errónea.<br><br>**6 puntos** | No evidencia desarrollo alguno con relación a lo solicitado.<br><br>**0 puntos** |

---

## 6. Puntos Críticos para Obtener el Puntaje Máximo (100 pts)
1. **Elección de Estadígrafos:** Emplear tanto medidas para variables cualitativas (tablas de frecuencia absolutas, relativas y porcentuales, gráficos de barras o sectores) como para variables cuantitativas (media, mediana, desviación estándar, rango intercuartílico, boxplots, histogramas).
2. **Justificación Metodológica:** En el Ítem 2, explicitar con qué estadígrafo se compara (e.g. preferir la mediana si los aranceles presentan sesgo o asimetría positiva con valores extremos).
3. **Interpretaciones Contextualizadas:** No limitar el trabajo a pegar tablas numéricas; cada tabla o gráfico debe tener su párrafo explicativo interpretando el fenómeno en el contexto regional y educativo chileno.
4. **Preparación Individual:** Como 25 puntos corresponden a la defensa individual ante la pregunta del docente, cada integrante debe comprender a cabalidad todo el código y análisis realizado.
