# 📊 Interconexión y Visualización de Datos Estadísticos Oficiales

Este repositorio contiene el proyecto en proceso para la normalización, interconexión y visualización dinámica de series de tiempo estadísticas provenientes de fuentes oficiales.

---
# viz_estadistica.ipynb: Visualización Dinámica de Datos Estadísticos Interconectados

## Descripción General
El módulo `viz_estadistica` está diseñado para facilitar el análisis de datos estadísticos oficiales mediante su **normalización, interconexión y visualización dinámica**. Permite a los usuarios seleccionar variables de diferentes fuentes de datos normalizadas y explorar su evolución temporal a través de gráficos interactivos y filtros de fecha.
## ⚠️ Prerrequisito Importante: Entorno de Ejecución
Este módulo utiliza la librería `ipywidgets` (o funcionalidades similares como `interact` de IPython), lo que permite la creación de una interfaz de usuario interactiva (filtros, botones, selectores) directamente en el cuaderno.
**Debido a esta dependencia, el módulo NO SE PUEDE ejecutar ni visualizar correctamente a través de la interfaz estática de GitHub o servicios similares.**
Para interactuar con la aplicación, debe:
1.  **Descargar** el proyecto completo (cuaderno `.ipynb` y directorio de fuente de datos data_clean*).
2.  **Ejecutarlo** en el entorno de cuaderno interactivo **Google Colaboratory (Colab)** 
## 📂 Estructura de Archivos Requerida
Para que el módulo funcione correctamente, es **IMPRESCINDIBLE** que la estructura de directorios se mantenga intacta:
| Archivo/Directorio | Descripción |
| :--- | :--- |
| `notebooks/viz_estadistica.ipynb` | Módulo principal con las funciones de carga de datos, interconexión, filtrado y graficación dinámica. |
| `data_clean/` | **Directorio de Datos:** Contiene los datasets limpios, normalizados y listos para el análisis |
## 🚀 Uso
Una vez que el directorio data_clean/ contenga los archivos procesados, puede iniciar el dashboard interactivo.
1. Abra y ejecute el cuaderno dashboard_viz.ipynb.
2. Complete la ruta correcta del directorio data_clean/ tal cual figura en su Google Drive
3. Una vez inicializado, use los selectores de datos y variables y los filtros de fecha (inicio/fin) para:

    * Unificar variables de diferentes datasets.
  
    * Observar la evolución gráfica de las series de tiempo.
  
    * Descargar tanto la gráfica generada como el Dataset Customizado (el archivo CSV con los datos unificados y filtrados).

Si encuentra errores de carga de archivos, asegúrese de que el entorno tiene acceso al directorio data_clean/ con los permisos correctos.
## 📜 Registro de Versiones
| Version | Fecha | Descripción |
|:--- | :--- |:--- |
| V1.0 | 2025/12/03 |- Seleccion de rango de fechas, hasta 6 fuentes de datos, estilos, colores, titulos, subtitulos, grid, descarga del png y csv|
