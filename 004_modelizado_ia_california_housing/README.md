# Modelizado de Sistemas de IA
**Dataset Seleccionado: : Caso California Housing**

**Material de Clase: Metodología de Trabajo y Comparativa de Modelos (Lineal vs. MLP)**

Este repositorio contiene el soporte práctico y teórico que desarrollé y expuse como docente invitado para la materia **Modelizado de Sistemas de IA** en el **IFTS 11** (CABA, Argentina), bajo la titularidad del profesor **Andrés Allievi**.

## Filosofía del Proyecto
Más allá de la implementación de algoritmos, este cuaderno propone una **metodología de trabajo sistémica** para encarar problemas basados en datos. Se parte de la premisa de que entender la naturaleza de los predictores y la estructura del dataset es un paso fundamental y obligatorio antes de cualquier tarea de modelado.

Por ello, el flujo de trabajo dedica un espacio crítico a la exploración y limpieza, priorizando la interpretabilidad de los datos para garantizar que la posterior aplicación de IA sea consistente y robusta.

## Contenido del Repositorio
* **`Clase_20260514.ipynb`**: Notebook principal que documenta el ciclo de vida del proyecto: ETL, análisis exploratorio profundo (EDA), preprocesamiento, entrenamiento y evaluación.
* **`best_mlp_model.pkl`**: Pesos del Perceptrón Multicapa (MLP) optimizado.
* **`scaler_mlp.pkl`**: Objeto de escalado estadístico para asegurar la consistencia en la escala de los datos durante la inferencia.
* **Tablas de Rendimiento**: Comparativa de métricas (MSE, MAE, R²) para validar el desempeño relativo de los modelos.

## Estructura Metodológica
1.  **Exploración y Curación de Datos (EDA/ETL):** Análisis de la naturaleza de las variables, detección de outliers y comprensión de los predictores.
2.  **Preparación de Datos:** Ingeniería de características y normalización, fundamentando por qué la Red Neuronal requiere un tratamiento específico de los datos.
3.  **Modelado Comparativo:**
    * *Baseline:* Regresión Lineal para establecer un marco de referencia.
    * *Deep Learning:* MLPRegressor para capturar patrones no lineales complejos.
4.  **Evaluación y Conclusiones:** Análisis crítico de los resultados para determinar si el incremento en la complejidad técnica se traduce en un beneficio real de negocio o investigación.

## Requisitos y Uso
* Entorno Python 3.x con las librerías: `scikit-learn`, `pandas`, `numpy`, `joblib` y `matplotlib`.
* **Nota para Inferencia:** Es indispensable cargar `scaler_mlp.pkl` y aplicar `.transform()` a cualquier dato nuevo antes de utilizar el modelo entrenado, manteniendo así la integridad de la escala estadística.

---
**Expositor Invitado:** Martin Nicolas Serafini  
**Materia:** Modelizado de Sistemas de IA  
**Institución:** IFTS 11 (CABA)  
**Docente Titular:** Andres Allievi  
**Fecha de la clase:** 14 de mayo de 2026
