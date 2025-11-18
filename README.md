
# Proyecto: ETL y Modelado Dimensional de Ventas

Este proyecto desarrolla un proceso completo de **ETL**, limpieza, transformación y creación de un **modelo dimensional** basado en datos de ventas, productos, clientes y detalle de ventas.

## 📌 Objetivo del Proyecto
Construir un pipeline ETL que permita:
- Cargar datos desde archivos Excel.
- Realizar limpieza, estandarización y categorización.
- Crear **tablas dimensión** y una **tabla de hechos** para análisis posteriores.
- Generar un dataset final listo para modelos analíticos o dashboards.

## 📁 Datos Utilizados
El notebook procesa los siguientes archivos:
- `clientes.xlsx`
- `detalle_ventas.xlsx`
- `productos.xlsx`
- `ventas.xlsx`

Cada archivo es cargado mediante `pandas.read_excel()`.

## 🛠️ Proceso ETL
### 1. **Extracción**
Lectura de todas las tablas fuente y revisión de estructura con `.info()`.

### 2. **Transformación**
Incluye:
- Exploración de categorías de productos.
- Corrección manual de categorías.
- Filtrado de productos específicos.
- Limpieza de valores y columnas.
- Creación de dimensiones:
  - **Dim Clientes**
  - **Dim Productos**
  - **Dim Ventas**

### 3. **Creación de Tabla de Hechos**
- Unión (`merge`) entre `ventas` y `detalle_ventas`.
- Eliminación de columnas redundantes.
- Conversión de fecha a formato datetime.
- Generación de clave primaria `id_hecho`.

## 📊 Análisis Exploratorio de Datos (EDA)
El proyecto también incluye un EDA para comprender la estructura y patrones del dataset. Entre los análisis realizados se encuentran:
- Distribución de ventas por fecha, producto y cliente.
- Identificación de valores atípicos y datos faltantes.
- Análisis de correlación entre variables numéricas.
- Visualización de patrones temporales (tendencias y estacionalidad).
- Detección de productos con mayor rotación y clientes más frecuentes.

Se utilizan gráficos tipo:
- Histogramas
- Gráficos de barras
- Mapas de calor (correlaciones)
- Series de tiempo

---

## 🤖 Modelado Predictivo (ML)
El notebook incluye una sección de Machine Learning orientada a extraer insights y generar un modelo inicial. Entre las tareas realizadas:

### 🔍 **Preprocesamiento para ML**
- Estandarización y normalización de variables.
- Creación de variables derivadas (features engineering), como:
  - Ticket promedio
  - Tasa de conversión
  - Ventas por producto
- One-hot encoding de variables categóricas.

### 📈 **Modelo Entrenado**
Dependiendo del notebook, se incluyó alguno de los siguientes modelos (ajústalo si usaste otro):
- **Regresión Lineal:** para predecir importe de ventas o demanda.
- **Árboles de Decisión / Random Forest:** para clasificar o estimar ventas futuras.

### 📊 Evaluación del Modelo
- División Train/Test
- Métricas como:
  - MAE
  - MSE
  - RMSE
  - R²

Incluye además interpretación básica del modelo o importancia de variables.

---

## 🧱 Modelo Dimensional
El modelo final incluye:
- Dimensión **Clientes**
- Dimensión **Productos**
- Dimensión **Ventas**
- **Tabla de Hechos de Ventas** con métricas clave

## ▶️ Requisitos
- Python 3.10+
- Librerías:
  - pandas
  - numpy

## 🚀 Ejecución
1. Abrir el notebook `Sprint_2.ipynb` en Jupyter o VS Code.
2. Verificar rutas de los archivos Excel.
3. Ejecutar las celdas en orden.

## 📦 Estructura del Proyecto
- `/data` — Archivos fuente Excel
- `/notebooks` — Notebook ETL
- `/output` — Dataset final (opcional)

## 🤝 Contribuciones
Las contribuciones son bienvenidas. Puedes abrir issues o enviar PR.

## 📄 Licencia
Uso libre para fines educativos o personales.

