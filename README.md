# Proyecto Aurelión - Sistema de Análisis Predictivo

Sistema interactivo de análisis de datos para optimización de inventario en la **Tienda Aurelión**   se realizara el analisis exploratorio de los datos.
 ETL , **EDA**, limpieza, transformación y creación de un **modelo dimensional** basado en datos de ventas, productos, clientes y detalle de ventas.


## 📘 Descripción

Este proyecto fue desarrollado como parte del cursado de **Fundamentos de IA (IBM)**. Implementa un sistema de análisis predictivo para la tienda minorista ficticia *Aurelión*, que permite identificar patrones de compra y comportamiento del cliente para optimizar el surtido de productos.

---

## 🎯 Objetivo del Proyecto

Optimizar el inventario y la rentabilidad del negocio mediante:

- **Análisis exploratorio** de datos históricos de ventas.  
- **categorizar productos demandados** de los productos más rentables.  
- **Segmentación geográfica** de clientes.  
- **sistema de recomendacion** para optimizar el inventario.
- **Construir un pipeline ETL** 
    - Realizar limpieza, estandarización y categorización.
    - Crear **tablas dimensión** y una **tabla de hechos** para análisis posteriores.
    - Generar un dataset final listo para modelos De Prediccion o dashboards.

---

## ⚙️ Características Principales

- Menú interactivo con **6 opciones de análisis**.  
- Visualización de **métricas clave del negocio**.  
- **Documentación completa** del proyecto.  
- **Pseudocódigo** y **diagrama de flujo** del sistema.  
- Instrucciones para uso con **GitHub Copilot**.

---

## 🧠 Tecnologías Utilizadas

- **Python 3.8+**  
- **Pandas** → Análisis y manipulación de datos.  
- **NumPy** → Cálculos numéricos.  
- **Matplotlib** → Visualización de datos.  
- **Jupyter Notebook** → Entorno de desarrollo interactivo.

---

## 📊 Datasets Utilizados

El proyecto emplea cuatro datasets principales:

| Archivo | Registros | Descripción |
|----------|------------|-------------|
| `clientes.xlsx` | 100 | Información demográfica de clientes |
| `productos.xlsx` | 100 | Catálogo completo de productos |
| `ventas.xlsx` | 120 | Transacciones de ventas realizadas |
| `detalle_ventas.xlsx` | Variable | Detalle de ítems por transacción |

---

## 🗂️ Estructura del Proyecto

```bash
AurelionT/
├── base de datos/                  # Datasets del proyecto
│   ├── clientes.xlsx
│   ├── productos.xlsx
│   ├── ventas.xlsx
│   └── detalle_ventas.xlsx
├── proyecto_aurelion.ipynb
│   
├── requirements.txt       # Dependencias del proyecto
└── README.md              # Este archivo
```

---

## 🚀 Uso del Sistema

### Opción 1: Menú Interactivo (Recomendado)

En el Jupyter Notebook, ejecutar:

```python
ejecutar_menu()
```

### Opción 2: Comandos Directos

```python
resumen_negocio()       # Métricas generales del negocio
ventas_ciudad()         # Distribución geográfica de ventas
top_productos()         # Productos más vendidos
mostrar_documentacion() # Documentación completa
mostrar_pseudocodigo()  # Pseudocódigo y diagramas
mostrar_copilot()       # Instrucciones para Copilot
```

---

## 🧩 Instalación y Configuración



2. **Crear entorno virtual (recomendado):**  
   ```bash
   python -m venv .venv
   ```
   - Windows: `.venv\Scripts\activate`  
   - Mac/Linux: `source .venv/bin/activate`

3. **Instalar dependencias:**  
   ```bash
   pip install -r requirements.txt
   ```

4. **Ejecutar Jupyter Notebook:**  
   ```bash
   jupyter notebook
   ```

5. **Abrir el notebook:**  
   `notebooks/proyecto_aurelion.ipynb`

---

## 🧮 Funcionalidades del Menú

| Opción | Descripción |
|--------|--------------|
| 1 | **Resumen del negocio** – Métricas generales y KPIs |
| 2 | **Ventas por ciudad** – Distribución geográfica de ventas |
| 3 | **Productos más vendidos** – Top 10 productos por volumen |
| 4 | **Documentación del proyecto** – Información completa |
| 5 | **Pseudocódigo y diagrama** – Estructura y flujo del sistema |
| 6 | **Instrucciones para Copilot** – Guía de uso con IA |


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
---


## 📊 Análisis Exploratorio de Datos (EDA)
El proyecto también incluye un EDA para comprender la estructura y patrones del dataset. Entre los análisis realizados se encuentran:
- Distribución de ventas por fecha, producto y cliente.
- Identificación de valores atípicos y datos faltantes.
- Análisis de correlación entre variables numéricas ('importe_total', 'visitantes_totales', 'tasa_conversion', 'cantidad_productos','ticket_promedio').
- Visualización de patrones  (tendencias y estacionalidad).
- Detección de comportamientos a traves de diagramas de dispersion para el uso de modelos ML.

Se utilizan gráficos tipo:
- Histogramas
- Gráficos de barras
- Mapas de calor (correlaciones)
- Series de tiempo

---

## 🤖 Modelado Predictivo en desarrollo(ML)
En esta sección de Machine Learning orientada a extraer insights y generar un modelo inicial. Entre las tareas realizadas:

### 🔍 **Preprocesamiento para ML**
- Estandarización y normalización de variables.
- Creación de variables derivadas (features engineering), como:
  - visitantes_totales
   - Ticket promedio
  - Tasa de conversión
  - cantidad_productos
  - importe_total' (varaible a predecir)
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

### GRAFICO DE MUESTRA

![pipeline](https://github.com/user-attachments/assets/61eda20d-efb9-424e-99a2-ddeb680f3676)


## 💻 Desarrollo

Este proyecto sigue las convenciones de **Conventional Commits**:

- `feat:` → Nueva funcionalidad.  
- `fix:` → Corrección de errores.  
- `docs:` → Documentación.  
- `style:` → Formato y estilo de código.

---

## 📜 Licencia

Proyecto de uso **educativo**, desarrollado como parte del programa de **Fundamentos de IA (IBM)**

---

## 💬 ¿Preguntas o Sugerencias?

Las contribuciones son bienvenidas. Puedes abrir issues o enviar PR.

