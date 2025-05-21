# 🏗️ Arquitectura de Datos en Azure con Databricks + Delta Lake

Este proyecto personal simula un entorno de procesamiento de datos bancarios, implementando un pipeline completo de ingesta, validación, transformación y calidad de datos en la nube con tecnologías modernas como Azure, Databricks, Spark y Delta Lake.

## 🎯 Objetivos

- Ingestar archivos CSV, Parquet y JSON desde Azure Blob Storage.
- Transformar y limpiar datos con PySpark en Databricks.
- Aplicar reglas de calidad de datos por capas: raw, staging y master.
- Almacenar resultados en Delta Lake para auditoría y versionado.
- Orquestar el flujo de procesamiento con Azure Data Factory.

## 🧱 Arquitectura

![Arquitectura](images/diagrama_arquitectura.png)

## 🛠️ Tecnologías Utilizadas

- Azure Blob Storage
- Azure Databricks
- Apache Spark (PySpark)
- Delta Lake
- Azure Data Factory
- Python
- SQL

## 🧪 Reglas de Calidad de Datos

- No nulos en campos obligatorios (`nombre`, `email`)
- Edad entre 0 y 100
- Eliminación de duplicados por `id`
- Validación de correos electrónicos

Ver [docs/reglas_calidad.md](docs/reglas_calidad.md)

## 🚀 Cómo Ejecutar

1. Cargar archivos de muestra en `/data/`
2. Ejecutar los notebooks en el orden:
   - `01_ingesta_raw.ipynb`
   - `02_limpieza_staging.ipynb`
   - `03_validacion_master.ipynb`
3. Validar salidas en Delta Lake y vistas SQL.
4. Orquestar con ADF o scripts adicionales.

## 📸 Capturas de Evidencia

- Azure Data Factory:
  ![ADF](images/adf_pipeline.png)

## 📂 Organización del Repositorio

| Carpeta | Descripción |
|---------|-------------|
| `/notebooks` | Notebooks con lógica ETL |
| `/data` | Archivos simulados para pruebas |
| `/images` | Diagramas y capturas del proyecto |
| `/docs` | Reglas, bitácora, documentación adicional |

## 🧠 Autor

**Carolina Boniee Chávez López**  
[LinkedIn](https://linkedin.com/in/cchavezlo) | [GitHub](https://github.com/cchavezlo)

---

