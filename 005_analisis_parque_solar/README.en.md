> 🇦🇷 [Versión en castellano](README.md)

# Solar Park Fault Analysis — Entre Rios, Argentina

Exploratory analysis of the fault log from a photovoltaic solar park in Entre Ríos, Argentina. The goal is to support the transition from reactive to data-driven preventive maintenance.

**Analysis period:** February – April 2026 (70 days)  
**Infrastructure:** +2K solar panels · 16 inverters · 4 groups (A, B, C, D)

---

## Key Findings

**Fleet-level behavior**
- Fault frequency is similar across all four groups (287–309 events), but total hours affected differ by up to 54% (Group C: 736 h vs. Group D: 477 h). The gap is explained by fault type mix, not frequency.
- Fault frequency and severity are not correlated. F24 (DC isolation) leads in event count (355 events, 30% of total), but F35 (no grid voltage) accounts for the most downtime (1,163 hours). The most frequent fault is not the most costly.
- No inverter falls into the critical quadrant (high frequency + long duration simultaneously).
- A2, B2, and D3 show high frequency and short duration, with over 98% co-occurrence with the fleet — they act as sensitivity indicators for grid disturbances, not as problematic units.
- C4 is the only inverter with 10% of faults occurring in isolation (no fleet co-occurrence), suggesting a local vulnerability in addition to systemic factors.

**F24 — DC isolation fault**
- 94% of F24 events occur between 06:00 and 08:00, peaking at 07:00, with a seasonal shift that tracks the delayed sunrise from February to April.
- The difference between a day with F24 and a day without is not built at the moment of the fault — it is built in the 8 hours prior to startup. On fault days, the temperature–dew point margin drops from 3.8 °C to 1.4 °C overnight; on fault-free days it holds above 5.0 °C.
- The dominant pattern is consecutive recurrence (3–4 days), not isolated events. Group C shows chronic recurrence; Group D is resistant and mostly shows single-day episodes.

---

## Repository Structure

```
solar-park-fault-analysis/
│
├── notebooks/
│   └── analisis_parque_solar.ipynb                         # Main notebook — runs end to end
│
├── data/
│   └── raw/
│       ├── bitacora_alertas.xlsx                           # Anonymized fault log (inverters labeled A1–D4)
│       ├── datos_clima_gualeguaychu.csv                    # Hourly climate data — Meteostat
│       ├── horarios_sol_gualeguaychu_2026_transpuesto.csv  # Sunrise/sunset times
│       └── coco.csv                                        # Meteostat condition code dictionary
│
└── reports/
    └── informe_parque_solar.pdf                            # Full analysis report (27 slides)
```

---

## Methodology

**Climate enrichment**
- Clear-sky irradiance model (Ortiz de Adler et al., 2010) with monthly Linke turbidity factors calibrated for Entre Ríos (Grossi Gallegos & Spreafichi, 2011).
- Panel temperature estimated via NOCT model (IEC 61215) with wind-cooling correction.
- Condensation risk indicators computed over a 6-hour rolling window: temperature–dew point margin, minimum relative humidity, accumulated precipitation, and a wet-startup binary flag.

**Fault analysis**
- Faults classified into three groups: grid faults (F30, F35, F41, F43, F45, F47, F48), DC isolation faults (F20, F23, F24, F26), and hardware faults (F64).
- Median used throughout instead of mean to avoid distortion from extreme outliers.
- Outlier detection via dynamic threshold (Q3 + 1.5 × IQR) per inverter.
- Co-occurrence analysis to distinguish systemic causes from local inverter vulnerabilities.
- F24 analysis uses the calendar day as the unit of analysis — hourly observations within the same day are not independent.

**Methodological note on F24 timing**  
Event timestamps use the actual fault opening time (`hora_abierta`) rather than the normalized reference time, correcting a potential bias of up to 59 minutes in minutes-since-sunrise calculations. With this correction: median on fault days = −7 min (before sunrise); median on fault-free days = +14 min.

---

## Scope

This report covers two priority phenomena in depth: fleet-level behavior and the F24 fault. Fault-by-fault analysis for the remaining event types (F35, F41, F47/F48, F64, and isolation variants) is under development and will be incorporated in subsequent deliveries.

Statistical consolidation of the findings presented here requires at least one full annual cycle to account for seasonal variation.

---

## Reproducing the Analysis

1. Clone the repository.
2. Open `notebooks/analisis_parque_solar.ipynb` in Google Colab or Jupyter.
3. Place the raw data files in `data/raw/` (paths are set as relative — no additional configuration needed).
4. Run all cells in order. The notebook runs end to end without manual intervention.

**Dependencies:** `numpy`, `pandas`, `matplotlib`, `seaborn`, `scipy`, `openpyxl` — all available in the standard Colab environment.

---

## Author
Martín Nicolás Serafini

Independent consultant — data analysis and tax advisory, Argentina.  
[LinkedIn](https://www.linkedin.com/in/martin-nicolas-serafini-05224923b/) · [GitHub](https://github.com/MartinSerafini)
