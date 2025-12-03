# Data Clean

Este directorio contiene los **datasets ya depurados, transformados y estandarizados** como resultado del proceso ETL aplicado sobre los datos originales del INDEC.

## Contenido
- Archivos derivados desde `data_raw/`, con:
  - Corrección de tipos de datos.
  - Estandarización de nombres de columnas.
  - Formatos normalizados para su análisis.
- Todos los datasets se encuentran listos para ser utilizados por scripts de análisis y por la futura interfaz interactiva.

## Propósito
El objetivo de este directorio es:
- Proveer datos limpios y consistentes para análisis estadísticos.
- Facilitar la exploración y visualización en la futura aplicación interactiva.
- Permitir reproducir el flujo completo desde datos crudos hasta datos listos para análisis.

## Trazabilidad
Cada archivo dentro de este directorio corresponde a un dataset de `data_raw/` y su transformación sigue criterios documentados en el proceso ETL.

## Origen de los datos
Todos los datasets provienen de datos oficiales publicados por el INDEC.

## Autor
**Martín Nicolás Serafini**
