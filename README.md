# Analisis-de-desempeno-RappiPlus
Se realizó un análisis del desempeño comercial con uso de herramientas de Python, obteniendo revenue, costos y ganancias, además de estructurar un funnel de conversión, crear cohortes para evaluación de la tasa de retención y tests estadísticos de probables cambios a la plataforma. 

## ❓​ Pregunta de negocio: 
- ¿Qué tan rentable está siendo el negocio, evaluándolo por producto y departamento, tomando de referencia el periodo del 2025.

## 🔢​ Datos: 
Se trabajó con los siguientes datasets: 

- `rappiplus_orders_raw.csv` → información de ordenes realizadas en el periodo de 2025.
- `rappiplus_marketing_spends.csv`→ información de gastos realizados en campañas de marketing realizados en el periodo de 2025.
- `rappiplus_catalog.csv` → información de productos disponibles en la plataforma, costo unitario, proveedor y categoría de producto.
- `experiment_checkout_ui.csv` → información de resultados del experimento sobre los cambios en la plataforma tipo A-B.

## ⚙️​ Procesos y 🔎​ Hallazgos: 
- Se realizó cambio de tipo de dato a datetime a la variable `fecha_hora_pedido` de la tabla  `orders_raw` utilizando `pd.to_datetime`, se corrigieron variaciones de escritura de la misma variable en la columna `pais` de la tabla `orders_raw` utilizando la función `.replace`,  se eliminaron un porcentaje no significativo de valores nulos utilizando `dropna.`, se establece tipo de dato a `int64` en la variable `cantidad` en la tabla `orders_raw` y, finalmente, en la tabla `marketing_raw` se realizó cambios de variable fecha a tipo datetime, identifique un 6.23% de datos nulos, los cuales se eliminan juntos a su respectiva fila. Posteriormente se generaron documentos CSV nuevos con los datasets limpios.

- Se realizó un análisis de rentabilidad del negocio en general, consiguiendo el ingreso total (revenue) de $51873170.44, costo total de $43095280.85, la inversión en marketing total de $2694664.43 y la rentabilidad con uso de la ganancia total del negocio (profit) de $6083225.16. 
- Posteriormente evalué por segmentación por producto, el comportamiento de ventas obteniendo el ticket promedio de $2100.13, cantidad de producto promedio por orden de 7.17 productos, el producto mas vendido siendo la Laptop-Gaming-16GB con 144181 unidades vendidas y el canal con mayor gasto en marketing siendo este `social`.
- Pese al valor alto de ganancias observado en los KPI del periodo evaluado, recomiendo un análisis comparativo con años previos para evaluar que tanto ha crecido o disminuido las ganancias de la plataforma.

- Desarrollé un análisis de funnel de conversión de la plataforma utilizando herramientas de SQL obteniendo los siguientes resultados: 
<img width="493" height="306" alt="image" src="https://github.com/user-attachments/assets/b1200ec2-f6e3-4c5e-85ca-4acce77ad3bd" />

- Se encuentra que hay una tasa de conversión final de aproximadamente 80%, lo que indica una conversión bastante alta de clientes.

- Creé cohortes para evaluar la tasa de retención de clientes nuevos en la plataforma de acuerdo a las fechas en las que realizaron su primera compra, utilizando herramientas de SQL se generaron cohortes por mes del año 2025. Tomé las tasas de retención de los clientes que compraron por primera vez en los primeros 5 meses del año 2025 obteniendo los siguientes resultados: 
<img width="489" height="288" alt="image" src="https://github.com/user-attachments/assets/a33ed367-e449-44c1-8f8a-0d02b1ff2e38" />

- Podemos observar que la tasa de retención independientemente del cohorte se mantuvo casi igual a lo largo del periodo evaluado, por lo que recomendé hacer una revisión de ofertas, programas de fidelidad o el marketing que se estuvo haciendo a los clientes ya registrados para aumentar su tasa de retención en la plataforma.

- Se genera un experimento UI de tipo A-B el cual se entrega en un CSV para poder realizar un test estadístico de Chi-Cuadrado (utilizando un alpha de 0.05), utilizando las herramientas de scipy.stats de Pandas, obtuve un valor chi-cuadrado: 0.618 y un valor P: 0.432 lo que nos indica que los resultados podrían verse asociados al azar y no con cambios reales por los cambios aplicados a la plataforma. Por lo que finalmente concluí que no deben realizarse los cambios de momento, se requieren nuevas evaluaciones de los cambios sugeridos. 


## ✔️​ Recomendación: 
- Se recomienda implementar una estrategia de optimización basada en datos que permita evaluar la evolución de la rentabilidad, identificar oportunidades de crecimiento en ventas, optimizar la inversión en marketing y fortalecer la retención de clientes. Asimismo, se propone analizar las estrategias comerciales de los productos con mejor desempeño para replicar las prácticas exitosas en otras categorías. Finalmente, se recomienda mantener los cambios del experimento en evaluación hasta contar con evidencia estadística suficiente que demuestre su impacto positivo en los resultados del negocio.


## ⏯️​ Cómo reproducirlo: 
- Librerías utilizadas: Pandas, Matplotlib.pyplot, Numpy, Seaborn, Scipy.stats y SQLalchemy.
- Versión de Python: 3.9.25
- Pasos:
1. Abre `notebooks/S12 Estudiante_Proyecto_Final.ipynb`
2. Ejecuta las celdas en orden
3. El notebook carga automáticamente el dataset desde `/data/` o desde un enlace público (según corresponda)
