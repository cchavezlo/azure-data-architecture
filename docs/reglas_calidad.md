# ✅ Reglas de Calidad de Datos – Proyecto de Bolsa de Valores

Este documento describe las reglas de validación aplicadas a los datos financieros obtenidos de APIs públicas sobre acciones, índices bursátiles y precios históricos.

## 🧪 Reglas Aplicadas

### 1. Registros completos
- Todos los campos obligatorios (`symbol`, `date`, `close`, `volume`) deben estar presentes.
- Se eliminan registros con valores nulos en campos críticos.

### 2. Precios y volumen válidos
- `close` > 0
- `volume` ≥ 0

### 3. Validación de símbolo de acción
- El símbolo debe ser una cadena alfanumérica de máximo 5 caracteres.  
- Ejemplo: `AAPL`, `MSFT`, `GOOG`.

### 4. Fechas válidas
- El campo `date` debe tener formato ISO (`yyyy-MM-dd`) y pertenecer a un rango realista (por ejemplo, entre 2010 y hoy).

### 5. Duplicados
- Se eliminan registros duplicados por combinación de `symbol + date`.

---

## 📌 Notas
Estas reglas aseguran que los análisis financieros como medias móviles, variaciones y patrones se basen en datos consistentes y confiables.
