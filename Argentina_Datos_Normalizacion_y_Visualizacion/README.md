# Proyecto de Normalización y Visualización de Datos Públicos

Este repositorio forma parte de un proyecto personal orientado a **normalizar y estandarizar datasets estadísticos publicados por el INDEC (Instituto Nacional de Estadística y Censos de la República Argentina)**.  
El objetivo final es construir una aplicación que permita:

- seleccionar series provenientes de organismos oficiales,
- integrarlas en una línea de tiempo común,
- compararlas y visualizarlas,
- y descargar tanto los gráficos como los datasets ya normalizados.

Actualmente el repositorio contiene la **primera etapa del proyecto**, centrada exclusivamente en datos del INDEC.

---

## Objetivo del Proyecto

Los datos públicos oficiales, si bien confiables en su origen, suelen presentar **diversidad estructural** que dificulta su comparación directa. En particular, los datasets del INDEC pueden incluir:

- distintos formatos de período (`set-2014`, columnas Año/Mes, strings heterogéneos);
- variaciones intermensuales o interanuales ausentes o con menor precisión decimal;
- estructuras y nomenclaturas desiguales entre series.

El proceso de ETL aplicado busca:

- unificar todos los formatos de fecha a un **único estándar `datetime`**;
- homogeneizar nombres de columnas y unidades;
- recalcular variaciones con una metodología consistente y más precisa;
- detectar inconsistencias o registros atípicos, incluso en fuentes oficiales;
- preparar las series para análisis comparables y visualizaciones futuras.

Este enfoque pone el énfasis no solo en “limpiar datos”, sino en **comprender su estructura y lógica de origen** para fortalecer la calidad analítica.

---

## Estructura del Repositorio (Etapa Actual)

### `data_raw/`
Incluye únicamente datasets descargados directamente desde el portal del INDEC, sin ningún tipo de alteración.

### `data_clean/`
Contiene los mismos datasets luego de la normalización, estandarización y cálculos derivados.

---

## Etapas Futuras

El proyecto incorporará progresivamente:

### 1. Código del ETL

### 2. Aplicación interactiva
Una aplicación (Gradio o Streamlit) que permitirá:

- seleccionar series del INDEC u otros organismos,
- graficarlas en una línea de tiempo unificada,
- compararlas,
- descargar gráficos y datasets listos para análisis.

---

## 📝 Estado del Proyecto

✔️ Normalización inicial de datasets del INDEC  
✔️ Publicación de datos crudos y limpios  
✔️ Identificación y reporte de inconsistencias (incluido un caso confirmado por INDEC)  
⏳ Incorporación del código ETL  
⏳ Desarrollo de la app interactiva  
⏳ Documentación técnica extendida

---

## Origen de los Datos

Todos los datasets provienen del sitio oficial del **INDEC**, descargados para su procesamiento sin modificaciones previas.

---
## Autor y contacto
**Martín Nicolás Serafini**

Tecnicatura Superior en Ciencia de Datos e Inteligencia Artificial
2025 — Buenos Aires, Argentina

**Linkedin:** [Link](https://www.linkedin.com/in/martin-nicolas-serafini-05224923b/)

---

## 📄 Licencia

Este proyecto se distribuye bajo licencia **MIT**.



