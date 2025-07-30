# 📈 Análisis Predictivo de Churn - Telecom X



Este proyecto implementa un **sistema predictivo de cancelación de clientes (churn)** para Telecom X, combinando análisis exploratorio avanzado y modelos de machine learning para identificar patrones de abandono.

## 🎯 Objetivo Principal
Desarrollar un **modelo predictivo con >85% de precisión** que permita:
- Identificar clientes con alto riesgo de cancelación
- Revelar los factores claves que influyen en el churn
- Proponer estrategias de retención basadas en datos

## 🏗 Estructura del Proyecto

### 1. Preparación de Datos
- **ETL completo** desde archivo JSON original
- Tratamiento de valores nulos y outliers
- Ingeniería de características:
  - `Cuentas_Diarias` = FacturaMensual/30
  - `TotalServicios` = Suma de servicios contratados
- Codificación de variables categóricas (One-Hot Encoding)

### 2. Análisis Exploratorio (EDA)
Principales hallazgos:
- **27.5% tasa general de churn**
- Variables críticas:
  | Variable | Correlación con Churn |
  |----------|----------------------|
  | MesesDeAntigüedad | -0.42 |
  | TipoContrato_Mensual | +0.39 | 
  | FacturaMensual | +0.25 |



### 3. Modelado Predictivo
Comparativa de modelos:

| Modelo | Accuracy | Precision | Recall | F1-Score |
|--------|----------|-----------|--------|----------|
| DummyClassifier | 0.50 | 0.00 | 0.00 | 0.00 |
| DecisionTree | 0.80 | 0.72 | 0.68 | 0.70 |
| **RandomForest** | **0.86** | **0.79** | **0.75** | **0.77** |

### 4. Variables Clave Identificadas

1. `TipoContrato_Mensual` (+39% riesgo)
2. `MesesDeAntigüedad` (-42% riesgo)
3. `FacturaMensual` (+25% riesgo)
4. `SinSeguridadEnLinea` (+60% riesgo)

## 🛠 Tecnologías Utilizadas
- **Python 3.10**
- Pandas, NumPy (Manipulación de datos)
- Scikit-learn (Modelado)
- Matplotlib/Seaborn (Visualización)
- Jupyter Notebook (Análisis interactivo)

## 📌 Recomendaciones de Negocio
1. **Programa "Primeros 6 Meses"**: Descuentos especiales para nuevos clientes
2. **Conversión a contratos anuales**: Bonificación de 1 mes gratis
3. **Paquetes con servicios esenciales**: Incluir seguridad en línea por defecto
4. **Sistema de alerta temprana**: Monitoreo de clientes con:
   - Factura > $70 
   - Antigüedad < 12 meses
   - Contrato mensual

## 🚀 Cómo Ejecutar
```bash
