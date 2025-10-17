# Reconfiguración del Mercado del Cine en Estados Unidos (1995–2024): Economía · Audiencia · Tecnología

Este repositorio contiene los materiales, datos y cuadernos de trabajo asociados al estudio **“Reconfiguración del Mercado del Cine en Estados Unidos (1995–2024): Economía, Audiencia y Tecnología”**, que analiza la evolución estructural del mercado cinematográfico estadounidense a partir de datos de taquilla, precios de entradas, asistencia y concentración del mercado.

El proyecto combina análisis económico, cultural y tecnológico para identificar los factores que explican la pérdida de centralidad del cine en sala frente al auge del streaming y la transformación digital del ecosistema audiovisual.

---
## Contenido del repositorio
| Archivo / Carpeta | Descripción |
|--------------------|-------------|
| `Reconfiguracion_del_Mercado_del_Cine_en_EEUU_1995-2024.pdf` | Documento principal del estudio, versión académica en formato PDF. |
| `notebooks/01_scraping_boxoffice.ipynb` | Cuaderno de Google Colab utilizado para la recolección de datos mediante *web scraping* y *PDF scraping*. |
| `notebooks/02_visualizaciones_taquilla.ipynb` | Cuaderno de Google Colab con la generación de series temporales, gráficos y análisis visual. |
| `data/` | Carpeta con los datasets obtenidos a partir del scraping y su versión procesada (archivos `.csv`). Incluye datos de taquilla, precios de tickets y asistencia estimada. |
| `README.md` | Este archivo descriptivo. |

---
## Objetivos del estudio

1. Analizar la evolución real de la taquilla cinematográfica estadounidense entre 1995 y 2024, ajustada por inflación.
2. Estimar la cantidad de espectadores (tickets vendidos) a partir del precio promedio anual de las entradas.
3. Identificar patrones de polarización en la distribución de la taquilla (Top 10, Top 200, total anual).
4. Evaluar la influencia de factores externos (crisis, eventos globales, pandemia) sobre la asistencia.
5. Examinar el rol del *streaming* y las franquicias (caso MCU) en la reconfiguración del mercado.

---
## Metodología y procesamiento

El estudio integra múltiples fuentes y técnicas:
- **Recolección de datos:**  
  Web scraping de *Box Office Mojo* y *The Numbers* (agosto 2025).  
  Extracción complementaria de PDFs.
- **Ajuste por inflación:**  
  Valores expresados en dólares constantes de 2024, utilizando el **IPC**.
- **Estimación de espectadores:**  
  Cálculo = Recaudación nominal anual / Precio promedio del ticket (*The Numbers*).  
- **Procesamiento de datos:**  
  Implementado en **Python** con `pandas`, `numpy`, `matplotlib` y `seaborn`.
- **Enfoque metodológico:**  
  Estudio descriptivo-analítico, con enfoque mixto (cuantitativo descriptivo y cualitativo contextual).

---
## Autor y contacto
**Martín Nicolás Serafini**
Tecnicatura Superior en Ciencia de Datos e Inteligencia Artificial
2025 — Buenos Aires, Argentina
**Linkedin:** [Link](https://www.linkedin.com/in/martin-nicolas-serafini-05224923b/)
