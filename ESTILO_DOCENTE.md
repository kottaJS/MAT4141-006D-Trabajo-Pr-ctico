# Guía de Estilo de Programación del Docente (MAT4141)

> **REGLA OBLIGATORIA DEL PROYECTO:**  
> Todo código en Python y Jupyter Notebook (`.ipynb`) generado para este trabajo debe imitar fielmente el estilo, convenciones, sintaxis, nombres de variables y estructura pedagógica utilizados por el profesor en las soluciones de los Laboratorios 0, 1, 2 y 3.

---

## 1. Filosofía y Estructura General
1. **Comentarios explicativos paso a paso:**  
   El docente siempre coloca comentarios directos antes de cada bloque de código explicando qué se está haciendo (ej. `# Bibliotecas`, `# Creación de DataFrame (DF)`, `# Variables`, `# Gráfico`, `# Personalización`).
2. **Cálculo de muestra explícito:**  
   Siempre se obtiene el tamaño de muestra con `.shape[0]` y se almacena en una variable explícita:
   ```python
   muestra = df.shape[0] # Número de filas
   muestra
   ```
3. **Exploración inicial estándar:**  
   Siempre se usa `df.head(5)`, `df.tail(5)` y `df['Columna'].unique()`.
4. **Redondeo formal:**  
   Uso recurrente de `round(tabla, 1)` para presentar resultados limpios a un decimal.

---

## 2. Construcción de Tablas de Frecuencia

### A. Variables Cualitativas / Discretas (Nominales y Ordinales)
Se utiliza `groupby().size()` para obtener frecuencias absolutas y se construye explícitamente un `pd.DataFrame`:
```python
# Frecuencia absoluta
cuenta_categoria = df.groupby('Categoría').size()

# Creación de DF con frecuencias absolutas y relativas
tabla_1 = pd.DataFrame({
    'Frecuencia absoluta': cuenta_categoria,
    'Frecuencia relativa (%)': round(cuenta_categoria / muestra * 100, 1)
})

# Ordenamiento (cuando aplica)
tabla_1.sort_values('Frecuencia absoluta', ascending=False)
```

### B. Variables con Frecuencias Acumuladas
Para variables que admiten orden o conteo:
```python
cuenta_var = df.groupby('Variable').size()

tabla_acum = pd.DataFrame({
    'Frecuencia absoluta': cuenta_var,
    'Frecuencia absoluta acumulada': cuenta_var.cumsum(),
    'Frecuencia relativa (%)': cuenta_var / muestra * 100,
    'Frecuencia relativa acumulada (%)': (cuenta_var / muestra * 100).cumsum()
})
round(tabla_acum, 1)
```

### C. Variables Cuantitativas Continuas (Intervalos de Clase)
El docente usa de forma estándar `pd.cut()` con argumentos obligatorios:
* `bins`: número de intervalos (ej. 8, 9, 10).
* `include_lowest=True`: para incluir el valor mínimo en el primer intervalo.
* `precision`: precisión de los límites (0, 1 o 2).
* `observed=True` en `groupby()`: para evitar advertencias de compatibilidad futura en pandas con variables categóricas.

```python
# Crearemos una nueva columna con los intervalos
df['Intervalos_var'] = pd.cut(df['Variable_continua'], bins=10, include_lowest=True, precision=0)

# Frecuencia absoluta con observed=True
cuenta_intervalos = df.groupby('Intervalos_var', observed=True).size()

tabla_int = pd.DataFrame({
    'Frecuencia absoluta': cuenta_intervalos,
    'Frecuencia absoluta acumulada': cuenta_intervalos.cumsum(),
    'Frecuencia relativa (%)': cuenta_intervalos / muestra * 100,
    'Frecuencia relativa acumulada (%)': (cuenta_intervalos / muestra * 100).cumsum()
})
round(tabla_int, 1)
```

---

## 3. Estilo de Gráficos (Matplotlib Orientado a Objetos)

El profesor utiliza consistentemente la API orientada a objetos de `matplotlib.pyplot` (`fig, ax = plt.subplots(...)`) con una estructura en 4 bloques:

### A. Gráfico de Barras
```python
# Biblioteca
import matplotlib.pyplot as plt

# Variables
categorias = tabla.index
frecuencias = tabla['Frecuencia absoluta'] # o relativa (%)

# Gráfico
fig, ax = plt.subplots(figsize=(7, 5))
barras = ax.bar(categorias, frecuencias, color='teal', edgecolor='black')

# Personalización
ax.set_title('Título descriptivo del gráfico')
ax.set_xlabel('Etiqueta eje X')
ax.set_ylabel('Cantidad de observaciones')
ax.bar_label(barras) # O con porcentaje: ax.bar_label(barras, fmt='%.1f%%')
plt.xticks(rotation=45, ha='right') # Rota en 45° las categorías para evitar superposición

plt.show()
```

### B. Histograma (Construido con las barras de los intervalos)
El profesor genera histogramas graficando directamente las frecuencias de los intervalos calculados con `pd.cut()` usando `width=1`:
```python
# Variables
categorias_intervalo = cuenta_intervalos.index
frecuencias_int = cuenta_intervalos # o tabla['Frecuencia relativa (%)']

# Gráfico
fig, ax = plt.subplots(figsize=(7, 5))
histograma = ax.bar(categorias_intervalo.astype(str), frecuencias_int, color='tomato', edgecolor='black', width=1)

# Personalización
ax.set_title('Distribución de Variable por Intervalos')
ax.set_xlabel('Variable (unidades)')
ax.set_ylabel('Frecuencia')
ax.bar_label(histograma)
plt.xticks(rotation=45, ha='right')

plt.show()
```

### C. Gráfico Circular (Pie Chart)
```python
# Variables
categorias = tabla.index
h = tabla['Frecuencia relativa (%)']

# Gráfico
fig, ax = plt.subplots(figsize=(6, 4))
circular = ax.pie(h, labels=categorias, autopct='%.1f%%')

# Personalización
ax.set_title('Distribución porcentual de Variable')

plt.show()
```

### D. Gráficos Múltiples (Subplots en una fila)
```python
fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(14, 6))

ax1.pie(h, labels=categorias, autopct='%.1f%%')
ax1.set_title('Distribución porcentual')

barras = ax2.bar(categorias, f, color='b', edgecolor='black')
ax2.set_title('Distribución absoluta')
ax2.set_xlabel('Categoría')
ax2.set_ylabel('Cantidad')
ax2.bar_label(barras)

plt.show()
```

### E. Gráfico de Dispersión (Scatter Plot)
```python
plt.figure(figsize=(10, 6))
plt.scatter(df['Variable_X'], df['Variable_Y'], alpha=0.7)
plt.title('Relación entre Variable X y Variable Y')
plt.xlabel('Variable X')
plt.ylabel('Variable Y')
plt.grid(True)
plt.show()
```

---

## 4. Medidas Estadísticas de Resumen (Pandas y NumPy)
* **Media:** `df['col'].mean()`
* **Mediana:** `df['col'].median()`
* **Moda:** `df['col'].mode()[0]`
* **Desviación Estándar:** `df['col'].std()`
* **Varianza:** `df['col'].var()`
* **Cuartiles y Percentiles:** `df['col'].quantile([0.25, 0.5, 0.75])`
* **Rango Intercuartílico (IQR):** `Q3 - Q1`
* **Resumen descriptivo global:** `round(df[['col1', 'col2']].describe(), 1)`
