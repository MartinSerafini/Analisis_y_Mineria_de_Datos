> 🇬🇧 [English version](README.en.md)

# Análisis de fallas Parque Solar — Entre Ríos, Argentina

Análisis exploratorio de la bitácora de fallas de un parque fotovoltaico en Entre Ríos, Argentina. El objetivo es sentar las bases para el pasaje de un mantenimiento reactivo a uno preventivo basado en datos.

**Período analizado:** febrero – abril 2026 (70 días)  
**Infraestructura:** +2K paneles solares · 16 inversores · 4 grupos (A, B, C, D)

---

## Hallazgos principales

**Comportamiento general de la flota**
- La frecuencia de fallas es similar entre los cuatro grupos (287–309 eventos), pero las horas afectadas difieren hasta un 54% (Grupo C: 736 h vs. Grupo D: 477 h). La diferencia se explica por el mix de tipo de falla, no por la frecuencia.
- Frecuencia y severidad no están correlacionadas. F24 (aislamiento CC) lidera en cantidad de eventos (355 eventos, 30% del total), pero F35 (sin tensión de red) concentra el mayor tiempo de indisponibilidad (1.163 horas). La falla más frecuente no es la más costosa.
- Ningún inversor cae en el cuadrante crítico (alta frecuencia y larga duración de forma simultánea).
- A2, B2 y D3 presentan alta frecuencia y corta duración, con más del 98% de coocurrencia con la flota: funcionan como indicadores de sensibilidad ante perturbaciones de red, no como equipos problemáticos.
- C4 es el único inversor con 10% de fallas en solitario (sin coocurrencia con la flota), lo que sugiere una vulnerabilidad local además de los factores sistémicos.

**F24 — falla de aislamiento CC**
- El 94% de los eventos F24 ocurre entre las 06:00 y las 08:00, con pico a las 07:00, y un desplazamiento estacional que acompaña el retraso del amanecer entre febrero y abril.
- La diferencia entre un día con F24 y uno sin F24 no se construye en el momento de la falla, sino en las 8 horas previas al arranque. En días con falla, el margen temperatura–punto de rocío cae de 3,8 °C a 1,4 °C durante la noche; en días sin falla, se mantiene por encima de 5,0 °C.
- El patrón dominante es la reincidencia consecutiva (3–4 días), no eventos aislados. El Grupo C muestra reincidencia crónica; el Grupo D es resistente y presenta mayormente episodios de un solo día.

---

## Estructura del repositorio

```
solar-park-fault-analysis/
│
├── notebooks/
│   └── analisis_parque_solar.ipynb                        # Cuaderno principal 
│
├── data/
│   └── raw/
│       ├── bitacora_alertas.xlsx                          # Bitácora de fallas anonimizada (inversores A1–D4)
│       ├── datos_clima_gualeguaychu.csv                   # Datos climáticos horarios — Meteostat
│       ├── horarios_sol_gualeguaychu_2026_transpuesto.csv # Horarios de salida y puesta del sol
│       └── coco.csv                                       # Diccionario de códigos de condición climática (Meteostat)
│
└── reports/
    └── informe_parque_solar.pdf                           # Informe del análisis
```

---

## Metodología

**Enriquecimiento climático**
- Modelo de irradiancia de cielo sin nubes (Ortiz de Adler et al., 2010) con factores de turbidez de Linke mensuales calibrados para Entre Ríos (Grossi Gallegos & Spreafichi, 2011).
- Temperatura de panel estimada mediante modelo NOCT (IEC 61215) con corrección de enfriamiento por viento.
- Indicadores de riesgo de condensación calculados sobre ventana móvil de 8 horas: margen temperatura–punto de rocío, humedad relativa mínima, precipitación acumulada e indicador binario de arranque húmedo.

**Análisis de fallas**
- Fallas clasificadas en tres grupos: fallas de red eléctrica (F30, F35, F41, F43, F45, F47, F48), fallas de aislamiento CC (F20, F23, F24, F26) y fallas de hardware (F64).
- Se utiliza la mediana en lugar de la media para evitar distorsión por outliers extremos.
- Detección de outliers mediante umbral dinámico (Q3 + 1,5 × IQR) por inversor.
- Análisis de coocurrencia para distinguir causas sistémicas de vulnerabilidades locales.
- El análisis de F24 usa el día calendario como unidad de análisis, dado que las observaciones horarias dentro de un mismo día no son independientes.

---

## Alcance

Este informe analiza en profundidad dos fenómenos prioritarios: el comportamiento general de la flota y la falla F24. El análisis falla por falla para el resto de los tipos de evento (F35, F41, F47/F48, F64 y variantes de aislamiento) está en desarrollo y será incorporado en entregas sucesivas.

La consolidación estadística de los hallazgos presentados requiere al menos un ciclo anual completo para contemplar la variación estacional.

---

## Reproducción del análisis

1. Clonar el repositorio.
2. Abrir `notebooks/analisis_parque_solar.ipynb` en Google Colab o Jupyter.
3. Colocar los archivos de datos en `data/raw/` (las rutas están configuradas como relativas, sin configuración adicional).
4. Ejecutar todas las celdas en orden. El cuaderno corre de punta a punta sin intervención manual.

**Dependencias:** `numpy`, `pandas`, `matplotlib`, `seaborn`, `scipy`, `openpyxl` — disponibles en el entorno estándar de Colab.

---

## Autor
Martín Nicolás Serafini

Consultor independiente — análisis de datos y asesoría contable, Argentina.  
[LinkedIn](https://www.linkedin.com/in/martin-nicolas-serafini-05224923b/) · [GitHub](https://github.com/MartinSerafini)
