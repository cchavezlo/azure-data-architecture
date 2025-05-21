# 📘 Bitácora ETL – Proyecto Bolsa de Valores

Esta bitácora documenta la ejecución del flujo ETL para procesar datos de precios de acciones desde una API financiera pública.

## 🗓️ Día 1 – Ingesta
- Fuente: API REST de Financial Modeling Prep (`https://financialmodelingprep.com/`)
- Endpoint: `/historical-price-full/AAPL?serietype=line`
- Estado: ✔️ Datos recibidos correctamente (1000+ registros)

## 🗓️ Día 2 – Limpieza y calidad
- Se eliminaron registros sin volumen o con precio negativo.
- Se detectaron y removieron 12 duplicados (`symbol + date`).
- Se validó consistencia de fechas y símbolos.

## 🗓️ Día 3 – Consolidación
- Archivos escritos en formato Delta en capa `master`.
- Creación de vista temporal para consultas por fecha, volumen y promedio móvil.

## 🧩 Observaciones
- Algunos símbolos (como acciones extranjeras) mostraban precios en otras monedas.
- Se documentó una posible expansión para integrar tipo de cambio USD/PEN.

---

## 🧠 Recomendaciones Futuras
- Automatizar la ingesta con Azure Data Factory y triggers diarios.
- Agregar validación cruzada con datos del Banco Central para comparación.
- Implementar reglas de alerta ante caídas bruscas (>10%) día a día.
