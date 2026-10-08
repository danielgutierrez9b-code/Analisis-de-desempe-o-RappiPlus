# Analisis-de-desempeno-RappiPlus
Se realizó un análisis del desempeño comercial con uso de herramientas de Python, obteniendo revenue, costos y ganancias, además de estructurar un funnel de conversión, crear cohortes para evaluación de la tasa de retención y tests estadísticos de probables cambios a la plataforma. 

## 🧠 Objetivo del análisis

- Identificar problemas de calidad de datos.
- Construir un pipeline de limpieza reproducible.
- Analizar los valores KPI financieros, segmentaciones por cohortes, cálculo de tasas de retención y análisis por pruebas estadísticas entre variables.
- Generar recomendaciones sobre las áreas de oportunidad que se presenta en departamentos y sugerencia de toma de decisión sobre cambios en la plataforma.

Se trabajó con los siguientes datasets: 
`rappiplus_orders_raw.csv` → información de ordenes realizadas en el periodo de 2025.
`rappiplus_marketing_spends.csv`→ información de gastos realizados en campañas de marketing realizados en el periodo de 2025.
`rappiplus_catalog.csv` → información de productos disponibles en la plataforma, costo unitario, proveedor y categoría de producto.
`experiment_checkout_ui.csv` → información de resultados del experimento sobre los cambios en la plataforma tipo A-B.

## 📂 Contenido del repositorio
- `notebooks/S12 Estudiante_Proyecto_Final.ipynb`
  → Notebook principal con limpieza, segmentaciones, tests estadísticos y conclusiones.


## 📘 Cómo reproducir el análisis

1. Abre `notebooks/S12 Estudiante_Proyecto_Final.ipynb`
2. Ejecuta las celdas en orden
3. El notebook carga automáticamente el dataset desde `/data/` o desde un enlace público (según corresponda)
