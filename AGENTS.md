# Instrucciones y Contexto Permanente del Proyecto: MATEMATICAS (MAT4141)

Este archivo define las reglas, contexto, estructura y estándares obligatorios para el proyecto de análisis estadístico de educación superior.

## REGLA CRÍTICA: Programar en el Estilo del Docente
**Todo código Python generado en este proyecto debe replicar fielmente el estilo de programación del profesor visto en los Laboratorios 0, 1, 2 y 3 (disponibles en `laboratorios_profe/` y documentados en [ESTILO_DOCENTE.md](file:///c:/Users/maxip/Desktop/Proyectos/MATEMATICAS/ESTILO_DOCENTE.md)).**

Lineamientos de código del docente:
1. **Comentarios sistemáticos paso a paso:** `# Bibliotecas`, `# Creación de DataFrame (DF)`, `# Variables`, `# Gráfico`, `# Personalización`, `plt.show()`.
2. **Cálculo de muestra:** `muestra = df.shape[0]` explícito al inicio.
3. **Tablas de frecuencias:**
   - Cualitativas: `cuenta = df.groupby('col').size()`, crear `pd.DataFrame({'Frecuencia absoluta': ..., 'Frecuencia relativa (%)': round(... / muestra * 100, 1)})`.
   - Intervalos de clase: `df['Intervalos_col'] = pd.cut(df['col'], bins=k, include_lowest=True, precision=p)`, agrupación con `df.groupby('Intervalos_col', observed=True).size()`, y columnas `cumsum()` para frecuencias acumuladas.
4. **Gráficos en Matplotlib Orientado a Objetos:**
   - `fig, ax = plt.subplots(figsize=(...))`
   - `ax.bar(categorias, f, color='...', edgecolor='black')`
   - Etiquetas directas en las barras con `ax.bar_label(barras)`
   - Rotación y alineación con `plt.xticks(rotation=45, ha='right')`
   - Histogramas construidos a partir de los intervalos de `pd.cut()` con `width=1`.
   - Gráficos circulares con `ax.pie(h, labels=categorias, autopct='%.1f%%')`.
5. **Redondeo:** `round(tabla, 1)` estándar.

## Estructura de Carpetas del Proyecto
- `data/`: Contiene la base de datos oficial (`05_MATRICULAS_ED_SUPERIOR_COQUIMBO_2021.xlsx`).
- `laboratorios_profe/`: Cuadernos de referencia con las soluciones del docente (`Soluciones_Laboratorio 0` al `3`).
- `notebooks/`: Cuadernos Jupyter para el desarrollo del trabajo grupal.
- `PAUTA_TRABAJO.md`: Pauta completa, preguntas de investigación y rúbrica oficial de 100 puntos.
- `ESTILO_DOCENTE.md`: Guía de código y sintaxis del profesor.
- `README.md`: Resumen y presentación del repositorio.

## Repositorio Remoto Oficial
- **URL GitHub:** `https://github.com/kottaJS/MAT4141-006D-Trabajo-Pr-ctico.git`
- Rama principal: `main`.

## Etapas del Proyecto
1. **Etapa 1:** Desarrollo en Google Colab / Jupyter Notebook (`.ipynb`) de los Ítems 1 y 2 con Python siguiendo el estilo del profesor.
2. **Etapa 2:** Diseño de presentación PPT / Infografía síntesis.
3. **Etapa 3:** Entrega formal del archivo `.ipynb` dentro del plazo.
4. **Etapa 4:** Exposición de resultados con defensa individual de preguntas del docente.

## Contenido de los Ítems
- **Ítem 1 (Análisis Descriptivo):**
  - Gráficos estadísticos claros y rotulados.
  - Tablas de frecuencia (unidimensionales y bivariadas).
  - Medidas de tendencia central (media, mediana, moda).
  - Percentiles y cuartiles.
  - Medidas de dispersión (desviación estándar, varianza, IQR, CV).
  - Otros resúmenes e interpretación escrita obligatoria de cada resultado.
- **Ítem 2 (Preguntas de Investigación):**
  - ¿Hay áreas del conocimiento donde las carreras sean más caras? (Diseñar y fundamentar el criterio estadístico, considerando sesgo/outliers).
  - ¿Qué influencia tiene la edad en el tipo de institución a la que ingresan los estudiantes? (Distribuciones por tipo de institución).
  - ¿Hay carreras cuyo arancel sea sustantivamente más caro que la mayoría? (Outliers extremos, variables auxiliares y contexto de la región de Coquimbo).

## Criterios de la Rúbrica (Objetivo: 100 puntos / Nota 7.0)
- **Entrega `.ipynb` (5 pts):** Formato limpio, ejecutable de arriba a abajo, ordenado con markdown explicativo.
- **Exposición de resultados (20 pts):** Lenguaje técnico, formal, lógica deductiva clara.
- **Interpretación de resultados estadísticos (25 pts):** Cero errores en interpretar estadígrafos y gráficos.
- **Selección y cálculo de herramientas estadísticas (25 pts):** Selección justificada y cálculos 100% exactos en el estilo del profesor.
- **Evaluación del desempeño individual (25 pts):** Preparar respuestas y explicaciones comprensibles para cada miembro del equipo.
